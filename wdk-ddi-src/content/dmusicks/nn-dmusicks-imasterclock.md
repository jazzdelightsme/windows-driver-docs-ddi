---
UID: NN:dmusicks.IMasterClock
title: IMasterClock (dmusicks.h)
description: The IMasterClock interface provides Microsoft DirectMusic streams with access to the current reference time from the master clock.
old-location: audio\imasterclock.htm
tech.root: audio
ms.assetid: 754aad8a-834c-4197-8505-dbf1cd74c697
ms.date: 05/08/2018
ms.keywords: IMasterClock, IMasterClock interface [Audio Devices], IMasterClock interface [Audio Devices],described, audio.imasterclock, audmp-routines_b8172e0e-55ac-4abd-8b62-39be5d708f9b.xml, dmusicks/IMasterClock
ms.topic: interface
req.header: dmusicks.h
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
- dmusicks.h
api_name:
- IMasterClock
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMasterClock interface


## -description


The <code>IMasterClock</code> interface provides Microsoft DirectMusic streams with access to the current reference time from the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/master-clocks">master clock</a>. The DMus port driver implements this interface to support accurate timing in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dmusicks/nn-dmusicks-imxf">IMXF</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dmusicks/nn-dmusicks-iallocatormxf">IAllocatorMXF</a> interfaces that make up the MIDI-transport part of the filter graph. When calling a DMus miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dmusicks/nf-dmusicks-iminiportdmus-newstream">IMiniportDMus::NewStream</a> method, the DMus port driver passes an <code>IMasterClock</code> reference as a call parameter. The <code>IMasterClock</code> interface wraps the master clock, as described in <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/latency-clocks">Latency Clocks</a>. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IMasterClock</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IMasterClock</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IMasterClock</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dmusicks/nf-dmusicks-imasterclock-gettime">IMasterClock::GetTime</a>
</td>
<td align="left" width="63%">
The <code>GetTime</code> method retrieves the current reference time read from the master clock.

</td>
</tr>
</table> 

