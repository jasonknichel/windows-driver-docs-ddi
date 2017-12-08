---
UID: NS.msviddrv.tag_video_configure_parms
title: tag_video_configure_parms
author: windows-driver-content
description: .
old-location: stream\videoconfigparms.htm
old-project: stream
ms.assetid: 58FE3B56-AFC6-46DE-BBE1-CCFA8FF1390A
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: tag_video_configure_parms, VIDEOCONFIGPARMS, *LPVIDEOCONFIGPARMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: msviddrv.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VIDEOCONFIGPARMS
req.alt-loc: Msviddrv.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.iface: 
---

# tag_video_configure_parms structure



## -description
<p></p>


## -syntax

````
typedef struct tag_video_configure_parms {
  LPDWORD lpdwReturn;
  LPVOID  lpData1;
  DWORD   dwSize1;
  LPVOID  lpData2;
  DWORD   dwSize2;
} VIDEOCONFIGPARMS, *LPVIDEOCONFIGPARMS;
````


## -struct-fields
<dl>

### -field lpdwReturn

<dd>
<p>Specifies the return parameter from the configure MSG.</p>
</dd>

### -field lpData1

<dd>
<p>Specifies a pointer to data 1.</p>
</dd>

### -field dwSize1

<dd>
<p>Specifies the size of data buffer 1.</p>
</dd>

### -field lpData2

<dd>
<p>Specifies a pointer to data 2.</p>
</dd>

### -field dwSize2

<dd>
<p>Specifies the size of data buffer 2.</p>
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
<dt>Msviddrv.h</dt>
</dl>
</td>
</tr>
</table>