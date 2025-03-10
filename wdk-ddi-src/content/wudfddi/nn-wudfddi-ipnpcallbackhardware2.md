---
UID: NN:wudfddi.IPnpCallbackHardware2
title: IPnpCallbackHardware2 (wudfddi.h)
description: The IPnpCallbackHardware2 interface exposes callback methods related to hardware.
old-location: wdf\ipnpcallbackhardware2.htm
tech.root: wdf
ms.assetid: C0DB967F-0A1A-4749-B902-EBA0D59A3E45
ms.date: 02/26/2018
ms.keywords: IPnpCallbackHardware2, IPnpCallbackHardware2 interface, IPnpCallbackHardware2 interface,described, umdf.ipnpcallbackhardware2, wdf.ipnpcallbackhardware2, wudfddi/IPnpCallbackHardware2
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
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
- Wudfddi.h
api_name:
- IPnpCallbackHardware2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPnpCallbackHardware2 interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

  The <b>IPnpCallbackHardware2</b>  interface exposes callback methods related to hardware.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPnpCallbackHardware2</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPnpCallbackHardware2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPnpCallbackHardware2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onpreparehardware">OnPrepareHardware</a>
</td>
<td align="left" width="63%">

   The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onpreparehardware">OnPrepareHardware</a> method performs any operations that are needed to make a device accessible to the driver.
  

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onreleasehardware">OnReleaseHardware</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallbackhardware2-onreleasehardware">OnReleaseHardware</a> method performs operations that are needed when a device is no longer accessible.

</td>
</tr>
</table> 


## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a>
 

 

