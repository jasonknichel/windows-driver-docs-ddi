---
UID : NE:ksmedia.KSCAMERA_PERFRAMESETTING_ITEM_TYPE
title : KSCAMERA_PERFRAMESETTING_ITEM_TYPE
author : windows-driver-content
description : This enumeration contains the different item types for the per-frame settings DDI.
old-location : stream\kscamera_perframesetting_item_type.htm
old-project : stream
ms.assetid : B4312084-E545-45FD-BA93-3BE551CE52DF
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSCAMERA_PERFRAMESETTING_ITEM_TYPE, KSCAMERA_PERFRAMESETTING_ITEM_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ksmedia.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KSCAMERA_PERFRAMESETTING_ITEM_TYPE
req.alt-loc : Ksmedia.h
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
req.typenames : KSCAMERA_PERFRAMESETTING_ITEM_TYPE
---

# KSCAMERA_PERFRAMESETTING_ITEM_TYPE Enumeration
This enumeration contains the different item types for the per-frame settings DDI.

## Syntax
````
typedef enum  { 
  KSCAMERA_PERFRAMESETTING_ITEM_EXPOSURE_TIME          = 1,
  KSCAMERA_PERFRAMESETTING_ITEM_FLASH,
  KSCAMERA_PERFRAMESETTING_ITEM_EXPOSURE_COMPENSATION,
  KSCAMERA_PERFRAMESETTING_ITEM_ISO,
  KSCAMERA_PERFRAMESETTING_ITEM_FOCUS,
  KSCAMERA_PERFRAMESETTING_ITEM_PHOTOCONFIRMATION,
  KSCAMERA_PERFRAMESETTING_ITEM_CUSTOM
} KSCAMERA_PERFRAMESETTING_ITEM_TYPE;
````

## Constants

<table>

<tr>
<td>KSCAMERA_PERFRAMESETTING_ITEM_CUSTOM</td>
<td>This is a custom item type.</td>
</tr>

<tr>
<td>KSCAMERA_PERFRAMESETTING_ITEM_EXPOSURE_COMPENSATION</td>
<td>This is an exposure compensation type.</td>
</tr>

<tr>
<td>KSCAMERA_PERFRAMESETTING_ITEM_EXPOSURE_TIME</td>
<td>This is an exposure item type.</td>
</tr>

<tr>
<td>KSCAMERA_PERFRAMESETTING_ITEM_FLASH</td>
<td>This is a flash item type.</td>
</tr>

<tr>
<td>KSCAMERA_PERFRAMESETTING_ITEM_FOCUS</td>
<td>This is a focus item type.</td>
</tr>

<tr>
<td>KSCAMERA_PERFRAMESETTING_ITEM_ISO</td>
<td>This is an ISO item type.</td>
</tr>

<tr>
<td>KSCAMERA_PERFRAMESETTING_ITEM_PHOTOCONFIRMATION</td>
<td>This is a photo confirmation item type.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h |