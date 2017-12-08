---
UID: NS.d3dkmddi._DXGK_POWER_COMPONENT_MAPPING
title: DXGK_POWER_COMPONENT_MAPPING
author: windows-driver-content
description: Used in the DXGK_POWER_RUNTIME_COMPONENT.ComponentMapping member to define the standard component types of the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys) that describe the power component.
old-location: display\dxgk_power_component_mapping.htm
old-project: display
ms.assetid: 6aa00a36-f7a2-4e49-bbd9-1a1ae3592951
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_POWER_COMPONENT_MAPPING, DXGK_POWER_COMPONENT_MAPPING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_POWER_COMPONENT_MAPPING
req.alt-loc: D3dkmddi.h
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

# DXGK_POWER_COMPONENT_MAPPING structure



## -description
<p>Used in the <a href="..\d3dkmddi\ns-d3dkmddi--dxgk-power-runtime-component.md">DXGK_POWER_RUNTIME_COMPONENT</a>.<b>ComponentMapping</b> member to define the standard component types of the Microsoft DirectX graphics kernel subsystem (Dxgkrnl.sys) that describe the power component.</p>


## -syntax

````
typedef struct _DXGK_POWER_COMPONENT_MAPPING {
  DXGK_POWER_COMPONENT_TYPE ComponentType;
  union {
    struct DXGK_POWER_COMPONENT_ENGINE_DESC {
      UINT NodeIndex;
    } EngineDesc;
    struct DXGK_POWER_COMPONENT_MONITOR_REFRESH_DESC {
      UINT VidPnSourceID;
    } MonitorRefreshDesc;
    struct DXGK_POWER_COMPONENT_MONITOR_DESC {
      UINT VidPnTargetID;
    } MonitorDesc;
  };
} DXGK_POWER_COMPONENT_MAPPING;
````


## -struct-fields
<dl>

### -field ComponentType

<dd>
<p>A <a href="..\d3dkmddi\ne-d3dkmddi--dxgk-power-component-type.md">DXGK_POWER_COMPONENT_TYPE</a>-typed value that indicates the power component type that is reported by the display miniport driver to the DirectX graphics kernel subsystem.</p>
</dd>

### -field EngineDesc

<dd>
<dl>

### -field NodeIndex

<dd>
<p>The index of the engine (node).</p>
</dd>
</dl>
</dd>

### -field MonitorRefreshDesc

<dd>
<dl>

### -field VidPnSourceID

<dd>
<p>An identifier of one of the video present sources associated with the video present network object.</p>
</dd>
</dl>
</dd>

### -field MonitorDesc

<dd>
<dl>

### -field VidPnTargetID

<dd>
<p>An identifier of one of the video present targets associated with the VidPN object.</p>
</dd>
</dl>
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
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ne-d3dkmddi--dxgk-power-component-type.md">DXGK_POWER_COMPONENT_TYPE</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi--dxgk-power-runtime-component.md">DXGK_POWER_RUNTIME_COMPONENT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_POWER_COMPONENT_MAPPING structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>