---
UID: NS.gnssdriver.GNSS_DRIVER_REQUEST_DATA
title: GNSS_DRIVER_REQUEST_DATA
author: windows-driver-content
description: This structure contains driver data request information.
old-location: sensors\gnss_driver_request_data.htm
old-project: sensors
ms.assetid: 801FBD9D-304A-41AC-AD28-00DE95DEFE63
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: GNSS_DRIVER_REQUEST_DATA, GNSS_DRIVER_REQUEST_DATA
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
req.alt-api: GNSS_DRIVER_REQUEST_DATA
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

# GNSS_DRIVER_REQUEST_DATA structure



## -description
<p>This structure contains driver data request information.

</p>


## -syntax

````
typedef struct {
  ULONG               Size;
  ULONG               Version;
  GNSS_DRIVER_REQUEST Request;
  ULONG               RequestFlag;
} GNSS_DRIVER_REQUEST_DATA, *PGNSS_DRIVER_REQUEST_DATA;
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

### -field Request

<dd>
<p>The type of request made by the driver.</p>
<p>Represented by the <a href="..\gnssdriver\ne-gnssdriver-gnss-driver-request.md">GNSS_DRIVER_REQUEST</a> enumeration.</p>
</dd>

### -field RequestFlag

<dd>
<p>Additional flags along with this information.</p>
</dd>
</dl>

## -remarks
<p>Based on certain rules, the HLOS  will provide data to the GNSS driver. However, during specific  times, if the GNSS driver determines that it needs  data it can request it without waiting for the HLOS to send it in its normal operation.</p>

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