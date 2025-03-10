---
UID: NF:video.VideoPortReadRegisterUchar
title: VideoPortReadRegisterUchar function (video.h)
description: The VideoPortReadRegisterUchar function reads a byte from a mapped register.
old-location: display\videoportreadregisteruchar.htm
tech.root: display
ms.assetid: 53270599-7e8e-491a-8d7b-05f550f100d3
ms.date: 05/10/2018
ms.keywords: VideoPortReadRegisterUchar, VideoPortReadRegisterUchar function [Display Devices], VideoPort_Functions_c8fea131-5f84-4f77-ab18-2ca8de12e598.xml, display.videoportreadregisteruchar, video/VideoPortReadRegisterUchar
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortReadRegisterUchar
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortReadRegisterUchar function


## -description


The <b>VideoPortReadRegisterUchar</b> function reads a byte from a mapped register.


## -parameters




### -param Register

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.


## -returns



<b>VideoPortReadRegisterUchar</b> returns the byte read from the adapter.




## -remarks



A miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadRegisterUchar</b>.

Callers of <b>VideoPortReadRegisterUchar</b> can be running at any IRQL, provided that the memory pointed to by the <i>Register</i> parameter is resident, mapped device memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
 

 

