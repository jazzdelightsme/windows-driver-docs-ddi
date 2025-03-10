---
UID: NC:fwpsk.FWPS_CALLOUT_CLASSIFY_FN0
title: FWPS_CALLOUT_CLASSIFY_FN0 (fwpsk.h)
description: The filter engine calls a callout's classifyFn0 callout function whenever there is data to be processed by the callout.Note  classifyFn0 is the specific version of classifyFn used in Windows Vista and later.
old-location: netvista\classifyfn0.htm
tech.root: netvista
ms.assetid: e8423c27-d3eb-4bef-a835-37fae0e2b68c
ms.date: 05/02/2018
ms.keywords: FWPS_CALLOUT_CLASSIFY_FN0, FWPS_CALLOUT_CLASSIFY_FN0 callback, classifyFn0, classifyFn0 callback function [Network Drivers Starting with Windows Vista], fwpsk/classifyFn0, netvista.classifyfn0, wfp_ref_2_funct_4_callout_402ad3d3-74db-4024-8dcb-50459ab669c7.xml
ms.topic: callback
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Fwpsk.h
api_name:
- classifyFn0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FWPS_CALLOUT_CLASSIFY_FN0 callback function


## -description


The filter engine calls a callout's 
  <i>classifyFn0</i> callout function whenever there is data to be processed by the callout.
<div class="alert"><b>Note</b>  <i>classifyFn0</i> is the specific version of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_netvista/">classifyFn</a> used in Windows Vista and later. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 8, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn2">classifyFn2</a> is available. For Windows 7, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn1">classifyFn1</a> is available.</div><div> </div>

## -parameters




### -param *inFixedValues [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_incoming_values0_">FWPS_INCOMING_VALUES0</a> structure. This
     structure contains the values for each of the data fields at the layer being filtered.


### -param *inMetaValues [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">
     FWPS_INCOMING_METADATA_VALUES0</a> structure. This structure contains the values for each of the
     metadata fields at the layer being filtered.


### -param *layerData [in, out]

A pointer to a structure that describes the raw data at the layer being filtered. This parameter
     might be <b>NULL</b>, depending on the layer being filtered and the conditions under which the 
     <i>classifyFn0</i> callout function is called. For the stream layer, this parameter points to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_stream_callout_io_packet0_">
     FWPS_STREAM_CALLOUT_IO_PACKET0</a> structure. For all of the other layers, this parameter points to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure if it is not
     <b>NULL</b>.


### -param *filter [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_filter0_">FWPS_FILTER0</a> structure. This structure
     describes the filter that specifies the callout for the filter's action.


### -param flowContext [in]

A UINT64-typed variable that contains the context associated with the data flow. If no context is
     associated with the data flow, then this parameter is zero. If the callout is added to the filter engine
     at a filtering layer that does not support data flows, the 
     <i>classifyFn0</i> callout function should ignore this parameter.


### -param *classifyOut [in, out]

A pointer to an 
     <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a> structure that
     receives any data that the 
     <i>classifyFn0</i> callout function returns to the caller.


## -returns



None




## -remarks



A callout driver registers a callout's callout functions with the filter engine by calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutregister0">FwpsCalloutRegister0</a> function.

The filter engine calls a callout's 
    <i>classifyFn0</i> callout function with data to be processed whenever all of the test conditions are true
    for a filter in the filter engine that specifies the callout for the filter's action.

A callout's 
    <i>classifyFn0</i> callout function should clear the FWPS_RIGHT_ACTION_WRITE flag in the 
    <b>rights</b> member of the 
    <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a> structure in any of
    the following situations:

<ul>
<li>
When the 
      <i>classifyFn0</i> callout function sets the 
      <b>actionType</b> member of the 
      <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a> structure to
      FWP_ACTION_BLOCK.

</li>
<li>
When the 
      <i>classifyFn0</i> callout function sets the 
      <b>actionType</b> member of the 
      <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a> structure to
      FWP_ACTION_PERMIT and the FWPS_FILTER_FLAG_CLEAR_ACTION_RIGHT flag is set in the 
      <b>Flags</b> member of the 
      <a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_filter0_">FWPS_FILTER0</a> structure.

</li>
<li>
When a callout has indicated that it intends to modify the clone net buffer list by setting the 
      <i>intendToModify</i> parameter to <b>TRUE</b> in a call to the 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsreferencenetbufferlist0">FwpsReferenceNetBufferList0</a> function.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/associating-context-with-a-data-flow">Associating Context with a Data Flow</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_netvista/">Callout Driver Callout Functions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/data-logging">Data Logging</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_callout0_">FWPS_CALLOUT0</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_classify_out0_">FWPS_CLASSIFY_OUT0</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_filter0_">FWPS_FILTER0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">
   FWPS_INCOMING_METADATA_VALUES0</a>



<a href="https://docs.microsoft.com/windows/desktop/api/fwpstypes/ns-fwpstypes-fwps_incoming_values0_">FWPS_INCOMING_VALUES0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutregister0">FwpsCalloutRegister0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutregister1">FwpsCalloutRegister1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsreferencenetbufferlist0">FwpsReferenceNetBufferList0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/packet-modification-examples">Packet Modification Examples</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/registering-callouts-with-the-filter-engine">Registering Callouts with the Filter Engine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-a-callout-for-deep-inspection-of-stream-data">Using a Callout
    for Deep Inspection of Stream Data</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/using-a-callout-for-deep-inspection">Using a Callout for Deep Inspection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_netvista/">classifyFn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn1">classifyFn1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_classify_fn2">classifyFn2</a>
 

 

