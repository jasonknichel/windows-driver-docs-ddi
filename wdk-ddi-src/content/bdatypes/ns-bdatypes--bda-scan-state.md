---
UID: NS.bdatypes._BDA_SCAN_STATE
title: BDA_SCAN_STATE
author: windows-driver-content
description: .
old-location: stream\bda_scan_state.htm
old-project: stream
ms.assetid: C80506D2-AAB6-4A37-A62F-CDDD3DCBC7F1
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: BDA_SCAN_STATE, BDA_SCAN_STATE, *PBDA_SCAN_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BDA_SCAN_STATE
req.alt-loc: Bdatypes.h
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

# BDA_SCAN_STATE structure



## -description
<p></p>


## -syntax

````
typedef struct _BDA_SCAN_STATE {
  PBDARESULT lResult;
  ULONG      ulSignalLock;
  ULONG      ulSecondsLeft;
  ULONG      ulCurrentFrequency;
} BDA_SCAN_STATE, *PBDA_SCAN_STATE;
````


## -struct-fields
<dl>

### -field lResult

<dd></dd>

### -field ulSignalLock

<dd></dd>

### -field ulSecondsLeft

<dd></dd>

### -field ulCurrentFrequency

<dd></dd>
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
<dt>Bdatypes.h</dt>
</dl>
</td>
</tr>
</table>