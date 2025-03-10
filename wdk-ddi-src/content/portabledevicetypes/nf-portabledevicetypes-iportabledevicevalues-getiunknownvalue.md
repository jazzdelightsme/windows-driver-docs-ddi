---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetIUnknownValue
title: IPortableDeviceValues::GetIUnknownValue (portabledevicetypes.h)
description: Retrieves an IUnknown interface value (type VT_UNKNOWN) that is specified by a key.
old-location: wpddk\iportabledevicevalues_getiunknownvalue.htm
tech.root: wpd_dk
ms.assetid: ae66a86c-bf63-4bc7-87db-9d464004519a
ms.date: 02/15/2018
ms.keywords: GetIUnknownValue, GetIUnknownValue method, GetIUnknownValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetIUnknownValue method, IPortableDeviceValues.GetIUnknownValue, IPortableDeviceValues::GetIUnknownValue, IPortableDeviceValuesGetIUnknownValue, portabledevicetypes/IPortableDeviceValues::GetIUnknownValue, wpddk.iportabledevicevalues_getiunknownvalue
ms.topic: method
req.header: portabledevicetypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- PortableDeviceTypes.h
api_name:
- IPortableDeviceValues.GetIUnknownValue
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::GetIUnknownValue


## -description



Retrieves an <b>IUnknown</b> interface value (type VT_UNKNOWN) that is specified by a key.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> key that specifies the item to retrieve.


### -param ppValue [out]

Address of a variable that receives a pointer to the retrieved <b>IUnknown</b> interface. The caller is responsible for calling <b>Release</b> on the retrieved interface.


## -returns



The method returns an <b>HRESULT</b>. Possible values include, but are not limited to, those in the following table.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>DISP_E_TYPEMISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The property specified by <i>key</i> is not an <b>IUnknown</b> interface.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_NOT_FOUND)</b></dt>
</dl>
</td>
<td width="60%">
The property specified by <i>key</i> is not in the collection.

</td>
</tr>
</table>
 




## -remarks



None.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-setiunknownvalue">IPortableDeviceValues::SetIUnknownValue</a>
 

 

