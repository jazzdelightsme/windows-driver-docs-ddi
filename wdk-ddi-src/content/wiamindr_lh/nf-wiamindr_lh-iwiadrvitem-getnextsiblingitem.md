---
UID: NF:wiamindr_lh.IWiaDrvItem.GetNextSiblingItem
title: IWiaDrvItem::GetNextSiblingItem (wiamindr_lh.h)
description: The IWiaDrvItem::GetNextSiblingItem method gets the next sibling of the current item in an IWiaDrvItem folder.
old-location: image\iwiadrvitem_getnextsiblingitem.htm
tech.root: image
ms.assetid: bc348f40-aaa4-4cd4-9dee-c02748d7412c
ms.date: 05/03/2018
ms.keywords: DrvItem_659ed27a-dca2-40de-acb7-f057178e9ab7.xml, GetNextSiblingItem, GetNextSiblingItem method [Imaging Devices], GetNextSiblingItem method [Imaging Devices],IWiaDrvItem interface, IWiaDrvItem interface [Imaging Devices],GetNextSiblingItem method, IWiaDrvItem.GetNextSiblingItem, IWiaDrvItem::GetNextSiblingItem, image.iwiadrvitem_getnextsiblingitem, wiamindr_lh/IWiaDrvItem::GetNextSiblingItem
ms.topic: method
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
- wiamindr_lh.h
api_name:
- IWiaDrvItem.GetNextSiblingItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWiaDrvItem::GetNextSiblingItem


## -description


The <b>IWiaDrvItem::GetNextSiblingItem</b> method gets the next sibling of the current item in an <b>IWiaDrvItem</b> folder.


## -parameters




### -param __MIDL__IWiaDrvItem0014






#### - ppISiblingItem [out, optional]

Points to a memory location that will receive the address of the <b>IWiaDrvItem</b> object representing the next sibling item in a folder.


## -returns



If the method succeeds, it stores a pointer to the next sibling item in <i>ppISiblingItem</i> and returns S_OK. If there are no more items in the folder, the method returns S_FALSE. If the method fails, it returns a standard COM error code. 




## -remarks



Minidrivers obtain a pointer to the first child item in a folder by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getfirstchilditem">IWiaDrvItem::GetFirstChildItem</a>. Minidrivers can then obtain the sibling items of this child item in the folder by making successive calls to <b>IWiaDrvItem::GetNextSiblingItem</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nn-wiamindr_lh-iwiadrvitem">IWiaDrvItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getfirstchilditem">IWiaDrvItem::GetFirstChildItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wiamindr_lh/nf-wiamindr_lh-iwiadrvitem-getparentitem">IWiaDrvItem::GetParentItem</a>
 

 

