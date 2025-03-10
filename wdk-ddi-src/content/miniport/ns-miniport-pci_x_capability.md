---
UID: NS:miniport.__unnamed_struct_0
title: PCI_X_CAPABILITY (miniport.h)
description: The PCI_X_CAPABILITY structure reports the contents of the command and status registers of a device that is compliant with the PCI-X Addendum to the PCI Local Bus Specification.
old-location: pci\pci_x_capability.htm
tech.root: PCI
ms.assetid: b30ccf86-ae6d-484a-a3f2-8b38df26e995
ms.date: 02/24/2018
ms.keywords: "*PPCI_X_CAPABILITY, PCI.pci_x_capability, PCI_X_CAPABILITY, PCI_X_CAPABILITY structure [Buses], PPCI_X_CAPABILITY, PPCI_X_CAPABILITY structure pointer [Buses], pci_struct_171a6a86-48fe-4955-8f12-43df82659f7a.xml, wdm/PCI_X_CAPABILITY, wdm/PPCI_X_CAPABILITY"
ms.topic: struct
req.header: miniport.h
req.include-header: Wdm.h, Miniport.h
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
req.irql: Any level (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- PCI_X_CAPABILITY
product:
- Windows
targetos: Windows
req.typenames: PCI_X_CAPABILITY, *PPCI_X_CAPABILITY
---

# PCI_X_CAPABILITY structure


## -description


The PCI_X_CAPABILITY structure reports the contents of the command and status registers of a device that is compliant with the <i>PCI-X Addendum to the PCI Local Bus Specification.</i>


## -syntax


```cpp
typedef struct {
  PCI_CAPABILITIES_HEADER Header;
  union {
    struct {
      USHORT DataParityErrorRecoveryEnable  :1;
      USHORT EnableRelaxedOrdering  :1;
      USHORT MaxMemoryReadByteCount  :2;
      USHORT MaxOutstandingSplitTransactions  :3;
      USHORT Reserved  :9;
    } bits;
    USHORT AsUSHORT;
  } Command;
  union {
    struct {
      ULONG FunctionNumber;
      ULONG DeviceNumber;
      ULONG BusNumber;
      ULONG Device64Bit;
      ULONG Capable133MHz;
      ULONG SplitCompletionDiscarded;
      ULONG UnexpectedSplitCompletion;
      ULONG DeviceComplexity;
      ULONG DesignedMaxMemoryReadByteCount;
      ULONG DesignedMaxOutstandingSplitTransactions;
      ULONG DesignedMaxCumulativeReadSize;
      ULONG ReceivedSplitCompletionErrorMessage;
      ULONG CapablePCIX266;
      ULONG CapablePCIX533;
    } bits;
    ULONG  AsULONG;
  } Status;
} PCI_X_CAPABILITY, *PPCI_X_CAPABILITY;
```


## -struct-fields




### -field Header

Contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_pci_capabilities_header">PCI_CAPABILITIES_HEADER</a> that identifies the capability and provides a link to the next capability description.


### -field Command



#### AsUSHORT

Reports the data in the device's command register in the form of a unsigned long integer.


### -field Command.bits


### -field Command.bits.DataParityErrorRecoveryEnable

Indicates that the data parity error recovery bit is set in the device's command register, and the device will attempt to recover from data parity errors. For more information about the significance of the value in the parity error recovery bit, see the <i>PCI Local Bus Specification</i>.


### -field Command.bits.EnableRelaxedOrdering

Indicates the enable relaxed ordering bit is set in the device's command register. This leaves the device free to adopt a more relaxed transaction ordering policy. For more information about how this bit effects transaction ordering, see the <i>PCI Local Bus Specification</i>.


### -field Command.bits.MaxMemoryReadByteCount

Reports the maximum byte count, recorded in the command register, that the device uses when initiating a burst memory read command. For more information about how this bit effects read commands, see the <i>PCI Local Bus Specification</i>.


### -field Command.bits.MaxOutstandingSplitTransactions

Reports the maximum number of split transactions, recorded in the command register, that the device can initiate asynchronously. For more information about how this value effects split transactions, see the <i>PCI Local Bus Specification</i>.


### -field Command.bits.Reserved

Reserved.


### -field Status



#### AsULONG

Reports the data in the device's status register in the form of a unsigned long integer.


### -field Status.bits


### -field Status.bits.FunctionNumber

Indicates the value in the function number field of an address of a type 0 configuration transaction. For more information about the meaning of this number, see the <i>PCI Local Bus Specification</i>.


### -field Status.bits.DeviceNumber

Indicates the value in the device number field of the address of a type 0 configuration transaction. For more information about the meaning of this number, see the <i>PCI Local Bus Specification</i>.


### -field Status.bits.BusNumber

Indicates the number of the bus segment on which the device is located. For more information about the meaning of this number, see the <i>PCI Local Bus Specification</i>.


### -field Status.bits.Device64Bit

Indicates when 1 that the bus is 64 bits wide. When 0 the bus is 32 bits wide. For more information about the meaning of the status register's device 64 bit, see the <i>PCI Local Bus Specification</i>.


### -field Status.bits.Capable133MHz

Indicates when 1 that the device's maximum operating frequency is 133 MHz. Indicates when 0 that the device's maximum operating frequency is 66 MHz. For more information about the meaning of status register's capable 133 Mhz bit, see the <i>PCI Local Bus Specification</i>.


### -field Status.bits.SplitCompletionDiscarded

Indicates when 1 that the device discarded a split completion transaction because the requester rejected it. A value of 0 indicates that the device has not discarded any split completion transactions since the status register's split completion discarded bit was last cleared. For more information about the status register's split completion discarded bit, see the <i>PCI Local Bus Specification</i>.


### -field Status.bits.UnexpectedSplitCompletion

Indicates when 1 that the device has received a split completion transaction with the device's requester ID. Indicates when 0 that the device has not received this kind of transaction. For more information about the meaning of the status register's unexpected split completion bit, see the <i>PCI Local Bus Specification</i>.


### -field Status.bits.DeviceComplexity

Indicates when 1 that the device is a bridge device. When 0 the device is not a bridge device. For more information about the meaning of the status register's device complexity bit, see the <i>PCI Local Bus Specification</i>.


### -field Status.bits.DesignedMaxMemoryReadByteCount

Reports the maximum byte count, defined in the status register, that the device uses when it initiates a read sequence. For more information about the meaning of this value, see the <i>PCI Local Bus Specification</i>.


### -field Status.bits.DesignedMaxOutstandingSplitTransactions

Reports the maximum number of split transactions, defined in the status register, that the device can permit at any one time. For more information about the meaning of this value, see the <i>PCI Local Bus Specification</i>.


### -field Status.bits.DesignedMaxCumulativeReadSize

Reports the maximum number of burst memory read transactions, defined in the status register, that the device allows at any one time. For more information about this value, see the <i>PCI Local Bus Specification</i>.


### -field Status.bits.ReceivedSplitCompletionErrorMessage

Indicates when 1 that the device has received a split completion error message. Indicates when 0 that the device has not received a split completion error message.


### -field Status.bits.CapablePCIX266




### -field Status.bits.CapablePCIX533






## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_pci_capabilities_header">PCI_CAPABILITIES_HEADER</a>



 

 


