---
UID: NS.gnssdriver.PGNSS_FIXDATA_ACCURACY
title: PGNSS_FIXDATA_ACCURACY
author: windows-driver-content
description: This structure defines the accuracy details of a fix.
old-location: sensors\gnss_fixdata_accuracy.htm
old-project: sensors
ms.assetid: 3C08FE5D-1385-4FE3-98C9-9FC530C6C755
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: PGNSS_FIXDATA_ACCURACY, GNSS_FIXDATA_ACCURACY, *PGNSS_FIXDATA_ACCURACY
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
req.alt-api: GNSS_FIXDATA_ACCURACY
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

# PGNSS_FIXDATA_ACCURACY structure



## -description
<p>This structure defines the accuracy details of a fix.</p>


## -syntax

````
typedef struct {
  ULONG Size;
  ULONG Version;
  ULONG HorizontalAccuracy;
  ULONG HorizontalErrorMajorAxis;
  ULONG HorizontalErrorMinorAxis;
  ULONG HorizontalErrorAngle;
  ULONG HeadingAccuracy;
  ULONG AltitudeAccuracy;
  ULONG SpeedAccuracy;
  ULONG HorizontalConfidence;
  ULONG HeadingConfidence;
  ULONG AltitudeConfidence;
  ULONG SpeedConfidence;
  float PositionDilutionOfPrecision;
  float HorizontalDilutionOfPrecision;
  float VerticalDilutionOfPrecision;
} GNSS_FIXDATA_ACCURACY, *PGNSS_FIXDATA_ACCURACY;
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

### -field HorizontalAccuracy

<dd>
<p>Accuracy reported with 95% confidence.</p>
</dd>

### -field HorizontalErrorMajorAxis

<dd>
<p>Horizontal uncertainty ellipse semi-major axis with  95% confidence accuracy.</p>
</dd>

### -field HorizontalErrorMinorAxis

<dd>
<p>Horizontal uncertainty ellipse semi-minor axis with  95% confidence accuracy.</p>
</dd>

### -field HorizontalErrorAngle

<dd>
<p>Horizontal uncertainty ellipse orientation angle with  95% confidence accuracy.</p>
</dd>

### -field HeadingAccuracy

<dd>
<p>Reserved, do not use.</p>
</dd>

### -field AltitudeAccuracy

<dd>
<p>Reserved, do not use.</p>
</dd>

### -field SpeedAccuracy

<dd>
<p>Reserved, do not use.</p>
</dd>

### -field HorizontalConfidence

<dd>
<p>Reserved, do not use.</p>
</dd>

### -field HeadingConfidence

<dd>
<p>Reserved, do not use.</p>
</dd>

### -field AltitudeConfidence

<dd>
<p>Reserved, do not use.</p>
</dd>

### -field SpeedConfidence

<dd>
<p>Reserved, do not use.</p>
</dd>

### -field PositionDilutionOfPrecision

<dd>
<p>Position dilution of precision (PDOP).</p>
<p>Satellite-based positions with a dilution of precision (DOP) value of 0 or a DOP value higher than 10 may be filtered by the GNSS adapter.</p>
</dd>

### -field HorizontalDilutionOfPrecision

<dd>
<p>Horizontal dilution of precision (HDOP).</p>
</dd>

### -field VerticalDilutionOfPrecision

<dd>
<p>Vertical dilution of precision (VDOP).</p>
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