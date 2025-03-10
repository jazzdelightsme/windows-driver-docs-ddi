---
UID: NF:printerextension.IPrintSchemaTicket.ValidateAsync
title: IPrintSchemaTicket::ValidateAsync (printerextension.h)
description: Gets an asynchronous PrintTicket validation operation context.
old-location: print\iprintschematicket_validateasync.htm
tech.root: print
ms.assetid: B46AE68A-36E1-4367-95F5-0FFBAA42171C
ms.date: 04/20/2018
ms.keywords: IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices],ValidateAsync method, IPrintSchemaTicket.ValidateAsync, IPrintSchemaTicket::ValidateAsync, ValidateAsync, ValidateAsync method [Print Devices], ValidateAsync method [Print Devices],IPrintSchemaTicket interface, print.iprintschematicket_validateasync, printerextension/IPrintSchemaTicket::ValidateAsync
ms.topic: method
req.header: printerextension.h
req.include-header: 
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
- COM
api_location:
- printerextension.h
api_name:
- IPrintSchemaTicket.ValidateAsync
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintSchemaTicket::ValidateAsync


## -description


Gets an asynchronous PrintTicket validation operation context.


## -parameters




### -param ppAsyncOperation [out]

The asynchronous validation operation context.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



 To perform the validation operation, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemaasyncoperation-start">IPrintSchemaAsyncOperation::Start</a> method to validate the settings of the current PrintTicket object and to pass the resulting PrintTicket to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemaasyncoperationevent-completed">IPrintSchemaAsyncOperationEvent::Completed</a> event. When the validation operation is completed, or if an error occurs during the validation operation, the <b>IPrintSchemaAsyncOperationEvent::Completed</b> event is fired. This method will not change the settings of the current PrintTicket object.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprintschemaasyncoperation">IPrintSchemaAsyncOperation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemaasyncoperation-start">IPrintSchemaAsyncOperation::Start</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprintschemaasyncoperationevent-completed">IPrintSchemaAsyncOperationEvent::Completed</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprintschematicket">IPrintSchemaTicket</a>
 

 

