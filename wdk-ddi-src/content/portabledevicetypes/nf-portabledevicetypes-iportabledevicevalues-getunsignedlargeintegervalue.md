---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetUnsignedLargeIntegerValue
title: IPortableDeviceValues::GetUnsignedLargeIntegerValue (portabledevicetypes.h)
description: Retrieves a ULONGLONG value (type VT_UI8) that is specified by a key.
old-location: wpddk\iportabledevicevalues_getunsignedlargeintegervalue.htm
tech.root: wpd_dk
ms.assetid: d7917c06-948e-47bf-bd58-9529e3bf7b7d
ms.date: 02/15/2018
ms.keywords: GetUnsignedLargeIntegerValue, GetUnsignedLargeIntegerValue method, GetUnsignedLargeIntegerValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetUnsignedLargeIntegerValue method, IPortableDeviceValues.GetUnsignedLargeIntegerValue, IPortableDeviceValues::GetUnsignedLargeIntegerValue, IPortableDeviceValuesGetUnsignedLargeIntegerValue, portabledevicetypes/IPortableDeviceValues::GetUnsignedLargeIntegerValue, wpddk.iportabledevicevalues_getunsignedlargeintegervalue
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
- IPortableDeviceValues.GetUnsignedLargeIntegerValue
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::GetUnsignedLargeIntegerValue


## -description



Retrieves a <b>ULONGLONG</b> value (type VT_UI8) that is specified by a key.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> key that specifies the item to retrieve.


### -param pValue [out]

Pointer to the retrieved <b>ULONGLONG</b> value.


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
The property specified by <i>key</i> is not a <b>ULONGLONG</b> type.

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



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-setunsignedlargeintegervalue">IPortableDeviceValues::SetUnsignedLargeIntegerValue</a>
 

 

