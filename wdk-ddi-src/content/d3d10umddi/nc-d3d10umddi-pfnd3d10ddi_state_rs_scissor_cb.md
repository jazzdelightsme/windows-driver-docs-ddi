---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_RS_SCISSOR_CB
title: PFND3D10DDI_STATE_RS_SCISSOR_CB (d3d10umddi.h)
description: The pfnStateRsScissorCb function causes the Microsoft Direct3D 10 runtime to refresh the scissor state.
old-location: display\pfnstatersscissorcb.htm
ms.assetid: 4bb88e3c-2309-42f5-bc22-4c7182358e6e
ms.date: 05/10/2018
ms.keywords: PFND3D10DDI_STATE_RS_SCISSOR_CB, PFND3D10DDI_STATE_RS_SCISSOR_CB callback, d3d10state_functions_8690a3ee-bc2c-4164-808b-c308a1784893.xml, d3d10umddi/pfnStateRsScissorCb, display.pfnstatersscissorcb, pfnStateRsScissorCb, pfnStateRsScissorCb callback function [Display Devices]
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- pfnStateRsScissorCb
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_STATE_RS_SCISSOR_CB callback function


## -description


The <b>pfnStateRsScissorCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the scissor state.


## -parameters




### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function. 


## -returns



None




## -remarks



The <b>pfnStateRsScissorCb</b> function calls the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setscissorrects">SetScissorRects</a> function with all of the currently set scissor rectangles (that is, portions of render targets that rendering is confined to).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setscissorrects">SetScissorRects</a>
 

 

