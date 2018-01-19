---
UID : NF:filterpipeline.IPartThumbnail.GetThumbnailProperties
title : IPartThumbnail::GetThumbnailProperties method
author : windows-driver-content
description : The GetThumbnailProperties method gets the thumbnail properties.
old-location : print\ipartthumbnail_getthumbnailproperties.htm
old-project : print
ms.assetid : 4255bdea-4d6e-4e69-ae76-6562a3f07678
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : IPartThumbnail, IPartThumbnail::GetThumbnailProperties, GetThumbnailProperties
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : filterpipeline.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IPartThumbnail.GetThumbnailProperties
req.alt-loc : filterpipeline.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : Filterpipeline.idl
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : EXpsFontRestriction
---


# GetThumbnailProperties method
The <b>GetThumbnailProperties</b> method gets the thumbnail properties.

## Syntax

````
HRESULT GetThumbnailProperties(
  [out] BSTR *pContentType
);
````

## Parameters

`pContentType`

A pointer to the content type of the thumbnail.


## Return Value

<b>GetThumbnailProperties</b> returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | filterpipeline.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |