---
UID: NS.ksmedia.tagKSCAMERA_EXTENDEDPROP_EVCOMPENSATION
title: tagKSCAMERA_EXTENDEDPROP_EVCOMPENSATION
author: windows-driver-content
description: The EV Compensation Control provides for exposure control that is adjusted by increments of EV compensation steps.
old-location: stream\kscamera_extendedprop_evcompensation.htm
old-project: stream
ms.assetid: C9CF39F2-5081-4B99-BFD1-9F7130B27369
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: tagKSCAMERA_EXTENDEDPROP_EVCOMPENSATION, KSCAMERA_EXTENDEDPROP_EVCOMPENSATION, *PKSCAMERA_EXTENDEDPROP_EVCOMPENSATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCAMERA_EXTENDEDPROP_EVCOMPENSATION
req.alt-loc: Ksmedia.h
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

# tagKSCAMERA_EXTENDEDPROP_EVCOMPENSATION structure



## -description
<p>The <i>EV Compensation Control</i> provides for exposure control that is adjusted by increments of EV compensation steps.</p>


## -syntax

````
typedef struct _KSCAMERA_EXTENDEDPROP_EVCOMPENSATION {
  ULONG     Mode;
  LONG      Min;
  LONG      Max;
  LONG      Value;
  ULONGLONG Reserved;
} KSCAMERA_EXTENDEDPROP_EVCOMPENSATION, *PKSCAMERA_EXTENDEDPROP_EVCOMPENSATION;
````


## -struct-fields
<dl>

### -field Mode

<dd>
<p>Not used. Set to 0.</p>
</dd>

### -field Min

<dd>
<p>The minimum EV compensation supported. This is an absolute EV value.</p>
</dd>

### -field Max

<dd>
<p>The maximum EV compensation supported. This is an absolute EV value.</p>
</dd>

### -field Value

<dd>
<p>EV Compensation in units of steps  selected in the <b>Flags</b> member of <a href="stream.kscamera_extendedprop_header">KSCAMERA_EXTENDEDPROP_HEADER</a>.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved.</p>
</dd>
</dl>

## -remarks
<p><b>Value</b> is assigned a stepping increment. For example, if <b>Min</b> = -2, <b>Max</b> = 2 and the compensation stepping is set as one third step (incremented in units of 1/3 EV compensation), the valid values of EV compensation are -2, -1 2/3, -1 1/3, -1, -2/3, -1/3, 0, 1/3, 2/3, 1, 1 1/3, 1 2/3, and 2.  This corresponds to the <b>Value</b> field as -6, -5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5, 6. As an example, if  <b>Value</b> = -6, then EV compensation = -2, or (-6 * 1/3) = -2.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 8.1.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ksmedia.h (include Ksmedia.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.kscamera_extendedprop_header">KSCAMERA_EXTENDEDPROP_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn567572">KSPROPERTY_CAMERACONTROL_EXTENDED_EVCOMPENSATION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSCAMERA_EXTENDEDPROP_EVCOMPENSATION structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>