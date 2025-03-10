---
UID: NN:dbgeng.IDebugEventCallbacks
title: IDebugEventCallbacks (dbgeng.h)
description: IDebugEventCallbacks interface
old-location: debugger\idebugeventcallbacks.htm
tech.root: debugger
ms.assetid: f5e51d0e-0967-4e35-b24b-4bd99c975569
ms.date: 05/03/2018
ms.keywords: ComCallbacks_72745555-ec34-41fa-9305-cf23357bcd17.xml, IDebugEventCallbacks, IDebugEventCallbacks interface [Windows Debugging], IDebugEventCallbacks interface [Windows Debugging],described, dbgeng/IDebugEventCallbacks, debugger.idebugeventcallbacks
ms.topic: interface
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
- dbgeng.h
api_name:
- IDebugEventCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugEventCallbacks interface


## -description




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugEventCallbacks</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugEventCallbacks</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IDebugEventCallbacks</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-breakpoint">Breakpoint</a>
</td>
<td align="left" width="63%">
 This method is called by the engine when the target issues a breakpoint exception.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-changedebuggeestate">ChangeDebuggeeState</a>
</td>
<td align="left" width="63%">
This method is called by the engine when it makes or detects changes to the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-changeenginestate">ChangeEngineState</a>
</td>
<td align="left" width="63%">
This method is called by the engine when its state has changed.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-changesymbolstate">ChangeSymbolState</a>
</td>
<td align="left" width="63%">
This method is called by the engine when the symbol state changes.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-createprocess">CreateProcess</a>
</td>
<td align="left" width="63%">
This method is called by the engine when a create-process debugging event occurs in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-createthread">CreateThread</a>
</td>
<td align="left" width="63%">
This method is called by the engine when a create-thread debugging event occurs in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-exception">Exception</a>
</td>
<td align="left" width="63%">
This method is called by the engine when an exception debugging event occurs in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-exitprocess">ExitProcess</a>
</td>
<td align="left" width="63%">
This method is called by the engine when an exit-process debugging event occurs in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-exitthread">ExitThread</a>
</td>
<td align="left" width="63%">
This method is called by the engine when an exit-thread debugging event occurs in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-getinterestmask">GetInterestMask</a>
</td>
<td align="left" width="63%">
This method is called to determine which events the <b>IDebugEventCallbacks</b> object is interested in.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-loadmodule">LoadModule</a>
</td>
<td align="left" width="63%">
This method is called by the engine when a module-load debugging event occurs in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-sessionstatus">SessionStatus</a>
</td>
<td align="left" width="63%">
This method is called by the engine when a change occurs in the debugger session.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-systemerror">SystemError</a>
</td>
<td align="left" width="63%">
This method is called by the engine when a system error occurs in the target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-unloadmodule">UnloadModule</a>
</td>
<td align="left" width="63%">
This method is called by the engine when a module-unload debugging event occurs in the target.

</td>
</tr>
</table> 


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugeventcallbackswide">IDebugEventCallbacksWide</a> interface includes Unicode versions of these methods; the Unicode methods share the same names as those used by the methods in <b>IDebugEventCallbacks</b>.



The following <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/events">events</a> are generated by the target.

<table>
<tr>
<th>Flag</th>
<th>IDebugEventCallbacksMethod </th>
<th>Event Description</th>
</tr>
<tr>
<td>
DEBUG_EVENT_BREAKPOINT

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-breakpoint">Breakpoint</a>


</td>
<td>
A breakpoint exception occurred in the target.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_EXCEPTION

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-exception">Exception</a>


</td>
<td>
An exception debugging event occurred in the target.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_CREATE_THREAD

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-createthread">CreateThread</a>


</td>
<td>
A create-thread debugging event occurred in the target.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_EXIT_THREAD

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-exitthread">ExitThread</a>


</td>
<td>
An exit-thread debugging event occurred in the target.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_CREATE_PROCESS

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugclient5-createprocess">CreateProcess</a>


</td>
<td>
A create-process debugging event occurred in the target.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_EXIT_PROCESS

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-exitprocess">ExitProcess</a>


</td>
<td>
An exit-process debugging event occurred in the target.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_LOAD_MODULE

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-loadmodule">LoadModule</a>


</td>
<td>
A module-load debugging event occurred in the target.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_UNLOAD_MODULE

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-unloadmodule">UnloadModule</a>


</td>
<td>
A module-unload debugging event occurred in the target.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_SYSTEM_ERROR

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-systemerror">SystemError</a>


</td>
<td>
A system error occurred in the target.

</td>
</tr>
</table>
 

The following events are generated by the debugger engine.

<table>
<tr>
<th>Flag</th>
<th>IDebugEventCallbacksMethod </th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_EVENT_SESSION_STATUS

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-sessionstatus">SessionStatus</a>


</td>
<td>
A change has occurred in the session status.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_CHANGE_DEBUGGEE_STATE

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-changedebuggeestate">ChangeDebuggeeState</a>


</td>
<td>
The engine has made or detected a change in the target status.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_CHANGE_ENGINE_STATE

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-changeenginestate">ChangeEngineState</a>


</td>
<td>
The engine state has changed.

</td>
</tr>
<tr>
<td>
DEBUG_EVENT_CHANGE_SYMBOL_STATE

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nf-dbgeng-idebugeventcallbacks-changesymbolstate">ChangeSymbolState</a>


</td>
<td>
The symbol state has changed.

</td>
</tr>
</table>
 



