---
UID: NF:prcomoem.IPrintOemUI2.DocumentEvent
title: IPrintOemUI2::DocumentEvent (prcomoem.h)
description: The IPrintOemUI2::DocumentEvent method allows a UI plug-in to replace the core driver UI module's default implementation of the DrvDocumentEvent DDI.
old-location: print\iprintoemui2_documentevent.htm
tech.root: print
ms.assetid: c98d1510-7db8-4fd6-a95f-1906f553d1c5
ms.date: 04/20/2018
ms.keywords: DocumentEvent, DocumentEvent method [Print Devices], DocumentEvent method [Print Devices],IPrintOemUI2 interface, IPrintOemUI2 interface [Print Devices],DocumentEvent method, IPrintOemUI2.DocumentEvent, IPrintOemUI2::DocumentEvent, prcomoem/IPrintOemUI2::DocumentEvent, print.iprintoemui2_documentevent, print_unidrv-pscript_ui_03e403e4-7b60-413c-a8d2-025b3124f427.xml
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
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
- prcomoem.h
api_name:
- IPrintOemUI2.DocumentEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUI2::DocumentEvent


## -description


The <code>IPrintOemUI2::DocumentEvent</code> method allows a UI plug-in to replace the core driver UI module's default implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/nf-winddiui-drvdocumentevent">DrvDocumentEvent</a> DDI.


## -parameters




### -param hPrinter

Caller-supplied printer handle.


### -param hdc

Caller-supplied device context handle, generated by a <b>CreateDC</b> call. This is zero if <i>iEsc</i> is DOCUMENTEVENT_CREATEDCPRE.


### -param iEsc

Caller-supplied escape code identifying the event to be handled. This parameter can be one of the following integer constants:

<table>
<tr>
<th>Escape Code</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DOCUMENTEVENT_ABORTDOC

</td>
<td>
GDI is about to process a call to its <b>AbortDoc</b> function.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_CREATEDCPOST

</td>
<td>
GDI has just processed a call to its <b>CreateDC</b> or <b>CreateIC</b> function.

This escape code should not be used unless there has been a previous call to <b>DrvDocumentEvent</b> with <i>iEsc</i> set to DOCUMENTEVENT_CREATEDCPRE.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_CREATEDCPRE

</td>
<td>
GDI is about to process a call to its <b>CreateDC</b> or <b>CreateIC</b> function.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_DELETEDC

</td>
<td>
GDI is about to process a call to its <b>DeleteDC</b> function.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_ENDDOCPOST

</td>
<td>
GDI has just processed a call to its <b>EndDoc</b> function.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_ENDDOCPRE 

or

DOCUMENTEVENT_ENDDOC

</td>
<td>
GDI is about to process a call to its <b>EndDoc</b> function.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_ENDPAGE

</td>
<td>
GDI is about to process a call to its <b>EndPage</b> function.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_ESCAPE

</td>
<td>
GDI is about to process a call to its <b>ExtEscape</b> function.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_QUERYFILTER

</td>
<td>
The DOCUMENTEVENT_QUERYFILTER event represents an opportunity for the spooler to query the driver for a list of the DOCUMENTEVENT_<i>XXX</i> events to which the driver will respond. This event is issued just prior to a call to <b>DrvDocumentEvent</b> that passes the DOCUMENTEVENT_CREATEDCPRE event.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_RESETDCPOST

</td>
<td>
GDI has just processed a call to its <b>ResetDC</b> function.

This escape code should not be used unless there has been a previous call to <b>DrvDocumentEvent</b> with <i>iEsc</i> set to DOCUMENTEVENT_RESETDCPRE.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_RESETDCPRE

</td>
<td>
GDI is about to process a call to its <b>ResetDC</b> function.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_STARTDOCPOST

</td>
<td>
GDI has just processed a call to its <b>StartDoc</b> function.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_STARTDOCPRE 

or

DOCUMENTEVENT_STARTDOC

