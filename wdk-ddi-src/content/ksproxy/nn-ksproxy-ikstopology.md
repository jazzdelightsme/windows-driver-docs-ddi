---
UID: NN:ksproxy.IKsTopology
title: IKsTopology (ksproxy.h)
description: The IKsTopology interface provides a method that opens topology node objects contained within a filter.
old-location: stream\ikstopology.htm
tech.root: stream
ms.assetid: 418a415c-b4db-41a1-825e-66704c45e134
ms.date: 04/23/2018
ms.keywords: IKsTopology, IKsTopology interface [Streaming Media Devices], IKsTopology interface [Streaming Media Devices],described, ksproxy/IKsTopology, ksproxy_521e5b73-c9cc-4cb2-acf5-746e470678cd.xml, stream.ikstopology
ms.topic: interface
req.header: ksproxy.h
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
- ksproxy.h
api_name:
- IKsTopology
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsTopology interface


## -description


The <b>IKsTopology</b> interface provides a method that opens topology node objects contained within a filter.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsTopology</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IKsTopology</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IKsTopology</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ksproxy/nf-ksproxy-ikstopology-createnodeinstance">CreateNodeInstance</a>
</td>
<td align="left" width="63%">
Requests a KS filter object to open a topology node object.

</td>
</tr>
</table> 


## -remarks



The IID for this interface is IID_IKsTopology.

The <b>IKsTopology</b> interface is supported by filters. 



