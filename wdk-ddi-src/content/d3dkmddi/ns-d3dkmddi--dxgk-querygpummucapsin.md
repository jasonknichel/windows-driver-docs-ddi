---
UID: NS.d3dkmddi._DXGK_QUERYGPUMMUCAPSIN
title: DXGK_QUERYGPUMMUCAPSIN
author: windows-driver-content
description: The DXGK_QUERYGPUMMUCAPSIN structure holds the index of the adapter being queried.
old-location: display\dxgk_querygpummucapsin.htm
old-project: display
ms.assetid: 8DFD307F-DD4E-4321-AD97-78A5D67687B0
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_QUERYGPUMMUCAPSIN, DXGK_QUERYGPUMMUCAPSIN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_QUERYGPUMMUCAPSIN
req.alt-loc: d3dkmddi.h
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

# DXGK_QUERYGPUMMUCAPSIN structure



## -description
<p>The <b>DXGK_QUERYGPUMMUCAPSIN</b> structure holds the index of the adapter being queried.</p>


## -syntax

````
typedef struct _DXGK_QUERYGPUMMUCAPSIN {
  UINT PhysicalAdapterIndex;
} DXGK_QUERYGPUMMUCAPSIN;
````


## -struct-fields
<dl>

### -field PhysicalAdapterIndex

<dd>
<p>A zero-based physical adapter index (engine ordinal) for which the data is queried.</p>
</dd>
</dl>

## -remarks
<p>To get GpuMmu caps Dxgkrnl calls <a href="display.dxgkddiqueryadapterinfo">DxgkDdiQueryAdapterInfo</a> with the following parameters:</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>