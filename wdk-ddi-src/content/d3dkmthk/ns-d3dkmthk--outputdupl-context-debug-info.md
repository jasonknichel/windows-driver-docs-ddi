---
UID: NS.d3dkmthk._OUTPUTDUPL_CONTEXT_DEBUG_INFO
title: OUTPUTDUPL_CONTEXT_DEBUG_INFO
author: windows-driver-content
description: Reserved for system use. Do not use in your driver.
old-location: display\outputdupl_context_debug_info.htm
old-project: display
ms.assetid: 9b8915a2-e62e-474a-ac03-199ce6d252c2
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: OUTPUTDUPL_CONTEXT_DEBUG_INFO, OUTPUTDUPL_CONTEXT_DEBUG_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OUTPUTDUPL_CONTEXT_DEBUG_INFO
req.alt-loc: D3dkmthk.h
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

# OUTPUTDUPL_CONTEXT_DEBUG_INFO structure



## -description
<p>Reserved for system use. Do not use in your driver.</p>


## -syntax

````
typedef struct _OUTPUTDUPL_CONTEXT_DEBUG_INFO {
  OUTPUTDUPL_CONTEXT_DEBUG_STATUS Status;
  HANDLE                          ProcessID;
  UINT32                          AccumulatedPresents;
  LARGE_INTEGER                   LastPresentTime;
  LARGE_INTEGER                   LastMouseTime;
  CHAR                            ProcessName[DXGK_DIAG_PROCESS_NAME_LENGTH];
} OUTPUTDUPL_CONTEXT_DEBUG_INFO;
````


## -struct-fields
<dl>

### -field Status

<dd></dd>

### -field ProcessID

<dd></dd>

### -field AccumulatedPresents

<dd></dd>

### -field LastPresentTime

<dd></dd>

### -field LastMouseTime

<dd></dd>

### -field ProcessName

<dd></dd>
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
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>