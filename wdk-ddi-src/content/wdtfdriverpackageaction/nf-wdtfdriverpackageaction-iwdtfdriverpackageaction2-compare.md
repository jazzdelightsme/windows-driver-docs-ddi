---
UID: NF:wdtfdriverpackageaction.IWDTFDriverPackageAction2.Compare
title: IWDTFDriverPackageAction2::Compare (wdtfdriverpackageaction.h)
description: Compares two driver packages.
old-location: dtf\iwdtfdriverpackageaction2_compare.htm
tech.root: dtf
ms.assetid: fa93d535-fe26-40cc-b08a-88841dcfdc96
ms.date: 04/04/2018
ms.keywords: Compare, Compare method [Windows Device Testing Framework], Compare method [Windows Device Testing Framework],IWDTFDriverPackageAction2 interface, IWDTFDriverPackageAction2 interface [Windows Device Testing Framework],Compare method, IWDTFDriverPackageAction2.Compare, IWDTFDriverPackageAction2::Compare, Microsoft.WDTF.IWDTFDriverPackageAction2.Compare, Microsoft::WDTF::IWDTFDriverPackageAction2::Compare, dtf.iwdtfdriverpackageaction2_compare, wdtfdriverpackageaction/IWDTFDriverPackageAction2::Compare
ms.topic: method
req.header: wdtfdriverpackageaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFDriverPackageAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverPackageAction.Interop.dll
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
- WDTFDriverPackageAction.Interop.dll
api_name:
- IWDTFDriverPackageAction2.Compare
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFDriverPackageAction2::Compare


## -description


Compares two driver packages.


## -parameters




### -param pDp [in]

The second driver package.


### -param pbIsIdentical [out, retval]

True if the two driver packages are the same; 
otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfdriverpackageaction/nn-wdtfdriverpackageaction-iwdtfdriverpackageaction2">IWDTFDriverPackageAction2</a>
 

 

