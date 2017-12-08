---
UID: NS.dxva._DXVA_DeinterlaceQueryAvailableModes
title: DXVA_DeinterlaceQueryAvailableModes
author: windows-driver-content
description: The DXVA_DeinterlaceQueryAvailableModes structure describes the available deinterlacing or frame-rate conversion modes for a particular input video format.
old-location: display\dxva_deinterlacequeryavailablemodes.htm
old-project: display
ms.assetid: c754f540-19ff-491f-89ec-63d3306c4068
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXVA_DeinterlaceQueryAvailableModes, DXVA_DeinterlaceQueryAvailableModes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVA_DeinterlaceQueryAvailableModes
req.alt-loc: dxva.h
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

# DXVA_DeinterlaceQueryAvailableModes structure



## -description
<p>The DXVA_DeinterlaceQueryAvailableModes structure describes the available deinterlacing or frame-rate conversion modes for a particular input video format.</p>


## -syntax

````
typedef struct _DXVA_DeinterlaceQueryAvailableModes {
  DWORD Size;
  DWORD NumGuids;
  GUID  Guids[MAX_DEINTERLACE_DEVICE_GUIDS];
} DXVA_DeinterlaceQueryAvailableModes;
````


## -struct-fields
<dl>

### -field Size

<dd>
<p>Indicates the size of this structure.</p>
</dd>

### -field NumGuids

<dd>
<p>Indicates the number of GUIDs that are returned in the <b>Guids</b> member for the available modes.</p>
</dd>

### -field Guids

<dd>
<p>An array of GUIDs that are returned for the available deinterlace modes.</p>
</dd>
</dl>

## -remarks
<p>The driver receives the DXVA_DeinterlaceQueryAvailableModes structure with the <b>Size</b> member assigned, assigns values to the remaining members, and returns DXVA_DeinterlaceQueryAvailableModes to the renderer.</p>

<p>There is a GUID for each deinterlace and frame conversion mode returned by the driver. The GUIDs should be returned in order of descending quality (that is, the highest quality mode should occupy the first element of the GUID array returned). </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dxva.h (include Dxva.h)</dt>
</dl>
</td>
</tr>
</table>