</td>
<td>
GDI is about to process a call to its <b>StartDoc</b> function.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_STARTPAGE

</td>
<td>
GDI is about to process a call to its <b>StartPage</b> function.

</td>
</tr>
</table>
 


### -param cbIn

Caller-supplied size, in bytes, of the buffer pointed to by <i>pvIn</i>.


### -param pvIn

Caller-supplied pointer, the use of which is dependent on the value supplied for <i>iEsc</i>, as follows:

<table>
<tr>
<th><i>iEsc</i> Constant</th>
<th><i>pvIn</i> Contents</th>
</tr>
<tr>
<td>
DOCUMENTEVENT_ABORTDOC

</td>
<td>
Not used.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_CREATEDCPOST

</td>
<td>
<i>pvIn</i> contains the address of a pointer to the <a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODEW</a> structure specified in the <i>pvOut</i> parameter in a previous call to this function, for which the <i>iEsc</i> parameter was set to DOCUMENTEVENT_CREATEDCPRE.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_CREATEDCPRE

</td>
<td>
<i>pvIn</i> points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/ns-winddiui-_docevent_createdcpre">DOCEVENT_CREATEDCPRE</a> structure.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_DELETEDC

</td>
<td>
Not used.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_ENDDOCPOST

</td>
<td>
Not used.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_ENDDOCPRE 

or

DOCUMENTEVENT_ENDDOC

</td>
<td>
Not used.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_ENDPAGE

</td>
<td>
Not used.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_ESCAPE

</td>
<td>
<i>pvIn</i> points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/ns-winddiui-_docevent_escape">DOCEVENT_ESCAPE</a> structure.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_QUERYFILTER

</td>
<td>
Same as for DOCUMENTEVENT_CREATEDCPRE.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_RESETDCPOST

</td>
<td>
<i>pvIn</i> contains the address of a pointer to the <a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODEW</a> structure specified in the <i>pvOut</i> parameter in a previous call to this function, for which the <i>iEsc</i> parameter was set to DOCUMENTEVENT_RESETDCPRE.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_RESETDCPRE

</td>
<td>
<i>pvIn</i> contains the address of a pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODEW</a> structure supplied by the caller of <b>ResetDC</b> (described in the Microsoft Windows SDK documentation).

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_STARTDOCPOST

</td>
<td>
<i>pvIn</i> points to a LONG that specifies the print job identifier returned by <b>StartDoc</b> (described in the Windows SDK documentation).

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_STARTDOCPRE

or

DOCUMENTEVENT_STARTDOC

</td>
<td>
<i>pvIn</i> contains the address of a pointer to a DOCINFO structure supplied by the caller of <b>StartDoc</b> (both described in the Windows SDK documentation). 

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_STARTPAGE

</td>
<td>
Not used.

</td>
</tr>
</table>
 


### -param cbOut





#### If iEsc is DOCUMENTEVENT_ESCAPE:

Function-supplied value that is used as the <i>cbOutput</i> parameter for <b>ExtEscape</b>.



#### If iEsc is DOCUMENTEVENT_QUERYFILTER:

Caller-supplied size, in bytes, of the buffer pointer to by <i>pvOut</i>.



#### For all other iEsc values:

Not used.


### -param pvOut

Function-supplied pointer to an output buffer, the use of which is dependent on the value supplied for <i>iEsc</i>, as follows. <b>CreateDC</b>, <b>ExtEscape</b>, and <b>ResetDC</b> are described in the Windows SDK documentation.

<table>
<tr>
<th><i>iEsc</i> Constant</th>
<th><i>pvOut</i> Contents</th>
</tr>
<tr>
<td>
DOCUMENTEVENT_CREATEDCPRE

</td>
<td>
Pointer to a driver-supplied DEVMODEW structure, which GDI uses instead of the one supplied by the <b>CreateDC</b> caller. (If <b>NULL</b>, GDI uses the caller-supplied structure.)

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_ESCAPE

