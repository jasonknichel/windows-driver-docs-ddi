---
UID: NS.dot11wdi._WDI_TXRX_TARGET_CONFIGURATION
title: WDI_TXRX_TARGET_CONFIGURATION
author: windows-driver-content
description: The WDI_TXRX_TARGET_CONFIGURATION structure defines the target configuration.
old-location: netvista\wdi_txrx_target_configuration.htm
old-project: netvista
ms.assetid: 5a2d8bdf-cfc2-4724-aab3-0277edb477e7
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDI_TXRX_TARGET_CONFIGURATION, WDI_TXRX_TARGET_CONFIGURATION, *PWDI_TXRX_TARGET_CONFIGURATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_TXRX_TARGET_CONFIGURATION
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
req.irql: PASSIVE_LEVEL
req.iface: 
---

# WDI_TXRX_TARGET_CONFIGURATION structure



## -description
<p>The 
  WDI_TXRX_TARGET_CONFIGURATION structure defines the target configuration.</p>


## -syntax

````
typedef struct _WDI_TXRX_TARGET_CONFIGURATION {
  WDI_TXRX_PARAMETERS TxRxParams;
  UINT8               MaxNumPorts;
  UINT8               MaxNumPeers;
} WDI_TXRX_TARGET_CONFIGURATION, *PWDI_TXRX_TARGET_CONFIGURATION;
````


## -struct-fields
<dl>

### -field TxRxParams

<dd>
<p>Specifies the TXRX parameters.</p>
</dd>

### -field MaxNumPorts

<dd>
<p>Specifies the maximum number of ports.</p>
</dd>

### -field MaxNumPeers

<dd>
<p>Specifies the maximum number of peers.</p>
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