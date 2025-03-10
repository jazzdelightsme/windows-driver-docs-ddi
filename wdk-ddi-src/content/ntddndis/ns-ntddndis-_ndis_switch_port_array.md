---
UID: NS:ntddndis._NDIS_SWITCH_PORT_ARRAY
title: _NDIS_SWITCH_PORT_ARRAY (ntddndis.h)
description: The NDIS_SWITCH_PORT_ARRAY structure specifies an array of port configuration parameters. Each element in the array specifies the parameters for a Hyper-V extensible switch port. Each element is formatted as an NDIS_SWITCH_PORT_PARAMETERS structure.
old-location: netvista\ndis_switch_port_array.htm
tech.root: netvista
ms.assetid: f753694a-f31b-4bb5-8388-bc20d12cb423
ms.date: 05/02/2018
ms.keywords: "*PNDIS_SWITCH_PORT_ARRAY, NDIS_SWITCH_PORT_ARRAY, NDIS_SWITCH_PORT_ARRAY structure [Network Drivers Starting with Windows Vista], PNDIS_SWITCH_PORT_ARRAY, PNDIS_SWITCH_PORT_ARRAY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SWITCH_PORT_ARRAY, netvista.ndis_switch_port_array, ntddndis/NDIS_SWITCH_PORT_ARRAY, ntddndis/PNDIS_SWITCH_PORT_ARRAY"
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h, Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
- HeaderDef
api_location:
- ntddndis.h
api_name:
- NDIS_SWITCH_PORT_ARRAY
product:
- Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_ARRAY, *PNDIS_SWITCH_PORT_ARRAY
---

# _NDIS_SWITCH_PORT_ARRAY structure


## -description


The <b>NDIS_SWITCH_PORT_ARRAY</b> structure specifies an array of port configuration parameters. Each element in the array specifies the parameters for a Hyper-V extensible switch port. Each element is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETERS</a> structure.


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PORT_ARRAY</b> structure. This member is formatted as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PORT_ARRAY</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value: 





#### NDIS_SWITCH_PORT_ARRAY_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PORT_ARRAY_REVISION_1.


### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.




### -field FirstElementOffset

A USHORT value that specifies the offset, in bytes, to the first element in an array of elements that follow this structure. The offset is measured from the start of the <b>NDIS_SWITCH_PORT_ARRAY</b> structure up to the beginning of the first element. Each element in the array is an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETERS</a> structure.



<div class="alert"><b>Note</b>  If <b>NumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>

### -field NumElements

A ULONG value that specifies the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETERS</a> elements that follow the <b>NDIS_SWITCH_PORT_ARRAY</b> structure. 


### -field ElementSize

A ULONG value that specifies the size, in bytes, of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETERS</a> elements that follows the <b>NDIS_SWITCH_PORT_ARRAY</b> structure. 


## -remarks



The <b>NDIS_SWITCH_PORT_ARRAY</b> structure is returned in OID query requests of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-array">OID_SWITCH_PORT_ARRAY</a>. An array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETERS</a> structures follow the <b>NDIS_SWITCH_PORT_ARRAY</b> structure in the information buffer that is associated with these OID query requests. The <b>InformationBuffer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure contains a pointer to this information buffer.

Extensible switch extensions can access individual <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETERS</a> elements inside an <b>NDIS_SWITCH_PORT_ARRAY</b> structure by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-switch-port-at-array-index">NDIS_SWITCH_PORT_AT_ARRAY_INDEX</a> macro.




## -see-also




<b></b>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-switch-port-at-array-index">NDIS_SWITCH_PORT_AT_ARRAY_INDEX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddndis/ns-ntddndis-_ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-switch-port-array">OID_SWITCH_PORT_ARRAY</a>
 

 

