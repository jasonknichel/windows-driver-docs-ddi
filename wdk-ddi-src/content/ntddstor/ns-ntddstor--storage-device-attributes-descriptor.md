---
UID: NS.ntddstor._STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR
title: STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR
author: windows-driver-content
description: The STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR structure is used to retrieve the attributes information for a device.
old-location: storage\storage_device_attributes_descriptor.htm
old-project: storage
ms.assetid: DA8434EF-6163-4D07-A81D-D1AC2D55BFB4
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR, STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR, *PSTORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR
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

# STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR structure



## -description
<p>The STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR structure is used to retrieve the attributes information for a  device.</p>


## -syntax

````
typedef struct _STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR {
  ULONG   Version;
  ULONG   Size;
  ULONG64 Attributes;
} STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR, *PSTORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR;
````


## -struct-fields
<dl>

### -field Version

<dd>
<p>Contains the version of the data reported. </p>
</dd>

### -field Size

<dd>
<p>Indicates the quantity of data reported, in bytes. This is the <code>sizeof(STORAGE_DEVICE_ATTRIBUTES_DESCRIPTOR)</code>.</p>
</dd>

### -field Attributes

<dd>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="STORAGE_ATTRIBUTE_BYTE_ADDRESSABLE_IO"></a><a id="storage_attribute_byte_addressable_io"></a><dl>

### -field STORAGE_ATTRIBUTE_BYTE_ADDRESSABLE_IO


### -field 0x01

</dl>
</td>
<td width="60%">
<p>Attribute that indicates a storage device supports byte addressable IO.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="STORAGE_ATTRIBUTE_BLOCK_IO"></a><a id="storage_attribute_block_io"></a><dl>

### -field STORAGE_ATTRIBUTE_BLOCK_IO


### -field 0x02

</dl>
</td>
<td width="60%">
<p>Attribute that indicates a storage device supports block IO.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="STORAGE_ATTRIBUTE_DYNAMIC_PERSISTENCE"></a><a id="storage_attribute_dynamic_persistence"></a><dl>

### -field STORAGE_ATTRIBUTE_DYNAMIC_PERSISTENCE


### -field 0x04

</dl>
</td>
<td width="60%">
<p>Attribute that indicates that persistence of data on storage device may change.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="STORAGE_ATTRIBUTE_VOLATILE"></a><a id="storage_attribute_volatile"></a><dl>

### -field STORAGE_ATTRIBUTE_VOLATILE


### -field 0x08

</dl>
</td>
<td width="60%">
<p>Attribute that indicates a storage device is volatile and does not support persistence of data.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="STORAGE_ATTRIBUTE_ASYNC_EVENT_NOTIFICATION"></a><a id="storage_attribute_async_event_notification"></a><dl>

### -field STORAGE_ATTRIBUTE_ASYNC_EVENT_NOTIFICATION


### -field 0x10

</dl>
</td>
<td width="60%">
<p>Reserved</p>
</td>
</tr>
<tr>
<td width="40%"><a id="STORAGE_ATTRIBUTE_PERF_SIZE_INDEPENDENT"></a><a id="storage_attribute_perf_size_independent"></a><dl>

### -field STORAGE_ATTRIBUTE_PERF_SIZE_INDEPENDENT


### -field 0x20

</dl>
</td>
<td width="60%">
<p>Attribute that indicates a storage device has IO performance independent of IO sizes.</p>
</td>
</tr>
</table>
<p> </p>
</dd>
</dl>

## -remarks


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
<dt>Ntddstor.h (include Ntddstor.h)</dt>
</dl>
</td>
</tr>
</table>