---
UID: NF:wdfiotarget.WdfIoTargetFormatRequestForIoctl
title: WdfIoTargetFormatRequestForIoctl function (wdfiotarget.h)
description: The WdfIoTargetFormatRequestForIoctl method builds a device control request for an I/O target but does not send the request.
old-location: wdf\wdfiotargetformatrequestforioctl.htm
tech.root: wdf
ms.assetid: 673f53e8-67ce-481d-be1b-ea4146b9776a
ms.date: 02/26/2018
ms.keywords: DFIOTargetRef_065d8ea7-7be0-41c4-be6b-648606404139.xml, WdfIoTargetFormatRequestForIoctl, WdfIoTargetFormatRequestForIoctl method, kmdf.wdfiotargetformatrequestforioctl, wdf.wdfiotargetformatrequestforioctl, wdfiotarget/WdfIoTargetFormatRequestForIoctl
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, RequestFormattedValid, RequestSendAndForgetNoFormatting, RequestSendAndForgetNoFormatting2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfIoTargetFormatRequestForIoctl
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetFormatRequestForIoctl function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoTargetFormatRequestForIoctl</b> method builds a device control request for an I/O target but does not send the request.


## -parameters




### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget">WdfDeviceGetIoTarget</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>, or from a method that a specialized I/O target supplies.


### -param Request [in]

A handle to a framework request object. For more information, see the following Remarks section.


### -param IoctlCode [in]

An I/O control code (IOCTL) that the I/O target supports. 


### -param InputBuffer [in, optional]

A handle to a framework memory object. This object represents a buffer that contains data that will be sent to the I/O target. For more information, see the following Remarks section.


### -param InputBufferOffset [in, optional]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/ns-wdfmemory-_wdfmemory_offset">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. The framework uses these values to determine the beginning address and length, within the input buffer, for the data transfer. If this pointer is <b>NULL</b>, the data transfer begins at the beginning of the input buffer, and the transfer size is the buffer size.


### -param OutputBuffer [in, optional]

A handle to a framework memory object. This object represents a buffer that will receive data from the I/O target. For more information, see the following Remarks section.


### -param OutputBufferOffset [in, optional]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/ns-wdfmemory-_wdfmemory_offset">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. The framework uses these values to determine the beginning address and length, within the output buffer, for the data transfer. If this pointer is <b>NULL</b>, the data transfer begins at the beginning of the output buffer, and the transfer size is the buffer size.


## -returns



