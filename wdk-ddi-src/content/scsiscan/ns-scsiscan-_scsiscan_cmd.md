---
UID: NS:scsiscan._SCSISCAN_CMD
title: _SCSISCAN_CMD (scsiscan.h)
description: The SCSISCAN_CMD structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_SCSISCAN_CMD.
old-location: image\scsiscan_cmd.htm
tech.root: image
ms.assetid: 412c35b2-eb08-43a3-b776-053645806f5d
ms.date: 05/03/2018
ms.keywords: "*PSCSISCAN_CMD, PSCSISCAN_CMD, PSCSISCAN_CMD structure pointer [Imaging Devices], SCSISCAN_CMD, SCSISCAN_CMD structure [Imaging Devices], _SCSISCAN_CMD, image.scsiscan_cmd, scsiscan/PSCSISCAN_CMD, scsiscan/SCSISCAN_CMD, stifnc_2a67c5d9-7866-4dc5-8ce4-6bc832cbf7de.xml"
ms.topic: struct
req.header: scsiscan.h
req.include-header: Scsiscan.h, Srb.h, Scsi.h
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
- HeaderDef
api_location:
- scsiscan.h
api_name:
- SCSISCAN_CMD
product:
- Windows
targetos: Windows
req.typenames: SCSISCAN_CMD, *PSCSISCAN_CMD
---

# _SCSISCAN_CMD structure


## -description


The SCSISCAN_CMD structure is used as a parameter to <a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a>, when the specified I/O control code is <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/scsiscan/ni-scsiscan-ioctl_scsiscan_cmd">IOCTL_SCSISCAN_CMD</a>.


## -struct-fields




### -field Reserved1

Reserved. Do not use.


### -field Size

Caller-supplied size, in bytes, of the SCSISCAN_CMD structure.


### -field SrbFlags

Caller-supplied SRB_FLAGS-prefixed bit flag specifying the requested operation. Flags are defined in <i>srb.h</i>.


### -field CdbLength

Length, in bytes, of the <a href="https://docs.microsoft.com/windows-hardware/drivers/">CDB</a> contained in the <b>Cdb</b> member.


### -field SenseLength

Length, in bytes, of the sense buffer the <b>pSenseBuffer</b> member points to.


### -field Reserved2

Reserved. Do not use.


### -field Reserved3

Reserved. Do not use.


### -field TransferLength

Length, in bytes, of the buffer to be transferred. This should match the value specified for the <a href="https://docs.microsoft.com/windows/desktop/api/ioapiset/nf-ioapiset-deviceiocontrol">DeviceIoControl</a> function's <i>nOutBufferSize</i> parameter.


### -field Cdb

Caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/">CDB</a> data. (The CDB structure is declared in <i>scsi.h</i>.)


### -field pSrbStatus

Caller-supplied pointer that will receive one of the SRB_STATUS-prefixed status values defined in <i>srb.h</i>.


### -field pSenseBuffer

Caller-supplied pointer to a request-sense buffer, to be filled in by the kernel-mode driver.

