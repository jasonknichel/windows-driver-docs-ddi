---
UID: NE.d3d10umddi.D3D11_1DDI_VIDEO_FRAME_FORMAT
title: D3D11_1DDI_VIDEO_FRAME_FORMAT
author: windows-driver-content
description: Describes how a video stream is interlaced.
old-location: display\d3d11_1ddi_video_frame_format.htm
old-project: display
ms.assetid: 36af5af2-dfb1-4827-8898-93e52f4c8312
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11_1DDI_VIDEO_FRAME_FORMAT
req.alt-loc: D3d10umddi.h
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

# D3D11_1DDI_VIDEO_FRAME_FORMAT enumeration



## -description
<p>Describes how a video stream is interlaced.</p>


## -syntax

````
typedef enum D3D11_1DDI_VIDEO_FRAME_FORMAT { 
  D3D11_1DDI_VIDEO_FRAME_FORMAT_PROGRESSIVE                    = 0,
  D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST     = 1,
  D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST  = 2
} D3D11_1DDI_VIDEO_FRAME_FORMAT;
````


## -enum-fields
<dl>

### -field D3D11_1DDI_VIDEO_FRAME_FORMAT_PROGRESSIVE

<dd>
<p>Frames are progressive.</p>
</dd>

### -field D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_TOP_FIELD_FIRST

<dd>
<p>Frames are interlaced. The top field of each frame is displayed first.</p>
</dd>

### -field D3D11_1DDI_VIDEO_FRAME_FORMAT_INTERLACED_BOTTOM_FIELD_FIRST

<dd>
<p>Frame are interlaced. The bottom field of each frame is displayed first.</p>
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
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>