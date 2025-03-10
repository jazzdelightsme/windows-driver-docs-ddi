---
UID: NF:wudfddi.IWDFUnifiedPropertyStore.SetPropertyData
title: IWDFUnifiedPropertyStore::SetPropertyData (wudfddi.h)
description: The SetPropertyData method modifies the current setting of a device property.
old-location: wdf\iwdfunifiedpropertystore_setpropertydata.htm
tech.root: wdf
ms.assetid: 07A79E40-6C49-4AF8-90B8-26652C46B6F1
ms.date: 02/26/2018
ms.keywords: IWDFUnifiedPropertyStore interface,SetPropertyData method, IWDFUnifiedPropertyStore.SetPropertyData, IWDFUnifiedPropertyStore::SetPropertyData, SetPropertyData, SetPropertyData method, SetPropertyData method,IWDFUnifiedPropertyStore interface, umdf.iwdfunifiedpropertystore_setpropertydata, wdf.iwdfunifiedpropertystore_setpropertydata, wudfddi/IWDFUnifiedPropertyStore::SetPropertyData
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFUnifiedPropertyStore.SetPropertyData
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUnifiedPropertyStore::SetPropertyData


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetPropertyData</b> method modifies the current setting of a device property.


## -parameters




### -param PropertyKey [in]

A pointer to a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/dn315031(v=vs.85)">DEVPROPKEY</a> structure that specifies the device property key.


### -param Lcid [in]

Specifies a locale identifier. Set this parameter either to a language-specific LCID value or to LOCALE_NEUTRAL. The LOCALE_NEUTRAL LCID specifies that the property is language-neutral (that is, not specific to any language). Do not set this parameter to LOCALE_SYSTEM_DEFAULT or LOCALE_USER_DEFAULT. For more information about language-specific LCID values, see <a href="https://docs.microsoft.com/openspecs/windows_protocols/ms-lcid/63d3d639-7fd2-4afb-abbe-0d5b5551eef8">LCID Structure</a>.


### -param Flags [in]

Reserved. Drivers should set this value to 0.


### -param PropertyType [in]

A pointer to a <a href="https://docs.microsoft.com/previous-versions/ff543546(v=vs.85)">DEVPROPTYPE</a> value that specifies the type of the data that is provided in the <i>PropertyData</i> buffer.


### -param PropertyDataSize [in]

The size, in bytes, of the buffer that <i>PropertyData</i> points to.


### -param PropertyData [in, optional]

A pointer to the device property data. Set this parameter to <b>NULL</b> to delete the specified property.


## -returns



<b>SetPropertyData</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The framework's attempt to allocate memory failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32 (ERROR_INVALID_PARAMETER)</b></dt>
</dl>
</td>
<td width="60%">
If the driver specifies <b>WdfPropertyStoreRootClassDeviceInterfaceKey</b>, the requested interface must be one that the UMDF driver previously registered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32 (STATUS_NOT_SUPPORTED)</b></dt>
</dl>
</td>
<td width="60%">
The driver can modify device interface property data only  starting with  Windows 8.

</td>
</tr>
</table>
 

This method might return an HRESULT-typed value corresponding to one of the other values that <i>Winerror.h</i> contains.




## -remarks



Framework-based drivers use the <b>SetPropertyData</b> method to modify device properties that are defined as part of the unified device property model.

In particular, you can use this method to modify a device's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">hardware key</a> or an instance of a device interface class. When you call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfunifiedpropertystorefactory-retrieveunifieddevicepropertystore">IWDFUnifiedPropertyStoreFactory::RetrieveUnifiedDevicePropertyStore</a>, set the <i>RootSpecifier</i> parameter's <b>RootClass</b> member to <b>WdfPropertyStoreRootClassHardwareKey</b> or <b>WdfPropertyStoreRootClassDeviceInterfaceKey</b>.  

If you specify  <b>WdfPropertyStoreRootClassHardwareKey</b>, then when you call <b>SetPropertyData</b>, you must provide a custom <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/dn315031(v=vs.85)">DEVPROPKEY</a> value in the <i>PropertyKey</i> parameter, and  not a PnP-defined key. The value must have been previously set by calling <b>SetPropertyData</b>, a <a href="https://docs.microsoft.com/windows-hardware/drivers/install/using-device-installation-functions">SetupDI device property function</a>, or by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/install/inf-addproperty-directive">INF AddProperty directive</a>.

If the driver specifies <b>WdfPropertyStoreRootClassDeviceInterfaceKey</b>, the requested interface must be one that the UMDF driver previously registered at runtime.


If the driver registers an interface in its INF file, it must set associated properties in the INF as well.

For more information about accessing the registry, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT
SetFriendlyName(
    _In_ IWDFUnifiedPropertyStore * pUnifiedPropertyStore
    )
{
    HRESULT hr = S_OK;
    WCHAR friendlyName[] = L"UMDF OSR USB Fx2 Test Device";

    hr = pUnifiedPropertyStore->SetPropertyData(
            &DEVPKEY_Device_FriendlyName,
            0, //Lcid
            0, //Flags
            DEVPROP_TYPE_STRING, //Type
            sizeof(friendlyName),
            friendlyName
            );

    if (FAILED(hr))
    {
        TraceEvents(
            TRACE_LEVEL_ERROR,
            TEST_TRACE_DEVICE,             
            "SetPropertyData failed: hr = %!HRESULT!",
            hr
            );
        goto exit;
    }

exit:
    return hr;
}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfunifiedpropertystore-getpropertydata">GetPropertyData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfunifiedpropertystore">IWDFUnifiedPropertyStore</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfunifiedpropertystorefactory">IWDFUnifiedPropertyStoreFactory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfunifiedpropertystorefactory-retrieveunifieddevicepropertystore">RetrieveUnifiedDevicePropertyStore</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi_types/ns-wudfddi_types-_wdf_property_store_root">WDF_PROPERTY_STORE_ROOT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi_types/ne-wudfddi_types-_wdf_property_store_root_class">WDF_PROPERTY_STORE_ROOT_CLASS</a>
 

 

