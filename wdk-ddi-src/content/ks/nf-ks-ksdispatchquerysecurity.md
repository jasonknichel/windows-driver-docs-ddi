---
UID : NF:ks.KsDispatchQuerySecurity
title : KsDispatchQuerySecurity function
author : windows-driver-content
description : The KsDispatchQuerySecurity function is used in the KSDISPATCH_TABLE.QuerySecurity entry to handle querying about the current security descriptor.
old-location : stream\ksdispatchquerysecurity.htm
old-project : stream
ms.assetid : 0aed2613-b40f-4328-91c4-c8e945c6ef17
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsDispatchQuerySecurity
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KsDispatchQuerySecurity
req.alt-loc : Ks.lib,Ks.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ks.lib
req.dll : 
req.irql : 
req.typenames : 
---


# KsDispatchQuerySecurity function
The <b>KsDispatchQuerySecurity</b> function is used in the KSDISPATCH_TABLE.QuerySecurity entry to handle querying about the current security descriptor. The assumption is that the KSOBJECT_HEADER structure is being used in the <b>FsContext</b> data structure and that the <b>CreateItem</b> points to a valid item that optionally contains a security descriptor.

## Syntax

````
NTSTATUS KsDispatchQuerySecurity(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp
);
````

## Parameters

`DeviceObject`

Specifies the device object associated with the IRP.

`Irp`

Specifies the IRP that is being handled.


## Return Value

The <b>KsDispatchQuerySecurity</b> function returns the security query status and completes the IRP if a security descriptor is present. If no security descriptor is present, it returns STATUS_NO_SECURITY_ON_OBJECT.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |