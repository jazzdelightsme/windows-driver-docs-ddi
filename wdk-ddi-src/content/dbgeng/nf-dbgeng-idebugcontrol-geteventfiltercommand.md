---
UID: NF:dbgeng.IDebugControl.GetEventFilterCommand
title: IDebugControl::GetEventFilterCommand (dbgeng.h)
description: The GetEventFilterCommand method returns the debugger command that the engine will execute when a specified event occurs.
old-location: debugger\geteventfiltercommand.htm
tech.root: debugger
ms.assetid: ea88d1de-70c1-424a-a3a0-cce46cc3fe39
ms.date: 05/03/2018
ms.keywords: GetEventFilterCommand, GetEventFilterCommand method [Windows Debugging], GetEventFilterCommand method [Windows Debugging],IDebugControl interface, GetEventFilterCommand method [Windows Debugging],IDebugControl2 interface, GetEventFilterCommand method [Windows Debugging],IDebugControl3 interface, IDebugControl interface [Windows Debugging],GetEventFilterCommand method, IDebugControl.GetEventFilterCommand, IDebugControl2 interface [Windows Debugging],GetEventFilterCommand method, IDebugControl2::GetEventFilterCommand, IDebugControl3 interface [Windows Debugging],GetEventFilterCommand method, IDebugControl3::GetEventFilterCommand, IDebugControl::GetEventFilterCommand, IDebugControl_a0acf45f-8741-48a0-9eb0-f8a9aa55c476.xml, dbgeng/IDebugControl2::GetEventFilterCommand, dbgeng/IDebugControl3::GetEventFilterCommand, dbgeng/IDebugControl::GetEventFilterCommand, debugger.geteventfiltercommand
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
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
- dbgeng.h
api_name:
- IDebugControl.GetEventFilterCommand
- IDebugControl2.GetEventFilterCommand
- IDebugControl3.GetEventFilterCommand
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl::GetEventFilterCommand


## -description


The <b>GetEventFilterCommand</b>  method returns the debugger command that the engine will execute when a specified event occurs.


## -parameters




### -param Index [in]

Specifies the index of the event filter.  <i>Index</i> can take any value between zero and one less than the total number of event filters returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getnumbereventfilters">GetNumberEventFilters</a> (inclusive).  For more information about the index of the filters, see Index and Exception Code.


### -param Buffer [out, optional]

Receives the debugger command that the engine will execute when the event occurs.


### -param BufferSize [in]

Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies.


### -param CommandSize [out, optional]

Receives the size in characters of the command.  If <i>CommandSize</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return error values.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/hresult-values">Return Values</a> for more details.

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
The method was successful.

</td>
</tr>
</table>
 




## -remarks



For more information about event filters, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/event-filters">Event Filters</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-getexceptionfiltersecondcommand">GetExceptionFilterSecondCommand</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol">IDebugControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol2">IDebugControl2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugcontrol3">IDebugControl3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugcontrol3-seteventfiltercommand">SetEventFilterCommand</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/sx--sxd--sxe--sxi--sxn--sxr--sx---set-exceptions-">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
 

 

