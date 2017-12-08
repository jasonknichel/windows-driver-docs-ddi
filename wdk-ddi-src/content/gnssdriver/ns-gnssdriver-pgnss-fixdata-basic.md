---
UID: NS.gnssdriver.PGNSS_FIXDATA_BASIC
title: PGNSS_FIXDATA_BASIC
author: windows-driver-content
description: This structure defines basic position information.
old-location: sensors\gnss_fixdata_basic.htm
old-project: sensors
ms.assetid: D293366B-13FA-438E-BEBD-1F0EAA693400
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: PGNSS_FIXDATA_BASIC, GNSS_FIXDATA_BASIC, *PGNSS_FIXDATA_BASIC
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
req.alt-api: GNSS_FIXDATA_BASIC
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

# PGNSS_FIXDATA_BASIC structure



## -description
<p>This structure defines basic position information.</p>


## -syntax

````
typedef struct {
  ULONG  Size;
  ULONG  Version;
  double Latitude;
  double Longitude;
  double Altitude;
  double Speed;
  double Heading;
} GNSS_FIXDATA_BASIC, *PGNSS_FIXDATA_BASIC;
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

### -field Latitude

<dd>
<p>Latitude value. Valid range is -180.0 to + 180.0. NaN indicates unavailable.</p>
</dd>

### -field Longitude

<dd>
<p>Longitude value. Valid range is -90.0 to + 90.0. NaN indicates unavailable.</p>
</dd>

### -field Altitude

<dd>
<p>Altitude value in meters (in relation to sea level). NaN indicates unavailable.</p>
</dd>

### -field Speed

<dd>
<p>Speed in meters per second. Zero or positive value. NaN indicates unavailable.</p>
</dd>

### -field Heading

<dd>
<p>Heading/direction in degrees. Valid range is 0 to 360. Zero indicates true north. NaN indicates unavailable.</p>
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