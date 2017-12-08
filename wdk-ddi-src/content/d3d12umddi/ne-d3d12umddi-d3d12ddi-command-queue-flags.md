---
UID: NE.d3d12umddi.D3D12DDI_COMMAND_QUEUE_FLAGS
title: D3D12DDI_COMMAND_QUEUE_FLAGS
author: windows-driver-content
description: Contains values for the video command queue.
old-location: display\d3d12ddi_command_queue_flags.htm
old-project: display
ms.assetid: A5EFE133-6F63-4EA4-8F7F-B2B6A4E1838C
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DWDDM2_2DDI_SWIZZLE_PATTERN_DESC, D3DWDDM2_2DDI_SWIZZLE_PATTERN_DESC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_COMMAND_QUEUE_FLAGS
req.alt-loc: D3d12umddi.h
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

# D3D12DDI_COMMAND_QUEUE_FLAGS enumeration



## -description
<p>Contains values for the video command queue. </p>


## -syntax

````
typedef enum D3D12DDI_COMMAND_QUEUE_FLAGS { 
  D3D12DDI_COMMAND_QUEUE_FLAG_NONE                = 0x00000000,
  D3D12DDI_COMMAND_QUEUE_FLAG_3D                  = 0x00000001,
  D3D12DDI_COMMAND_QUEUE_FLAG_COMPUTE             = 0x00000002,
  D3D12DDI_COMMAND_QUEUE_FLAG_COPY                = 0x00000004,
  D3D12DDI_COMMAND_QUEUE_FLAG_PAGING              = 0x00000008,
  D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_DECODE   = 0x00000010,
  D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_PROCESS  = 0x00000020
} D3D12DDI_COMMAND_QUEUE_FLAGS;
````


## -enum-fields
<dl>

### -field D3D12DDI_COMMAND_QUEUE_FLAG_NONE

<dd>
<p>No flags.</p>
</dd>

### -field D3D12DDI_COMMAND_QUEUE_FLAG_3D

<dd>
<p>3D.</p>
</dd>

### -field D3D12DDI_COMMAND_QUEUE_FLAG_COMPUTE

<dd>
<p>Compute.</p>
</dd>

### -field D3D12DDI_COMMAND_QUEUE_FLAG_COPY

<dd>
<p>Copy.</p>
</dd>

### -field D3D12DDI_COMMAND_QUEUE_FLAG_PAGING

<dd>
<p>Paging.</p>
</dd>

### -field D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_DECODE

<dd>
<p>Decode video.</p>
</dd>

### -field D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_PROCESS

<dd>
<p>Process video.</p>
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
<dt>D3d12umddi.h (include D3d12umddi.h)</dt>
</dl>
</td>
</tr>
</table>