---
UID: NF:fltkernel.FltRetrieveFileInfoOnCreateCompletionEx
title: FltRetrieveFileInfoOnCreateCompletionEx function
author: windows-driver-content
description: A minifilter calls FltRetrieveFileInfoOnCreateCompletionEx to query file information upon file creation completion.
tech.root: ifsk
ms.assetid: b0a99090-40a5-4e40-8ddb-54816ba789b5
ms.author: windowsdriverdev
ms.date: 1/11/2019
ms.topic: function
ms.keywords: FltRetrieveFileInfoOnCreateCompletionEx, FltRetrieveFileInfoOnCreateCompletion
req.header: fltkernel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - 
api_location: 
 - 
api_name: 
 - FltRetrieveFileInfoOnCreateCompletionEx
product: 
 - Windows
targetos: Windows

ms.custom: 19H1
---

# FltRetrieveFileInfoOnCreateCompletionEx function


## -description

A minifilter calls **FltRetrieveFileInfoOnCreateCompletionEx** to query file information upon file creation completion.

## -parameters

### -param Filter

Opaque filter pointer that uniquely identifies the minifilter driver. It is returned by [FltRegisterFilter](nf-fltkernel-fltregisterfilter.md), and remains constant as long as the minifilter driver is loaded.

### -param Data

Pointer to the [FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md) callback data representing the I/O operation.

### -param InfoClass

Flag that indicates the type of information to return. Note that flags cannot be combined. ???ARE THERE ANY PUBLIC FLAGS TO DOCUMENT????

### -param Size

Pointer to a ULONG that receives the size of the file information buffer.

### -param RetInfoBuffer

Receives a pointer to a buffer with the requested file information. If the file system is able to process the request but can't find the requested file information, this parameter is set to NULL.

## -returns
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
The file system successfully returned the requested file information.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The file system processed the request, but the requested information was not present on the file, or the file system does not recognize the information request in <i>InfoClass</i> ???SHOULD CODE BE AMENDED TO RETURN STATUS_NOT_SUPPORTED FOR THIS LATTER CASE???. The caller should not use traditional file system APIs????????? to request the information. 
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The file system was unable to retrieve the requested information. This error occurs when the file system doesn't support the information request or  associated ECP, or because [FltRequestFileInfoOnCreateCompletion](nf-fltkernel-_fltrequestfileinfooncreatecompletion.md) wasn't called during file pre-creation. The caller should instead use traditional file system APIs to retry requesting the information. 
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The file system received an error while trying to retrieve the requested information. The caller can try requesting the information by way of normal file system APIs ???WHICH ONES???, but that will likely fail. 
</td>
</tr>

</table>

## -remarks
A minifilter must call <b>FltRequestFileInfoOnCreateCompletionEx</b> during file pre-creation to specify which file information the file system should track.

## -see-also

[ECP_LIST](https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff540148(v=vs.85))

[FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md)

[FltRequestFileInfoOnCreateCompletion](nf-fltkernel-_fltrequestfileinfooncreatecompletion.md)
