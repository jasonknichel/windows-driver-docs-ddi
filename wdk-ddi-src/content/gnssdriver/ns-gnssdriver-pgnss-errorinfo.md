---
UID: NS.gnssdriver.PGNSS_ERRORINFO
title: PGNSS_ERRORINFO
author: windows-driver-content
description: This structure contains error information.
old-location: sensors\gnss_errorinfo.htm
old-project: sensors
ms.assetid: 754CD1DD-88E6-4E02-8E24-1939222FE326
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: PGNSS_ERRORINFO, GNSS_ERRORINFO, *PGNSS_ERRORINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GNSS_ERRORINFO
req.alt-loc: gnssdriver.h
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

# PGNSS_ERRORINFO structure



## -description
<p>This structure contains error information.</p>


## -syntax

````
typedef struct {
  ULONG Size;
  ULONG Version;
  ULONG ErrorCode;
  BOOL  IsRecoverable;
  WCHAR ErrorDescription[256];
  BYTE  Unused[512];
} GNSS_ERRORINFO, *PGNSS_ERRORINFO;
````


## -struct-fields
<dl>

### -field Size

<dd>
<p>Structure size.</p>
</dd>

### -field Version

<dd>
<p>Version number.</p>
</dd>

### -field ErrorCode

<dd>
<p>Win32 Error Code associated with the event.</p>
<p>The IHV can pick the error that is most similar to what needs to be reported (for example, E_OUTOFMEMORY). The IHV can also use FACILITY_ITF to create custom errors. For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=525284">Codes in FACILITY_ITF</a>.
</p>
</dd>

### -field IsRecoverable

<dd>
<p>If FALSE, the GNSS adapter needs to reset it’s state with the GNSS driver.</p>
</dd>

### -field ErrorDescription[256]

<dd>
<p>Clear-text description of the error (not-localized) that is used for diagnostic purpose only.</p>
</dd>

### -field Unused[512]

<dd>
<p>Padding buffer.</p>
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
<dt>Gnssdriver.h</dt>
</dl>
</td>
</tr>
</table>