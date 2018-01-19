---
UID : NE:ksmedia.KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY
title : KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY
author : windows-driver-content
description : This enumeration contains the property IDs defined for the per-frame property set.
old-location : stream\ksproperty_cameracontrol_perframesetting_property.htm
old-project : stream
ms.assetid : 59328DD6-3E7B-43C3-A1FF-E02DC24228BA
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY, KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY
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
req.alt-api : KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY
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
req.typenames : KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY
---

# KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY Enumeration
This enumeration contains the property IDs defined for the per-frame property set.

## Syntax
````
typedef enum  { 
  KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_CAPABILITY  = 0,
  KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_SET,
  KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_CLEAR
} KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY;
````

## Constants

<table>

<tr>
<td>KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_CAPABILITY</td>
<td>This is used to query the driver’s per-frame settings capabilities.</td>
</tr>

<tr>
<td>KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_CLEAR</td>
<td>This is used to clear the per-frame settings previously configured.</td>
</tr>

<tr>
<td>KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_SET</td>
<td>This is used to configure the per-frame settings.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h |