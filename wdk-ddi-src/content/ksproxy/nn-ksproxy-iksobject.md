---
UID : NN:ksproxy.IKsObject
title : IKsObject
author : windows-driver-content
description : The IKsObject interface provides a method to retrieve the file handle of a KS object.
old-location : stream\iksobject.htm
old-project : stream
ms.assetid : c4422564-3fc0-4087-b628-056488c723e6
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsSynchronousDeviceControl
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : interface
req.header : ksproxy.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IKsObject
req.alt-loc : ksproxy.h,ksproxy.h.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ksproxy.h
req.dll : 
req.irql : 
req.typenames : PIPE_STATE
---

# IKsObject interface

The <b>IKsObject</b> interface provides a method to retrieve the file handle of a KS object.

## Methods

<p>The <b>IKsObject</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [ksproxy.IKsObject.KsGetObjectHandle](nf-ksproxy-iksobject-ksgetobjecthandle.md) | The KsGetObjectHandle method retrieves a file handle to a KS object. |

## Remarks

The IID for this interface is IID_IKsObject.

<b>IKsObject</b> is defined in <i>Ksproxy.h</i> within the #ifdef __STREAMS__ section.

__STREAMS__ is defined in <i>Stream.h</i>, a header from the DirectX SDK.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum UMDF version** |  |
| **Header** | ksproxy.h |
| **DLL** |  |