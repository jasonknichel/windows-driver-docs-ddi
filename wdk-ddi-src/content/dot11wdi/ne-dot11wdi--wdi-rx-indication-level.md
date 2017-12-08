---
UID: NE.dot11wdi._WDI_RX_INDICATION_LEVEL
title: WDI_RX_INDICATION_LEVEL
author: windows-driver-content
description: The WDI_RX_INDICATION_LEVEL enumeration defines the RX indication levels.
old-location: netvista\wdi_rx_indication_level.htm
old-project: netvista
ms.assetid: 73ad8d04-c245-4a3c-92ff-4729737ede92
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
req.alt-api: WDI_RX_INDICATION_LEVEL
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

# WDI_RX_INDICATION_LEVEL enumeration



## -description
<p>The WDI_RX_INDICATION_LEVEL enumeration defines the RX indication levels.</p>


## -syntax

````
typedef enum _WDI_RX_INDICATION_LEVEL { 
  WDI_RX_INDICATION_DISPATCH_GENERAL                           = 0,
  WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC                      = 1,
  WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES                      = 2,
  WDI_RX_INDICATION_PASSIVE                                    = 3,
  WDI_RX_INDICATION_FLAG_RESOURCES                             = 0x80000000,
  WDI_RX_INDICATION_DISPATCH_GENERAL_WITH_LOW_RESOURCES        = WDI_RX_INDICATION_FLAG_RESOURCES | WDI_RX_INDICATION_DISPATCH_GENERAL,
  WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC_WITH_LOW_RESSOURCES  = WDI_RX_INDICATION_FLAG_RESOURCES | WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC,
  WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES_WITH_LOW_RESOURCES   = WDI_RX_INDICATION_FLAG_RESOURCES | WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES,
  WDI_RX_INDICATION_PASSIVE_WITH_LOW_RESOURCES                 = WDI_RX_INDICATION_FLAG_RESOURCES | WDI_RX_INDICATION_PASSIVE
} WDI_RX_INDICATION_LEVEL;
````


## -enum-fields
<dl>

### -field WDI_RX_INDICATION_DISPATCH_GENERAL

<dd>
<p>Used for subsequent data indications in a DPC. <b>WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC</b> is used for the first data indication of a DPC.</p>
</dd>

### -field WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC

<dd>
<p>Used for the first data indication (<a href="..\dot11wdi\nc-dot11wdi-ndis-wdi-rx-inorder-data-ind.md">NdisWdiRxInorderDataIndication</a>) of a DPC.</p>
</dd>

### -field WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES

<dd>
<p>Used when making data indications in the context of <a href="..\dot11wdi\nc-dot11wdi-miniport-wdi-rx-resume.md">MiniportWdiRxResume</a>.</p>
</dd>

### -field WDI_RX_INDICATION_PASSIVE

<dd>
<p>Used when making data indications at passive level.</p>
</dd>

### -field WDI_RX_INDICATION_FLAG_RESOURCES

<dd>
<p>Bitwise OR’d with other enum values to cause RxMgr to set <b>NDIS_RECEIVE_FLAG_RESOURCES</b>.</p>
</dd>

### -field WDI_RX_INDICATION_DISPATCH_GENERAL_WITH_LOW_RESOURCES

<dd>
<p>Bitwise OR of <b>WDI_RX_INDICATION_FLAG_RESOURCES</b> and <b>WDI_RX_INDICATION_DISPATCH_GENERAL</b>.</p>
</dd>

### -field WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC_WITH_LOW_RESSOURCES

<dd>
<p>Bitwise OR of <b>WDI_RX_INDICATION_FLAG_RESOURCES</b> and <b>WDI_RX_INDICATION_DISPATCH_FIRST_OF_DPC</b>.</p>
</dd>

### -field WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES_WITH_LOW_RESOURCES

<dd>
<p>Bitwise OR of <b>WDI_RX_INDICATION_FLAG_RESOURCES</b> and <b>WDI_RX_INDICATION_FROM_RX_RESUME_FRAMES</b>.</p>
</dd>

### -field WDI_RX_INDICATION_PASSIVE_WITH_LOW_RESOURCES

<dd>
<p>Bitwise OR of <b>WDI_RX_INDICATION_FLAG_RESOURCES</b> and <b>WDI_RX_INDICATION_PASSIVE</b>.</p>
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