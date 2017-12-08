---
UID: NS.scsiscan._SCSISCAN_INFO
title: SCSISCAN_INFO
author: windows-driver-content
description: The SCSISCAN_INFO structure is used as a parameter to DeviceIoControl (described in the Microsoft Windows SDK documentation), when the specified I/O control code is IOCTL_SCSISCAN_GET_INFO.
old-location: image\scsiscan_info.htm
old-project: image
ms.assetid: 5fd9b381-c0e3-45bf-9061-da816da5e29f
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: SCSISCAN_INFO, SCSISCAN_INFO, *PSCSISCAN_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsiscan.h
req.include-header: Scsiscan.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SCSISCAN_INFO
req.alt-loc: scsiscan.h
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
req.product: Windows 10 or later.
---

# SCSISCAN_INFO structure



## -description
<p>The SCSISCAN_INFO structure is used as a parameter to <a href="base.deviceiocontrol">DeviceIoControl</a> (described in the Microsoft Windows SDK documentation), when the specified I/O control code is <a href="..\scsiscan\ni-scsiscan-ioctl-scsiscan-get-info.md">IOCTL_SCSISCAN_GET_INFO</a>.</p>


## -syntax

````
typedef struct _SCSISCAN_INFO {
  ULONG Size;
  ULONG Flags;
  UCHAR PortNumber;
  UCHAR PathId;
  UCHAR TargetId;
  UCHAR Lun;
  UCHAR AdapterName[MAX_STRING];
  ULONG Reserved;
} SCSISCAN_INFO, *PSCSISCAN_INFO;
````


## -struct-fields
<dl>

### -field Size

<dd>
<p>Size, in bytes, of the SCSISCAN_INFO structure.</p>
</dd>

### -field Flags

<dd>
<p>Not used, must be zero.</p>
</dd>

### -field PortNumber

<dd>
<p>SCSI adapter number.</p>
</dd>

### -field PathId

<dd>
<p>Host SCSI ID.</p>
</dd>

### -field TargetId

<dd>
<p>Target SCSI ID.</p>
</dd>

### -field Lun

<dd>
<p>Target logical unit number (LUN).</p>
</dd>

### -field AdapterName

<dd>
<p><i>For internal use only.</i></p>
</dd>

### -field Reserved

<dd>
<p><i>For internal use only.</i></p>
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
<dt>Scsiscan.h (include Scsiscan.h)</dt>
</dl>
</td>
</tr>
</table>