---
UID: NS.d3d12umddi.D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030
title: D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030
author: windows-driver-content
description: Video content protection system support data.
old-location: display\d3d12ddi-video-content-protection-system-support-data-0030.htm
old-project: display
ms.assetid: 82096e3b-574d-44f6-85a9-b560749f6472
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030, D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030
req.alt-loc: d3d12umddi.h
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

# D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030 structure



## -description
<p>Video content protection system support data.</p>


## -syntax

````
typedef struct _D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030 {
  UINT    NodeIndex;
  UINT    ContentProtectionSystemCount;
  GUID *  pContentProtectionSystems;
} D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030, D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030;
````


## -struct-fields
<dl>

### -field NodeIndex

<dd>
<p>Node index.</p>
</dd>

### -field ContentProtectionSystemCount

<dd>
<p>Content protection system count.</p>
</dd>

### -field pContentProtectionSystems

<dd>
<p>Content protection systems.</p>
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
<dt>D3d12umddi.h</dt>
</dl>
</td>
</tr>
</table>