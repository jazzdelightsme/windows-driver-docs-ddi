---
UID: NF:wudfddi_hwaccess.WRITE_REGISTER_UCHAR
title: WRITE_REGISTER_UCHAR function (wudfddi_hwaccess.h)
description: The WRITE_REGISTER_UCHAR routine writes a byte to the specified address.
old-location: wdf\write_register_uchar.htm
tech.root: wdf
ms.assetid: C56D6CD8-7D23-4DA7-9241-F72ADBDD2770
ms.date: 02/26/2018
ms.keywords: WRITE_REGISTER_UCHAR, WRITE_REGISTER_UCHAR function, umdf.write_register_uchar, wdf.write_register_uchar, wudfddi_hwaccess/WRITE_REGISTER_UCHAR
ms.topic: function
req.header: wudfddi_hwaccess.h
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
- HeaderDef
api_location:
- Wudfddi_hwaccess.h
api_name:
- WRITE_REGISTER_UCHAR
product:
- Windows
targetos: Windows
req.typenames: 
---

# WRITE_REGISTER_UCHAR function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WRITE_REGISTER_UCHAR</b> routine writes a byte to the specified address.


## -parameters




### -param pDevice [in]

Specifies a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfdevice3">IWDFDevice3</a> interface for the device object of the device to access.


### -param Register [in]

A pointer to the register, which must be a mapped range in memory space.


### -param Value [in]

Specifies a byte to write to the register.


## -returns



This function does not return a value.




## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reading-and-writing-to-device-registers-in-umdf-1-x-drivers">Reading and Writing to Device Registers in UMDF 1.x Drivers</a>.



