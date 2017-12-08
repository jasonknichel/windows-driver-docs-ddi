---
UID: NE.gnssdriver.GNSS_AGNSS_REQUEST_TYPE
title: GNSS_AGNSS_REQUEST_TYPE
author: windows-driver-content
description: This enumeration indicates the type of AGNSS injection request represented by the GNSS_AGNSS_REQUEST_PARAM structure.
old-location: sensors\gnss_agnss_request_type.htm
old-project: sensors
ms.assetid: 31293354-D68B-475F-91BD-0504129207A5
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_, FWPS_VSWITCH_EVENT_DISPATCH_TABLE0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GNSS_AGNSS_REQUEST_TYPE
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
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# GNSS_AGNSS_REQUEST_TYPE enumeration



## -description
<p>This enumeration indicates the type of AGNSS injection request represented by the <a href="sensors.gnss_agnss_request_param">GNSS_AGNSS_REQUEST_PARAM</a> structure.</p>


## -syntax

````
typedef enum  { 
  GNSS_AGNSS_TimeInjection      = 0x01,
  GNSS_AGNSS_PositionInjection  = 0x02,
  GNSS_AGNSS_BlobInjection      = 0x03
} GNSS_AGNSS_REQUEST_TYPE;
````


## -enum-fields
<dl>

### -field GNSS_AGNSS_TimeInjection

<dd>
<p>Indicates the injection request is for time injection.</p>
</dd>

### -field GNSS_AGNSS_PositionInjection

<dd>
<p>Indicates the injection request is for position injection.</p>
</dd>

### -field GNSS_AGNSS_BlobInjection

<dd>
<p>Indicates the injection request is for blob injection.</p>
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