---
UID: NS.strmini.PKSSCATTER_GATHER
title: PKSSCATTER_GATHER
author: windows-driver-content
description: .
old-location: stream\ksscatter_gather.htm
old-project: stream
ms.assetid: 10AFDC4B-75E5-4E88-A614-60043848C570
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSSCATTER_GATHER, KSSCATTER_GATHER, *PKSSCATTER_GATHER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: strmini.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSSCATTER_GATHER
req.alt-loc: Strmini.h
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
req.product: Windows 10 or later.
---

# PKSSCATTER_GATHER structure



## -description
<p></p>


## -syntax

````
typedef struct {
  PHYSICAL_ADDRESS PhysicalAddress;
  ULONG            Length;
} KSSCATTER_GATHER, *PKSSCATTER_GATHER;
````


## -struct-fields
<dl>

### -field PhysicalAddress

<dd></dd>

### -field Length

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
<dt>Strmini.h</dt>
</dl>
</td>
</tr>
</table>