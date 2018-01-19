---
UID : NF:filterpipeline.IXpsPartIterator.IsDone
title : IXpsPartIterator::IsDone method
author : windows-driver-content
description : The IsDone method determines whether the iterator has finished the iteration.
old-location : print\ixpspartiterator_isdone.htm
old-project : print
ms.assetid : 80877e8e-378f-4849-a8ce-b0651fdc2755
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : IXpsPartIterator, IXpsPartIterator::IsDone, IsDone
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
req.alt-api : IXpsPartIterator.IsDone
req.alt-loc : Filterpipeline.h
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


# IsDone method
The <code>IsDone</code> method determines whether the iterator has finished  the iteration.

## Syntax

````
BOOL STDMETHODCALLTYPE IsDone(
    None
);
````

## Parameters

This function has no parameters.

## Return Value

<code>IsDone</code> returns <b>true</b> if the iterator has finished iterating.


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