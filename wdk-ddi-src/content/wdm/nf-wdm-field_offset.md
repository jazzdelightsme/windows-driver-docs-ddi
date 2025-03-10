---
UID: NF:wdm.FIELD_OFFSET
title: FIELD_OFFSET macro (wdm.h)
description: The FIELD_OFFSET macro returns the byte offset of a named field in a known structure type.
old-location: kernel\field_offset.htm
tech.root: kernel
ms.assetid: c792d021-3c64-4341-878c-08a7e163447c
ms.date: 04/30/2018
ms.keywords: FIELD_OFFSET, FIELD_OFFSET function [Kernel-Mode Driver Architecture], k106_d6f0b450-e99c-4dd7-94c5-f428e4b1d642.xml, kernel.field_offset, ntdef/FIELD_OFFSET
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Miniport.h, Minitape.h, Scsi.h, Storport.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntdef.h
api_name:
- FIELD_OFFSET
product:
- Windows
targetos: Windows
req.typenames: 
---

# FIELD_OFFSET macro


## -description


The <b>FIELD_OFFSET</b> macro returns the byte offset of a named field in a known structure type.


## -parameters




### -param type [in]


Specifies the name of a known structure type containing <i>Field</i>. 


### -param field [in]

Specifies the name of a field in a structure of type <i>Type</i>. 





## -remarks



Used by device driver writers to symbolically determine the offset of a known field in a known structure type. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">CONTAINING_RECORD</a>
 

 

