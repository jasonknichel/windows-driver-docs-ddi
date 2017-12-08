---
UID: NE.dot11wdi._WDI_OPERATION_MODE
title: WDI_OPERATION_MODE
author: windows-driver-content
description: The WDI_OPERATION_MODE enumeration defines operation modes.
old-location: netvista\wdi_operation_mode.htm
old-project: netvista
ms.assetid: 9838eeb9-6bd6-46a5-9361-6af3aa2d3014
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: SYNTHVOICEPRIORITY_INSTANCE, SYNTHVOICEPRIORITY_INSTANCE, *PSYNTHVOICEPRIORITY_INSTANCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_OPERATION_MODE
req.alt-loc: dot11wdi.h
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
req.iface: ISynthSinkDMus
---

# WDI_OPERATION_MODE enumeration



## -description
<p>The WDI_OPERATION_MODE enumeration defines operation modes.</p>


## -syntax

````
typedef enum _WDI_OPERATION_MODE { 
  WDI_OPERATION_MODE_STA         = 0x1,
  WDI_OPERATION_MODE_P2P_DEVICE  = 0x8,
  WDI_OPERATION_MODE_P2P_CLIENT  = 0x10,
  WDI_OPERATION_MODE_P2P_GO      = 0x20
} WDI_OPERATION_MODE;
````


## -enum-fields
<dl>

### -field WDI_OPERATION_MODE_STA

<dd>
<p>Infrastructure client.</p>
</dd>

### -field WDI_OPERATION_MODE_P2P_DEVICE

<dd>
<p>Wi-Fi Direct Device.</p>
</dd>

### -field WDI_OPERATION_MODE_P2P_CLIENT

<dd>
<p>Wi-Fi Direct Client.</p>
</dd>

### -field WDI_OPERATION_MODE_P2P_GO

<dd>
<p>Wi-Fi Direct Group Owner.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dot11wdi.h</dt>
</dl>
</td>
</tr>
</table>