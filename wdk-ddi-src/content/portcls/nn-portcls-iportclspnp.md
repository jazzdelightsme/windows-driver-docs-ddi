---
UID: NN:portcls.IPortClsPnp
title: IPortClsPnp (portcls.h)
description: IPortClsPnp is the PnP management interface that the port class driver (PortCls) exposes to the adapter.
old-location: audio\iportclspnp.htm
tech.root: audio
ms.assetid: AC04051E-8412-4B61-B452-C05A9D8D5CD9
ms.date: 05/08/2018
ms.keywords: IPortClsPnp, IPortClsPnp interface [Audio Devices], IPortClsPnp interface [Audio Devices],described, audio.iportclspnp, portcls/IPortClsPnp
ms.topic: interface
req.header: portcls.h
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
- portcls.h
api_name:
- IPortClsPnp
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsPnp interface


## -description


<code>IPortClsPnp</code> is the PnP management interface that the port class driver (PortCls) exposes to the adapter.

For more information,  see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/implement-pnp-rebalance-for-portcls-audio-drivers">Implement PnP Rebalance for PortCls Audio Drivers</a>.

The <code>IPortClsPnp</code> interface is available in Windows 10, version 1511 and later versions of Windows. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortClsPnp</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPortClsPnp</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPortClsPnp</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iportclspnp-registeradapterpnpmanagement">IPortClsPnp::RegisterAdapterPnpManagement</a>
</td>
<td align="left" width="63%">
The <code>RegisterAdapterPowerManagement</code> method registers the PnP management interface of the adapter with PortCls.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iportclspnp-unregisteradapterpnpmanagement">IPortClsPnp::UnregisterAdapterPnpManagement</a>
</td>
<td align="left" width="63%">
The <code>UnRegisterAdapterPowerManagement</code> method unregisters the PnP management interface of the adapter from PortCls.

</td>
</tr>
</table> 

