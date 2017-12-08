---
UID: NE.wudfddi_types._WDF_CALLBACK_CONSTRAINT
title: WDF_CALLBACK_CONSTRAINT
author: windows-driver-content
description: WDF_CALLBACK_CONSTRAINT enumeration
old-location: wdf\wdf_callback_constraint.htm
old-project: wdf
ms.assetid: 118a9dcc-8dd4-454a-bab2-1558821781a7
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WRITE_REGISTER_USHORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi_types.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: WDF_CALLBACK_CONSTRAINT
req.alt-loc: wudfddi_types.h
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

# WDF_CALLBACK_CONSTRAINT enumeration



## -description

## -syntax

````
typedef enum _WDF_CALLBACK_CONSTRAINT { 
  None              = 0,
  WdfDeviceLevel    = 1,
  WdfLevelReserved  = 2
} WDF_CALLBACK_CONSTRAINT;
````


## -enum-fields
<dl>

### -field None

<dd>
<p>No callback functions into the driver are synchronized.  The driver must handle all synchronization.</p>
</dd>

### -field WdfDeviceLevel

<dd>
<p>All callback functions into the driver that are associated with the device are synchronized, including all callback functions that are associated with I/O queues. Only one event handler that is associated with the device can run at any given time.</p>
</dd>

### -field WdfLevelReserved

<dd>
<p>Reserved.</p>
</dd>
</dl>

## -remarks
<p>Note that the above locking models apply only for I/O (that is, open, read, write, and device I/O control) operations and not for Plug and Play (PnP) and power management notifications. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>1.9</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wudfddi_types.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>