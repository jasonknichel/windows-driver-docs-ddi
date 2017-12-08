---
UID: NS.gnssdriver.PGNSS_CP_NI_INFO
title: PGNSS_CP_NI_INFO
author: windows-driver-content
description: This structure contains CP NI information.
old-location: sensors\gnss_cp_ni_info.htm
old-project: sensors
ms.assetid: FC05C59C-F8B5-4573-A1F0-722A25BDA151
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: PGNSS_CP_NI_INFO, GNSS_CP_NI_INFO, *PGNSS_CP_NI_INFO
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
req.alt-api: GNSS_CP_NI_INFO
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

# PGNSS_CP_NI_INFO structure



## -description
<p>This structure contains CP NI information.</p>


## -syntax

````
typedef struct {
  ULONG Size;
  ULONG Version;
  WCHAR RequestorId[MAX_PATH];
  WCHAR NotificationText[MAX_PATH];
} GNSS_CP_NI_INFO, *PGNSS_CP_NI_INFO;
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

### -field RequestorId[MAX_PATH]

<dd>
<p>Requestor ID.</p>
<p>This will be displayed on the notification dialog to the user. The GNSS driver must provide a UNICODE string that is decoded per the encoding scheme required by the mobile operator.</p>
</dd>

### -field NotificationText[MAX_PATH]

<dd>
<p>Name of the client that requests the location of the device.</p>
<p>This will be displayed on the notification dialog to the user. The GNSS Driver must provide a UNICODE string that is decoded per the encoding scheme required by the mobile operator.</p>
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