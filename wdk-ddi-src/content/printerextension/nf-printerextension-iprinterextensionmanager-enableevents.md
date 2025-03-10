---
UID: NF:printerextension.IPrinterExtensionManager.EnableEvents
title: IPrinterExtensionManager::EnableEvents (printerextension.h)
description: The EnableEvents method allows events to be generated for the specified printer driver until DisableEvents is called.
old-location: print\iprinterextensionmanager_enableevents.htm
tech.root: print
ms.assetid: 8DF89C18-10CA-4E8B-8E2A-B373C80F7B39
ms.date: 04/20/2018
ms.keywords: EnableEvents, EnableEvents method [Print Devices], EnableEvents method [Print Devices],IPrinterExtensionManager interface, IPrinterExtensionManager interface [Print Devices],EnableEvents method, IPrinterExtensionManager.EnableEvents, IPrinterExtensionManager::EnableEvents, print.iprinterextensionmanager_enableevents, printerextension/IPrinterExtensionManager::EnableEvents
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
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
- Printerextension.h
api_name:
- IPrinterExtensionManager.EnableEvents
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrinterExtensionManager::EnableEvents


## -description


The EnableEvents method allows events to be generated for the specified printer driver until  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nf-printerextension-iprinterextensionmanager-disableevents">DisableEvents</a> is called. 


## -parameters




### -param printerDriverId [in]

The GUID representing the specified driver for which to enable events. This GUID is specified in the INF file, and is also specified by the manifest file directive 'PrinterDriverID'.


## -returns



This method returns an <b>HRESULT</b> value.

The printer extension should call this method when it is launched so that driver events are generated for it to consume.




## -remarks



In the case of a driver event like, for example, Print Preferences or Printer Notifications, the app is expected to call <b>EnableEvents</b>. But if the app doesn't call <b>EnableEvents</b> within 30s, the print system assumes that a UI was  called but it's not being responsive so a standard UI is displayed instead.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printerextension/nn-printerextension-iprinterextensionmanager">IPrinterExtensionManager</a>
 

 