</td>
<td>
Buffer pointer that is used as the <i>lpszOutData</i> parameter for <b>ExtEscape</b>.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_QUERYFILTER

</td>
<td>
Caller-supplied pointer to buffer containing a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/ns-winddiui-_docevent_filter">DOCEVENT_FILTER</a> structure.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_RESETDCPRE

</td>
<td>
Pointer to a driver-supplied DEVMODEW structure, which GDI uses instead of the one supplied by the <b>ResetDC</b> caller. (If <b>NULL</b>, GDI uses the caller-supplied structure.)

</td>
</tr>
<tr>
<td>
All other <i>iEsc</i> values

</td>
<td>
Not used.

</td>
</tr>
</table>
 


### -param piResult

Pointer to a memory location that receives one of the following values:

<table>
<tr>
<th>Return Value</th>
<th>Definition</th>
</tr>
<tr>
<td>
DOCUMENTEVENT_FAILURE

</td>
<td>
The driver supports the escape code identified by <i>iEsc</i>, but a failure occurred.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_SUCCESS

</td>
<td>
The driver successfully handled the escape code identified by <i>iEsc</i>. Also see the Remarks section for more information.

</td>
</tr>
<tr>
<td>
DOCUMENTEVENT_UNSUPPORTED

</td>
<td>
The driver does not support the escape code identified by <i>iEsc</i>.

</td>
</tr>
</table>
 


## -returns



This method should return one of the following values. See the Remarks section for more information.

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
The UI plug-in implements this method.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The UI plug-in does not implement this method.

</td>
</tr>
</table>
 




## -remarks



A user interface plug-in's <code>IPrintOemUI2::DocumentEvent</code> method performs the same types of operations as the DrvDocumentEvent DDI that is exported by user-mode printer interface DLLs. For information about document events and how they should be processed, see the description of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/nf-winddiui-drvdocumentevent">DrvDocumentEvent</a> DDI.

If you provide a user interface plug-in, the printer driver's DrvDocumentEvent DDI calls the <code>IPrintOemUI2::DocumentEvent</code> method. The DrvDocumentEvent DDI performs its own processing for the specified event, and then calls the <code>IPrintOemUI2::DocumentEvent</code> method to handle additional processing of the event.

When this method is called with a value of the <i>iEsc</i> parameter of DOCUMENTEVENT_QUERYFILTER, and returns with *<i>piResult</i> == DOCUMENTEVENT_SUCCESS, the spooler can interpret this value in either of two ways, depending on whether certain members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/ns-winddiui-_docevent_filter">DOCEVENT_FILTER</a> structure changed values. For more information, see the Remarks section for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/nf-winddiui-drvdocumentevent">DrvDocumentEvent</a>.

When the DOCUMENTEVENT_QUERYFILTER event is fired, the core driver calls plug-ins in the order they were installed, until one of them returns S_OK, or until all of the plug-ins have been called and none of them returned S_OK. In this way, at most one plug-in is allowed to handle the DOCUMENTEVENT_QUERYFILTER event, and the filter it specifies is applied to all plug-ins in the plug-in chain.

For a plug-in writer who is implementing the <b>IPrintOemUI2</b> interface, but does not need to support the <code>IPrintOemUI2::DocumentEvent</code> method, this method should return E_NOTIMPL for all values of <i>iEsc</i>. If you do need to implement this method, it should return S_OK for all values of <i>iEsc</i>. This signals the core driver that this method has handled the relevant event. The core driver uses the value that this method places in <i>piResult</i> as the return value for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/nf-winddiui-drvdocumentevent">DrvDocumentEvent</a> DDI.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/ns-winddiui-_docevent_createdcpre">DOCEVENT_CREATEDCPRE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/ns-winddiui-_docevent_escape">DOCEVENT_ESCAPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/ns-winddiui-_docevent_filter">DOCEVENT_FILTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winddiui/nf-winddiui-drvdocumentevent">DrvDocumentEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nn-prcomoem-iprintoemui2">IPrintOemUI2</a>
 

 

