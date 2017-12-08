---
UID: NE.d3dkmdt._DXGK_DISPLAY_TECHNOLOGY
title: DXGK_DISPLAY_TECHNOLOGY
author: windows-driver-content
description: Enum used to specify the display technology being used.
old-location: display\dxgk_display_technology.htm
old-project: display
ms.assetid: 4612213A-E79F-4C3B-95B4-8C83C0B5FB32
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO, DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_DISPLAY_TECHNOLOGY
req.alt-loc: d3dkmdt.h
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

# DXGK_DISPLAY_TECHNOLOGY enumeration



## -description
<p>Enum used to specify the display technology being used.</p>


## -syntax

````
typedef enum _DXGK_DISPLAY_TECHNOLOGY { 
  DXGK_DT_INVALID  = 0,
  DXGK_DT_OTHER,
  DXGK_DT_LCD,
  DXGK_DT_OLED
} DXGK_DISPLAY_TECHNOLOGY, *PDXGK_DISPLAY_TECHNOLOGY ;
````


## -enum-fields
<dl>

### -field DXGK_DT_INVALID

<dd>
<p>Invalid type.</p>
</dd>

### -field DXGK_DT_OTHER

<dd>
<p>A display technology which does not match one of the defined, valid types.</p>
</dd>

### -field DXGK_DT_LCD

<dd>
<p>A display using an LCD panel.</p>
</dd>

### -field DXGK_DT_OLED

<dd>
<p>A display using an OLED panel.</p>
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
<dt>D3dkmdt.h</dt>
</dl>
</td>
</tr>
</table>