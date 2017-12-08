---
UID: NS.ntddstor._STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR
title: STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR
author: windows-driver-content
description: The output buffer for the StorageDeviceIoCapabilityProperty as defined in STORAGE_PROPERTY_ID.
old-location: storage\storage_device_io_capability_descriptor.htm
old-project: storage
ms.assetid: 98377F8F-62C8-4E8F-838B-A63DC63E4A0C
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR, STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR, *PSTORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR
req.alt-loc: ntddstor.h
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

# STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR structure



## -description
<p>The output buffer for the StorageDeviceIoCapabilityProperty as defined in <a href="storage.storage_property_id">STORAGE_PROPERTY_ID</a>.</p>


## -syntax

````
typedef struct _STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR {
  ULONG Version;
  ULONG Size;
  ULONG LunMaxIoCount;
  ULONG AdapterMaxIoCount;
} STORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR, *PSTORAGE_DEVICE_IO_CAPABILITY_DESCRIPTOR;
````


## -struct-fields
<dl>

### -field Version

<dd>
<p>The version of this structure. The Size serves as the version.</p>
</dd>

### -field Size

<dd>
<p>The size of this structure.</p>
</dd>

### -field LunMaxIoCount

<dd>
<p>The logical unit number (LUN) max outstanding I/O count.</p>
</dd>

### -field AdapterMaxIoCount

<dd>
<p>The adapter max outstanding I/O count.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Server</p>
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
<dt>Ntddstor.h</dt>
</dl>
</td>
</tr>
</table>