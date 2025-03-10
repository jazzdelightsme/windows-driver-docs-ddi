---
UID: NN:prcomoem.IPrintOemPS2
title: IPrintOemPS2 (prcomoem.h)
description: This section describes the methods defined for the IPrintOemPS2 COM interface. In addition to these methods, this interface includes all of the methods defined in the IPrintOemPS COM interface.
old-location: print\iprintoemps2_interface.htm
tech.root: print
ms.assetid: f2fb4176-c366-4cf9-bc17-59cc0c69a32b
ms.date: 04/20/2018
ms.keywords: IPrintOemPS2, IPrintOemPS2 interface [Print Devices], IPrintOemPS2 interface [Print Devices],described, prcomoem/IPrintOemPS2, print.iprintoemps2_interface, print_unidrv-pscript_rendering_261718f5-d2d9-4032-887d-0faea8b519ad.xml
ms.topic: interface
req.header: prcomoem.h
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
- prcomoem.h
api_name:
- IPrintOemPS2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemPS2 interface


## -description


This section describes the methods defined for the <b>IPrintOemPS2</b> COM interface. In addition to these methods, this interface includes all of the methods defined in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nn-prcomoem-iprintoemps">IPrintOemPS</a> COM interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemPS2</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintOemPS2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintOemPS2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemps2-getpdevadjustment">IPrintOemPS2::GetPDEVAdjustment</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS2::GetPDEVAdjustment</code> method enables a plug-in to override specific <a href="https://docs.microsoft.com/windows-hardware/drivers/">PDEV</a> settings.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemps2-writeprinter">IPrintOemPS2::WritePrinter</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemPS2::WritePrinter</code> method, if supported, enables a rendering plug-in to capture all output data generated by a Postscript driver. If this method is not supported, the output data would otherwise be sent to the spooler in a call to the spooler's <b>WritePrinter</b> API (described in the Microsoft Windows SDK documentation).

</td>
</tr>
</table> 

