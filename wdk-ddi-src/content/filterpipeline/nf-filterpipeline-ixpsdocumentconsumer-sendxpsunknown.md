---
UID : NF:filterpipeline.IXpsDocumentConsumer.SendXpsUnknown
title : IXpsDocumentConsumer::SendXpsUnknown method
author : windows-driver-content
description : The SendXpsUnknown method sends an XPS document part that cannot be identified to the filter pipeline.
old-location : print\ixpsdocumentconsumer_sendxpsunknown.htm
old-project : print
ms.assetid : 5e2880c6-0f5a-4098-a97e-809ad75ddfd0
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : IXpsDocumentConsumer, IXpsDocumentConsumer::SendXpsUnknown, SendXpsUnknown
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
req.alt-api : IXpsDocumentConsumer.SendXpsUnknown
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


# SendXpsUnknown method
The <code>SendXpsUnknown</code> method sends an XPS document part that cannot be identified to the filter pipeline.

## Syntax

````
HRESULT SendXpsUnknown(
  [in] IUnknown *pUnknown
);
````

## Parameters

`pUnknown`

A pointer to an unrecognized document part interface.


## Return Value

<code>SendXpsUnknown</code> returns an HRE<b></b>SULT value.

## Remarks

If the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556324">IXpsDocumentProvider::GetXpsPart</a> method returns an object that the filter cannot identify, the filter should forward the unrecognized object to the next filter in the filter pipeline by calling <code>SendXpsUnknown</code>. Passing unrecognized objects to the next filter helps the filter maintain compatibility with future document formats.</p>

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