<b>WdfIoTargetFormatRequestForIoctl</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The transfer length was larger than the buffer length, or the I/O request was already queued to an I/O target.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The framework could not allocate system resources (typically memory).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REQUEST_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The I/O request packet (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_irp">IRP</a>) that the <i>Request</i> parameter represents does not provide enough <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a> structures to allow the driver to forward the request.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Use the <b>WdfIoTargetFormatRequestForIoctl</b> method, followed by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a> method, to send device control requests either synchronously or asynchronously. Alternatively, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a> method to send device control requests synchronously. 

For more information about device control requests, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-i-o-control-codes">Using I/O Control Codes</a>.

You can forward a device control request that your driver received in an I/O queue, or you can create and send a new request. In either case, the framework requires a request object and some buffer space.

To forward a device control request that your driver received in an I/O queue:

<ol>
<li>
Specify the received request's handle for the <b>WdfIoTargetFormatRequestForIoctl</b> method's <i>Request</i> parameter.

</li>
<li>
Use the received request's input buffer for the <b>WdfIoTargetFormatRequestForIoctl</b> method's <i>InputBuffer</i> parameter. 

The driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a> to obtain a handle to a framework memory object that represents the request's input buffer, and it must use that handle as the value for <i>InputBuffer</i>.

</li>
<li>
Use the received request's output buffer for the <b>WdfIoTargetFormatRequestForIoctl</b> method's <i>OutputBuffer</i> parameter. 

The driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputmemory">WdfRequestRetrieveOutputMemory</a> to obtain a handle to the request's output buffer, and it must use that handle as the value for <i>OutputBuffer</i>.

</li>
</ol>
For more information about forwarding an I/O request, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.

Drivers often divide received I/O requests into smaller requests that they send to an I/O target, so your driver might create new requests.

To create a new I/O request:

<ol>
<li>
Create a new request object and supply its handle for the <b>WdfIoTargetFormatRequestForIoctl</b> method's <i>Request</i> parameter.

Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcreate">WdfRequestCreate</a> to preallocate one or more request objects. You can reuse these request objects by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestreuse">WdfRequestReuse</a>. Your driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function can preallocate request objects for a device.

</li>
<li>
Provide buffer space, and supply the buffer's handle for the <b>WdfIoTargetFormatRequestForIoctl</b> method's <i>InputBuffer</i> and <i>OutputBuffer</i> parameters.

Your driver must specify this buffer space as WDFMEMORY handles to framework-managed memory. Your driver can do either of the following:

<ul>
<li> Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/nf-wdfmemory-wdfmemorycreate">WdfMemoryCreate</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/nf-wdfmemory-wdfmemorycreatepreallocated">WdfMemoryCreatePreallocated</a> to create a new memory buffer, if you want the driver to pass a new buffer to the I/O target.  </li>
<li> Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputmemory">WdfRequestRetrieveOutputMemory</a> to obtain a handle to the memory object that represents a received I/O request's buffer, if you want the driver to pass that buffer's contents to the I/O target. </li>
</ul>
Note that if your driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputmemory">WdfRequestRetrieveOutputMemory</a> and passes the memory handle to <b>WdfIoTargetFormatRequestForIoctl</b>, the driver must not complete the received I/O request until after the driver deletes, reuses, or reformats the new, driver-created request object. (<b>WdfIoTargetFormatRequestForIoctl</b> increments the memory object's reference count. Deleting, reusing, or reformatting a request object decrements the memory object's reference count.)

</li>
</ol>
After a driver calls <b>WdfIoTargetFormatRequestForIoctl</b> to format a device control request, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a> to send the request (either synchronously or asynchronously) to an I/O target.

Multiple calls to <b>WdfIoTargetFormatRequestForIoctl</b> that use the same request do not cause additional resource allocations. Therefore, to reduce the chance that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcreate">WdfRequestCreate</a> will return STATUS_INSUFFICIENT_RESOURCES, your driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function can call <b>WdfRequestCreate</b> to preallocate one or more request objects for a device. The driver can subsequently reuse (call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestreuse">WdfRequestReuse</a>), reformat (call <b>WdfIoTargetFormatRequestForIoctl</b>), and resend (call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a>) each request object without risking a STATUS_INSUFFICIENT_RESOURCES return value from a later call to <b>WdfRequestCreate</b>. All subsequent calls to <b>WdfIoTargetFormatRequestForIoctl</b> for the reused request object will return STATUS_SUCCESS, if parameter values do not change. (If the driver does not call the same request-formatting method each time, additional resources might be allocated. Additionally, if the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/defining-i-o-control-codes">I/O control code</a> specifies a transfer type of METHOD_BUFFERED, the framework must allocate a system buffer for each request and that allocation could fail because of insufficient memory resources.)

For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about <b>WdfIoTargetFormatRequestForIoctl</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sending-i-o-requests-to-general-i-o-targets">Sending I/O Requests to General I/O Targets</a>.

For more information about I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets">Using I/O Targets</a>.


#### Examples

The following code reuses a preallocated request object and preallocated memory objects. The example assigns input and output buffers to the memory objects, formats the request object, registers a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a> callback function, and sends the request to an I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
NICSendOidRequestToTargetAsync(
    IN WDFIOTARGET  IoTarget,
    IN WDFREQUEST  Request,
    IN PFILE_OBJECT  FileObject,
    IN ULONG  IoctlControlCode,
    IN OUT PVOID  InputBuffer,
    IN ULONG  InputBufferLength,
    IN OUT PVOID  OutputBuffer,
    IN ULONG  OutputBufferLength,
    OUT PULONG  BytesReadOrWritten
    )
{
    NTSTATUS  status;
    PREQUEST_CONTEXT  reqContext;
    WDF_REQUEST_REUSE_PARAMS  params;
    WDFMEMORY  inputMem, outputMem;
 
    WDF_REQUEST_REUSE_PARAMS_INIT(
                                  &params, 
                                  WDF_REQUEST_REUSE_NO_FLAGS, 
                                  STATUS_SUCCESS
                                  );
    status = WdfRequestReuse(Request, &params);
    if (!NT_SUCCESS(status)){
        return status;
    }

    reqContext = GetRequestContext(Request);

    inputMem = outputMem = NULL;
 
    if (InputBuffer != NULL) {
        status = WdfMemoryAssignBuffer(
                                       reqContext->InputMemory,
                                       InputBuffer, 
                                       InputBufferLength
                                       );
        if (!NT_SUCCESS(status)) {
             return status;
        }
        inputMem = reqContext->InputMemory;
    }

    if (OutputBuffer != NULL) {
        status = WdfMemoryAssignBuffer(
                                       reqContext->OutputMemory,
                                       OutputBuffer, 
                                       OutputBufferLength
                                       );
        if (!NT_SUCCESS(status)) {
            return status;
        }
        outputMem = reqContext->OutputMemory;
    }

    status = WdfIoTargetFormatRequestForIoctl(
                                              IoTarget,
                                              Request,
                                              IoctlControlCode,
                                              inputMem,
                                              NULL,
                                              outputMem,
                                              NULL
                                              );
    if (!NT_SUCCESS(status)) {
        return status;
    }

    WdfRequestSetCompletionRoutine(
                                   Request,
                                   NICSendOidRequestToTargetAsyncCompletionRoutine,
                                   BytesReadOrWritten
                                   );

    if (WdfRequestSend(
                       Request,
                       IoTarget,
                       WDF_NO_SEND_OPTIONS
                       ) == FALSE) {
        status = WdfRequestGetStatus(Request);
    }
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/ns-wdfmemory-_wdfmemory_offset">WDFMEMORY_OFFSET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget">WdfDeviceGetIoTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetformatrequestforinternalioctl">WdfIoTargetFormatRequestForInternalIoctl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfiotarget/nf-wdfiotarget-wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/nf-wdfmemory-wdfmemorycreate">WdfMemoryCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/nf-wdfmemory-wdfmemorycreatepreallocated">WdfMemoryCreatePreallocated</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestcreate">WdfRequestCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputmemory">WdfRequestRetrieveOutputMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestreuse">WdfRequestReuse</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a>
 

 

