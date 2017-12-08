---
UID: NS.d3dumddi._D3DDDICB_DESTROYHWQUEUE
title: D3DDDICB_DESTROYHWQUEUE
author: windows-driver-content
description: A structure that holds information to destroy a hardware queue.
old-location: display\d3dddicb_destroyhwqueue.htm
old-project: display
ms.assetid: 80735E36-C483-4CD8-AB53-873BA5E997D0
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DDDICB_DESTROYHWQUEUE, D3DDDICB_DESTROYHWQUEUE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDICB_DESTROYHWQUEUE
req.alt-loc: d3dumddi.h
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

# D3DDDICB_DESTROYHWQUEUE structure



## -description
<p>A structure that holds information to destroy a hardware queue.</p>


## -syntax

````
typedef struct _D3DDDICB_DESTROYHWQUEUE {
  HANDLE hHwQueue;
} D3DDDICB_DESTROYHWQUEUE;
````


## -struct-fields
<dl>

### -field hHwQueue

<dd>
<p>Handle to the queue to destroy.</p>
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
<dt>D3dumddi.h</dt>
</dl>
</td>
</tr>
</table>