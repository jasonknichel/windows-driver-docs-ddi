---
UID: NE.ntddsfio._IO_ACCESS_MODE
title: IO_ACCESS_MODE
author: windows-driver-content
description: Defines the types of access mode for Scheduled File I/O (SFIO).
old-location: kernel\io_access_mode.htm
old-project: kernel
ms.assetid: E48BDF14-5B56-45AF-9DD2-F019C8B7D7E5
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: SERIALPERF_STATS, SERIALPERF_STATS, *PSERIALPERF_STATS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddsfio.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IO_ACCESS_MODE
req.alt-loc: Ntddsfio.h
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

# IO_ACCESS_MODE enumeration



## -description
<p>Defines the types of access mode for Scheduled File I/O (SFIO).</p>


## -syntax

````
typedef enum _IO_ACCESS_MODE { 
  SequentialAccess,
  RandomAccess
} IO_ACCESS_MODE;
````


## -enum-fields
<dl>

### -field SequentialAccess

<dd>
<p>Indicates that the input/output will be sent down in a sequential order.</p>
</dd>

### -field RandomAccess

<dd>
<p>Indicates that the input/output might not be in a predictable order.</p>
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
<dt>Ntddsfio.h</dt>
</dl>
</td>
</tr>
</table>