---
UID: NF:wdm.NtPrepareEnlistment
title: NtPrepareEnlistment function (wdm.h)
description: The ZwPrepareEnlistment routine initiates the prepare operation for a specified enlistment's transaction.
old-location: kernel\zwprepareenlistment.htm
tech.root: kernel
ms.assetid: 1597f27d-8d1e-445e-bc68-b7c151fd19d5
ms.date: 04/30/2018
ms.keywords: NtPrepareEnlistment, ZwPrepareEnlistment, ZwPrepareEnlistment routine [Kernel-Mode Driver Architecture], kernel.zwprepareenlistment, ktm_ref_2da2ab5a-1353-4598-9413-35f6bfc8ee31.xml, wdm/NtPrepareEnlistment, wdm/ZwPrepareEnlistment
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwPrepareEnlistment
- NtPrepareEnlistment
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtPrepareEnlistment function


## -description


The <b>ZwPrepareEnlistment</b> routine initiates the prepare operation for a specified enlistment's transaction.


## -parameters




### -param EnlistmentHandle [in]

A handle to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a> that was obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>. The object must represent a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-a-superior-transaction-manager">superior enlistment</a> and the handle must have ENLISTMENT_SUPERIOR_RIGHTS access to the object.


### -param TmVirtualClock [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-virtual-clock-values">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>ZwPrepareEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ENLISTMENT_NOT_SUPERIOR</b></dt>
</dl>
</td>
<td width="60%">
The caller is not a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-a-superior-transaction-manager">superior transaction manager</a> for the enlistment.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_RESPONSE_NOT_ENLISTED</b></dt>
</dl>
</td>
<td width="60%">
The caller did not register to receive TRANSACTION_NOTIFY_PREPARE_COMPLETE notifications.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The specified handle is not a handle to an enlistment object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The object handle is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have appropriate access to the enlistment object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_REQUEST_NOT_VALID</b></dt>
</dl>
</td>
<td width="60%">
The enlistment's transaction is not in a state that allows it to enter the prepare phase.

</td>
</tr>
</table>
 

The routine might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



Only superior transaction managers can call <b>ZwPrepareEnlistment</b>.

The <b>ZwPrepareEnlistment</b> routine causes KTM to send TRANSACTION_NOTIFY_PREPARE notifications to all resource managers that have enlisted in the transaction.

Callers of <b>ZwPrepareEnlistment</b> must register to receive TRANSACTION_NOTIFY_PREPARE_COMPLETE notifications.

For more information about <b>ZwPrepareEnlistment</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-a-superior-transaction-manager">Creating a Superior Transaction Manager</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/handling-commit-operations">Handling Commit Operations</a>.

<b>NtPrePrepareEnlistment</b> and <b>ZwPrePrepareEnlistment</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-tmprepareenlistment">TmPrepareEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>
 

 

