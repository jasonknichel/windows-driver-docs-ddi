---
UID: NS.nfcsedev._SECURE_ELEMENT_NFCC_CAPABILITIES
title: SECURE_ELEMENT_NFCC_CAPABILITIES
author: windows-driver-content
description: SECURE_ELEMENT_NFCC_CAPABILITIES contains NFC controller capabilities.
old-location: nfpdrivers\_secure_element_nfcc_capabilities.htm
old-project: nfpdrivers
ms.assetid: D1F9588B-02D9-49B0-B45F-AF5C140D74E4
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: SECURE_ELEMENT_NFCC_CAPABILITIES, SECURE_ELEMENT_NFCC_CAPABILITIES, *PSECURE_ELEMENT_NFCC_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: nfcsedev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SECURE_ELEMENT_NFCC_CAPABILITIES
req.alt-loc: nfcsedev.h
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
req.iface: 
---

# SECURE_ELEMENT_NFCC_CAPABILITIES structure



## -description
<p>SECURE_ELEMENT_NFCC_CAPABILITIES contains NFC controller capabilities. </p>


## -syntax

````
typedef struct _SECURE_ELEMENT_NFCC_CAPABILITIES {
  USHORT  cbMaxRoutingTableSize;
  BOOLEAN IsAidRoutingSupported;
  BOOLEAN IsProtocolRoutingSupported;
  BOOLEAN IsTechRoutingSupported;
} SECURE_ELEMENT_NFCC_CAPABILITIES, *P_SECURE_ELEMENT_NFCC_CAPABILITIES;
````


## -struct-fields
<dl>

### -field cbMaxRoutingTableSize

<dd>
<p>NFCC maximum listen mode routing table size.</p>
</dd>

### -field IsAidRoutingSupported

<dd>
<p>Specifies whether NFCC supports AID-based routing.
</p>
</dd>

### -field IsProtocolRoutingSupported

<dd>
<p>Specify whether NFCC supports protocol-based routing.</p>
</dd>

### -field IsTechRoutingSupported

<dd>
<p>Specify whether NFCC supports technology-based routing.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Nfcsedev.h</dt>
</dl>
</td>
</tr>
</table>