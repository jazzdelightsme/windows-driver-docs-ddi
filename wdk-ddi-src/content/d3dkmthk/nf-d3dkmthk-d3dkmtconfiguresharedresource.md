---
UID: NF:d3dkmthk.D3DKMTConfigureSharedResource
title: D3DKMTConfigureSharedResource function (d3dkmthk.h)
description: The D3DKMTConfigureSharedResource function configures a shared resource.
old-location: display\d3dkmtconfiguresharedresource.htm
ms.assetid: 3664ef23-f7bc-4a94-8085-aa5a3d0ba550
ms.date: 05/10/2018
ms.keywords: D3DKMTConfigureSharedResource, D3DKMTConfigureSharedResource callback function [Display Devices], OpenGL_Functions_f95f6a64-49a7-4a93-a544-6d4315f12212.xml, PFND3DKMT_CONFIGURESHAREDRESOURCE, PFND3DKMT_CONFIGURESHAREDRESOURCE callback, d3dkmthk/D3DKMTConfigureSharedResource, display.d3dkmtconfiguresharedresource
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTConfigureSharedResource is supported beginning with the Windows 7 operating system.
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
req.lib: Gdi32.lib 
req.dll: Gdi32.dll 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Gdi32.dll
api_name:
- D3DKMTConfigureSharedResource
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTConfigureSharedResource function

## -description


The <b>D3DKMTConfigureSharedResource</b> function configures a shared resource. 

## -parameters

### -param D3DKMT_CONFIGURESHAREDRESOURCE

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_configuresharedresource">D3DKMT_CONFIGURESHAREDRESOURCE</a> structure that specifies parameters to configure the shared resource. 

## -returns

<b>D3DKMTConfigureSharedResource</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | The shared resource was successfully configured. | 
| **STATUS_DEVICE_REMOVED** | The graphics adapter was stopped or the display device was reset. | 
| **STATUS_INVALID_PARAMETER** | Parameters were validated and determined to be incorrect. | 
| **STATUS_NO_MEMORY** | [D3DKMTConfigureSharedResource](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtconfiguresharedresource)  could not complete because of insufficient memory. | 

This function might also return other <b>NTSTATUS</b> values.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_configuresharedresource">D3DKMT_CONFIGURESHAREDRESOURCE</a>
 

 

