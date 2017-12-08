---
UID: NS.ksmedia.PKSCAMERA_PERFRAMESETTING_HEADER
title: PKSCAMERA_PERFRAMESETTING_HEADER
author: windows-driver-content
description: This structure contains header information for the per-frame settings payload.
old-location: stream\kscamera_perframesetting_header.htm
old-project: stream
ms.assetid: 2D8A9E54-5551-4DDF-A123-077BA73AE06D
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSCAMERA_PERFRAMESETTING_HEADER, KSCAMERA_PERFRAMESETTING_HEADER, *PKSCAMERA_PERFRAMESETTING_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCAMERA_PERFRAMESETTING_HEADER
req.alt-loc: Ksmedia.h
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

# PKSCAMERA_PERFRAMESETTING_HEADER structure



## -description
<p>This structure contains header information for the per-frame settings payload.</p>


## -syntax

````
typedef struct {
  ULONG     Size;
  ULONG     FrameCount;
  GUID      Id;
  ULONGLONG Flags;
  ULONG     LoopCount;
  ULONG     Reserved;
} KSCAMERA_PERFRAMESETTING_HEADER, *PKSCAMERA_PERFRAMESETTING_HEADER;
````


## -struct-fields
<dl>

### -field Size

<dd>
<p>The size of this header, frame headers, item headers, value payloads, custom items, and custom data for all frames.</p>
</dd>

### -field FrameCount

<dd>
<p>The number of frame settings in this per-frame settings payload.</p>
</dd>

### -field Id

<dd>
<p>Not used.</p>
</dd>

### -field Flags

<dd>
<p>Not used.</p>
</dd>

### -field LoopCount

<dd>
<p>The number of repeats for this per-frame setting. This is always 1.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved for future use.</p>
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
<dt>Ksmedia.h</dt>
</dl>
</td>
</tr>
</table>