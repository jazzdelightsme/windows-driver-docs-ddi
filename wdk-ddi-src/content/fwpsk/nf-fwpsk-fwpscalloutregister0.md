---
UID: NF:fwpsk.FwpsCalloutRegister0
title: FwpsCalloutRegister0 function (fwpsk.h)
description: The FwpsCalloutRegister0 function registers a callout with the filter engine.Note  FwpsCalloutRegister0 is the specific version of FwpsCalloutRegister used in Windows Vista and later.
old-location: netvista\fwpscalloutregister0.htm
tech.root: netvista
ms.assetid: 1f003775-4b93-44cd-8c58-18e0e3fb5656
ms.date: 05/02/2018
ms.keywords: FwpsCalloutRegister0, FwpsCalloutRegister0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsCalloutRegister0, netvista.fwpscalloutregister0, wfp_ref_2_funct_3_fwps_C_a1902e8d-fa04-4d2c-ab39-04d313d01833.xml
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Fwpkclnt.lib
- Fwpkclnt.dll
api_name:
- FwpsCalloutRegister0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsCalloutRegister0 function


## -description


The 
  <b>FwpsCalloutRegister0</b> function registers a callout with the filter engine.
<div class="alert"><b>Note</b>  <b>FwpsCalloutRegister0</b> is the specific version of <b>FwpsCalloutRegister</b> used in Windows Vista and later. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 8, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutregister2">FwpsCalloutRegister2</a> is available. For Windows 7, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutregister1">FwpsCalloutRegister1</a> is available.</div><div> </div>

## -parameters




### -param deviceObject [in, out]

A pointer to a device object that was previously created by the callout driver. For more
     information about how a callout driver creates a device object, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-a-device-object">Creating a Device Object</a>.


### -param callout [in]

A pointer to a constant 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_callout0_">FWPS_CALLOUT0</a> structure that contains the
     data that is required to register the callout with the filter engine.


### -param calloutId [out, optional]

A pointer to a UINT32-typed variable that receives a run-time identifier that identifies the
     callout in the filter engine. The callout driver passes this identifier to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutunregisterbyid0">FwpsCalloutUnregisterById0</a> function when unregistering the callout from the filter engine. If a
     callout driver is filtering a data flow, it also passes this identifier to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsflowassociatecontext0">FwpsFlowAssociateContext0</a> and 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsflowremovecontext0">FwpsFlowRemoveContext0</a> functions.
     If a callout driver injects data into data streams, it also passes this identifier to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsstreaminjectasync0">FwpsStreamInjectAsync0</a> function. 
     The filter engine also passes this
     identifier to the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_flow_delete_notify_fn0">flowDeleteFn</a> callout function. This
     parameter is optional and can be <b>NULL</b>.


## -returns



The 
     <b>FwpsCalloutRegister0</b> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The callout was successfully registered with the filter engine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_ALREADY_EXISTS</b></dt>
</dl>
</td>
<td width="60%">
The callout could not be registered with the filter engine. A callout is already registered in
       the filter engine with an identifier identical to the GUID specified in the 
       <b>calloutKey</b> member of the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_callout0_">FWPS_CALLOUT0</a> structure pointed to by the 
       <i>callout</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>
 




## -remarks



A callout driver calls the 
    <b>FwpsCalloutRegister0</b> function to register a callout with the filter engine. A callout driver can
    register a callout with the filter engine at any time, even if the filter engine is not currently
    running.

A callout and filters that specify the callout for the filter's action can be added to the filter
    engine before a callout driver registers the callout with the filter engine. In this situation, filters
    with an action type of <b>FWP_ACTION_CALLOUT_TERMINATING</b> or <b>FWP_ACTION_CALLOUT_UNKNOWN</b> are treated as
    <b>FWP_ACTION_BLOCK</b>, and filters with an action type of <b>FWP_ACTION_CALLOUT_INSPECTION</b> are ignored until the
    callout is registered with the filter engine.

A callout driver unregisters a callout from the filter engine by calling either the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutunregisterbyid0">
    FwpsCalloutUnregisterById0</a> function or the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutunregisterbykey0">
    FwpsCalloutUnregisterByKey0</a> function. A callout driver cannot be unloaded until all of the callouts
    that were previously registered with the filter engine have been successfully unregistered.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-a-device-object">Creating a Device Object</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_callout0_">FWPS_CALLOUT0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutregister1">FwpsCalloutRegister1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutregister2">FwpsCalloutRegister2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutunregisterbyid0">FwpsCalloutUnregisterById0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpscalloutunregisterbykey0">FwpsCalloutUnregisterByKey0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsflowassociatecontext0">FwpsFlowAssociateContext0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsflowremovecontext0">FwpsFlowRemoveContext0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsstreaminjectasync0">FwpsStreamInjectAsync0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-iocreatedevice">IoCreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/types-of-callouts">Types of Callouts</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_callout_flow_delete_notify_fn0">flowDeleteFn</a>
 

 

