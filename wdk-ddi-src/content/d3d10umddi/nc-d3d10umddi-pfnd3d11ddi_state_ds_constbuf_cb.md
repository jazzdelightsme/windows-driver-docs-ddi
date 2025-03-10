---
UID: NC:d3d10umddi.PFND3D11DDI_STATE_DS_CONSTBUF_CB
title: PFND3D11DDI_STATE_DS_CONSTBUF_CB (d3d10umddi.h)
description: The pfnStateDsConstBufCb function causes the Microsoft Direct3D 11 runtime to refresh the domain shader constant buffer state.
old-location: display\pfnstatedsconstbufcb.htm
ms.assetid: 8170be69-3e75-4e33-a123-3039e3f9d0c0
ms.date: 05/10/2018
ms.keywords: PFND3D11DDI_STATE_DS_CONSTBUF_CB, PFND3D11DDI_STATE_DS_CONSTBUF_CB callback, d3d10umddi/pfnStateDsConstBufCb, d3d11state_functions_5672a801-6215-48f3-b107-82281c9e8a9d.xml, display.pfnstatedsconstbufcb, pfnStateDsConstBufCb, pfnStateDsConstBufCb callback function [Display Devices]
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: pfnStateDsConstBufCb is supported beginning with the Windows 7 operating system.
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
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- pfnStateDsConstBufCb
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_STATE_DS_CONSTBUF_CB callback function


## -description


The <b>pfnStateDsConstBufCb</b> function causes the Microsoft Direct3D 11 runtime to refresh the domain shader constant buffer state. 


## -parameters




### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D runtime. This handle is supplied to the driver in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function. 

### -param Arg2

Base [in]

The beginning constant buffer for which the runtime should refresh state. 

### -param Arg3

Count [in]

The total number of constant buffers. The number can be -1, which specifies that the Direct3D runtime uses its high watermarks to substitute an optimal value (which is typically less than the maximum valid value for <i>Count</i>). However, no non-NULL binding exists in a slot larger than the optimal <i>Count</i> value.



## -returns



None




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddi_corelayer_devicecallbacks">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>
 

 

