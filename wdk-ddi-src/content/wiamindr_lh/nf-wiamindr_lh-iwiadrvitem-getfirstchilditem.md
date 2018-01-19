---
UID : NF:wiamindr_lh.IWiaDrvItem.GetFirstChildItem
title : IWiaDrvItem::GetFirstChildItem method
author : windows-driver-content
description : The IWiaDrvItem::GetFirstChildItem method gets the first child item in an IWiaDrvItem folder item.
old-location : image\iwiadrvitem_getfirstchilditem.htm
old-project : image
ms.assetid : 2e580a57-03cb-4ff4-b3c6-0b5ef17b4ccb
ms.author : windowsdriverdev
ms.date : 1/17/2018
ms.keywords : IWiaDrvItem, IWiaDrvItem::GetFirstChildItem, GetFirstChildItem
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wiamindr_lh.h
req.include-header : Wiamindr.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IWiaDrvItem.GetFirstChildItem
req.alt-loc : wiamindr_lh.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PSCANWINDOW, SCANWINDOW"
req.product : Windows 10 or later.
---


# GetFirstChildItem method
The <b>IWiaDrvItem::GetFirstChildItem</b> method gets the first child item in an <b>IWiaDrvItem</b> folder item.

## Syntax

````
HRESULT GetFirstChildItem(
  [out, optional] IWiaDrvItem **ppIChildItem
);
````

## Parameters

`__MIDL__IWiaDrvItem0013`




## Return Value

If the method succeeds, it stores a pointer to the first child item in <i>ppIChildItem</i> and returns S_OK. If a child item cannot be found, the method returns S_FALSE. If the item being searched is not a folder, the method returns E_INVALIDARG. If the method fails for another reason, it returns a standard COM error code.

## Remarks

Minidrivers typically use this method to retrieve the first child item in a driver item folder. The item being searched must be a folder item.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wiamindr_lh.h (include Wiamindr.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiadrvitem.md">IWiaDrvItem</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543889">IWiaDrvItem::GetNextSiblingItem</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543892">IWiaDrvItem::GetParentItem</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaDrvItem::GetFirstChildItem method%20 RELEASE:%20(1/17/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>