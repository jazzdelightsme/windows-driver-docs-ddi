---
UID: NN:filterpipeline.IPrintPipelineProgressReport
title: IPrintPipelineProgressReport (filterpipeline.h)
description: A rendering filter uses the IPrintPipelineProgressReport interface to send progress status to a spooler.
old-location: print\iprintpipelineprogressreport.htm
tech.root: print
ms.assetid: 7a2644af-fdfe-4481-8c44-c40244b8a00e
ms.date: 04/20/2018
ms.keywords: IPrintPipelineProgressReport, IPrintPipelineProgressReport interface [Print Devices], IPrintPipelineProgressReport interface [Print Devices],described, filterpipeline/IPrintPipelineProgressReport, filterpipeline_de104fc6-8ac2-4a10-ab09-09596a093835.xml, print.iprintpipelineprogressreport
ms.topic: interface
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
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
- filterpipeline.h
api_name:
- IPrintPipelineProgressReport
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintPipelineProgressReport interface


## -description


A rendering filter uses the <code>IPrintPipelineProgressReport</code> interface to send progress status to a spooler. 

A rendering filter should search for the <b>XPS_FP_PROGRESS_REPORT</b> property in a property bag, get the progress, and then remove it from the property bag. If there are no rendering filters, the filter pipeline sends the notifications to the spooler. It is very important for a rendering filter to remove the progress and send progress status to the spooler; if progress status is not handled correctly, the spooler may get conflicting progress reports.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintPipelineProgressReport</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintPipelineProgressReport</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintPipelineProgressReport</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nf-filterpipeline-iprintpipelineprogressreport-reportprogress">IPrintPipelineProgressReport::ReportProgress</a>
</td>
<td align="left" width="63%">
The <code>ReportProgress</code> method reports the progress of the XPS job consumption to the pipeline manager.

</td>
</tr>
</table> 

