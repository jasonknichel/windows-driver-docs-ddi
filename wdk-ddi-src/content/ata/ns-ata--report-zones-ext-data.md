---
UID: NS.ata._REPORT_ZONES_EXT_DATA
title: REPORT_ZONES_EXT_DATA
author: windows-driver-content
description: Note  This structure is for internal use only and should not be called from your code. .
old-location: storage\report_zones_ext_data.htm
old-project: storage
ms.assetid: 0c6b4b7c-548d-42c0-af9b-cf0d65bf2e45
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: REPORT_ZONES_EXT_DATA, REPORT_ZONES_EXT_DATA, *PREPORT_ZONES_EXT_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ata.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: REPORT_ZONES_EXT_DATA
req.alt-loc: ata.h
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
---

# REPORT_ZONES_EXT_DATA structure



## -description
<p>
<div class="alert"><b>Note</b>  This  structure is for internal use only and should not be called from your code.</div>
<div> </div>
</p>


## -syntax

````
typedef struct _REPORT_ZONES_EXT_DATA {
  ULONG     ZoneListLength;
  UCHAR     SAME  :4;
  UCHAR     Reserved0  :4;
  UCHAR     Reserved1[3];
  ULONGLONG MaxLBA  :48;
  ULONGLONG Reserved2  :16;
  UCHAR     Reserved3[48];
} REPORT_ZONES_EXT_DATA, *PREPORT_ZONES_EXT_DATA;
````


## -struct-fields
<dl>

### -field ZoneListLength

<dd>
<p>N/A</p>
</dd>

### -field SAME

<dd>
<p>N/A</p>
</dd>

### -field Reserved0

<dd>
<p>Reserved for future use.</p>
</dd>

### -field Reserved1

<dd>
<p>Reserved for future use.</p>
</dd>

### -field MaxLBA

<dd>
<p>N/A</p>
</dd>

### -field Reserved2

<dd>
<p>Reserved for future use.</p>
</dd>

### -field Reserved3

<dd>
<p>Reserved for future use.</p>
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
<dt>Ata.h</dt>
</dl>
</td>
</tr>
</table>