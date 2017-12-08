---
UID: NS.ntddvdeo._VIDEO_POINTER_POSITION
title: VIDEO_POINTER_POSITION
author: windows-driver-content
description: The VIDEO_POINTER_POSITION structure contains the location of the screen pointer relative to the top left corner of the screen.
old-location: display\video_pointer_position.htm
old-project: display
ms.assetid: 07586be9-a8bc-4149-8037-7b649a75a818
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: VIDEO_POINTER_POSITION, VIDEO_POINTER_POSITION, *PVIDEO_POINTER_POSITION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VIDEO_POINTER_POSITION
req.alt-loc: Ntddvdeo.h
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

# VIDEO_POINTER_POSITION structure



## -description
<p>The VIDEO_POINTER_POSITION structure contains the location of the screen pointer relative to the top left corner of the screen.</p>


## -syntax

````
typedef struct _VIDEO_POINTER_ATTRIBUTES {
  SHORT Column;
  SHORT Row;
} VIDEO_POINTER_POSITION, *PVIDEO_POINTER_POSITION;
````


## -struct-fields
<dl>

### -field Column

<dd>
<p>Specifies the column location of the pointer in pixels, starting from the top left corner of the screen.</p>
</dd>

### -field Row

<dd>
<p>Specifies the row location of the pointer in pixels, starting from the top left corner of the screen.</p>
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
<dt>Ntddvdeo.h (include Ntddvdeo.h)</dt>
</dl>
</td>
</tr>
</table>