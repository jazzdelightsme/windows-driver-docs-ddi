---
UID: NF:irb.AtaPortRegistryControllerKeyWrite
title: AtaPortRegistryControllerKeyWrite function (irb.h)
description: The AtaPortRegistryControllerKeyWrite routine writes the data to the indicated value name under the registry key HKLM\CurrentControlSet\Services\<service name>\ControllerN, where N is the number of the controller.
old-location: storage\ataportregistrycontrollerkeywrite.htm
tech.root: storage
ms.assetid: dfe97cce-f349-49a1-9075-c3c3d1a60681
ms.date: 03/29/2018
ms.keywords: AtaPortRegistryControllerKeyWrite, AtaPortRegistryControllerKeyWrite routine [Storage Devices], atartns_c17cd629-759c-4469-a7f4-61125a791736.xml, irb/AtaPortRegistryControllerKeyWrite, storage.ataportregistrycontrollerkeywrite
ms.topic: function
req.header: irb.h
req.include-header: Ata.h, Irb.h
req.target-type: Desktop
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
- irb.h
api_name:
- AtaPortRegistryControllerKeyWrite
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortRegistryControllerKeyWrite function


## -description


The <b>AtaPortRegistryControllerKeyWrite</b> routine writes the data to the indicated value name under the registry key <b>HKLM\CurrentControlSet\Services\</b><i><service name></i><b>\Controller</b><i>N</i>, where <i>N </i>is the number of the controller. 
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension. 


### -param ControllerNumber [in]

Contains the controller number. 


### -param ValueName [in]

Contains the name of the registry value to write to. 


### -param ValueType [in]

Indicates the type of data that is contained in the registry value. This member should be assigned one of the values indicated in the following table.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
IDE_REG_DWORD

</td>
<td>
A 4-byte numeric value. 

</td>
</tr>
<tr>
<td>
IDE_REG_BINARY

</td>
<td>
Binary data. 

</td>
</tr>
<tr>
<td>
IDE_REG_SZ

</td>
<td>
A null-terminated, Unicode string. 

</td>
</tr>
</table>
 


### -param Buffer [in]

A pointer to the source buffer that contains the data to write to the registry value. 


### -param BufferLength

<p>A pointer to the number of bytes of data to copy. If the operation fails, the location that is pointed to by <i>Length</i> will update the length of data that was successfully copied to the registry.</p>




## -returns



<b>AtaPortRegistryControllerKeyWrite</b> returns <b>TRUE</b> if the operation succeeds. Otherwise, it returns <b>FALSE</b>. The routine also returns <b>FALSE</b> if the miniport driver does not call it from the correct routine. 




## -remarks



The buffer should be allocated by using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nf-irb-ataportregistryallocatebuffer">AtaPortRegistryAllocateBuffer</a>. 

The miniport driver must call <b>AtaPortRegistryControllerKeyWrite</b> during the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nc-irb-ide_channel_init">AtaChannelInitRoutine</a> routine or the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nc-irb-ide_hw_control">IdeHwControl</a> routine.; The miniport driver cannot call <b>AtaPortRegistryControllerKeyWrite</b> from any other routine or it will return <b>FALSE</b>. Additionally, the miniport driver can only call <b>AtaPortRegistryControllerKeyWrite</b> from its <b>IdeHwControl</b> routine if its <b>IdeHwControl</b> routine was called and had a value of either <b>StartChannel</b> or <b>StopChannel</b> in its <i>ControlAction </i>parameter. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nc-irb-ide_channel_init">AtaChannelInitRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nf-irb-ataportregistryallocatebuffer">AtaPortRegistryAllocateBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/irb/nc-irb-ide_hw_control">IdeHwControl</a>
 

 

