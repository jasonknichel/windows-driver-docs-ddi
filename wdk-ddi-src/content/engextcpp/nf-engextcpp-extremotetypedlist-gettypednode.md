---
UID : NF:engextcpp.ExtRemoteTypedList.GetTypedNode
title : ExtRemoteTypedList::GetTypedNode method
author : windows-driver-content
description : The GetTypedNode method returns the current list item.
old-location : debugger\extremotetypedlist_gettypednode.htm
old-project : debugger
ms.assetid : f74090c9-4e15-4d6c-bb62-b8d5c56d5a1c
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : debugger.extremotetypedlist_gettypednode, ExtRemoteTypedList class [Windows Debugging], GetTypedNode method, EngExtCpp_Ref_d00ee135-bef4-4326-97e5-374d52fd20a6.xml, ExtRemoteTypedList::GetTypedNode, GetTypedNode method [Windows Debugging], ExtRemoteTypedList class, ExtRemoteTypedList, GetTypedNode method [Windows Debugging], GetTypedNode
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : engextcpp.hpp
req.include-header : Engextcpp.hpp
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : engextcpp.hpp
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# GetTypedNode method
The <b>GetTypedNode</b> method returns the current list item.

## Syntax

````
ExtRemoteTyped GetTypedNode();
````

## Parameters

This function has no parameters.

## Return Value

<b>GetTypedNode</b> returns a typed data description of the current list item.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |