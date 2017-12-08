---
UID: NF.wdfcore.WDF_ABS_TIMEOUT_IN_MS
title: WDF_ABS_TIMEOUT_IN_MS
author: windows-driver-content
description: The WDF_ABS_TIMEOUT_IN_MS function converts a specified number of milliseconds to an absolute time value.
old-location: wdf\wdf_abs_timeout_in_ms.htm
old-project: wdf
ms.assetid: 271d2b39-53a3-454b-97d0-0bace8504b48
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_ABS_TIMEOUT_IN_MS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcore.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_ABS_TIMEOUT_IN_MS
req.alt-loc: None,None.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: None
req.dll: 
req.irql: Any level
req.iface: 
req.product: Windows 10 or later.
---

# WDF_ABS_TIMEOUT_IN_MS function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WDF_ABS_TIMEOUT_IN_MS</b> function converts a specified number of milliseconds to an absolute time value.</p>


## -syntax

````
LONGLONG WDF_ABS_TIMEOUT_IN_MS(
  _In_ ULONGLONG Time
);
````


## -parameters
<dl>

### -param Time [in]

<dd>
<p>The number of milliseconds to convert.</p>
</dd>
</dl>

## -returns
<p><b>WDF_ABS_TIMEOUT_IN_MS</b> returns the absolute time value, in system time units (100-nanosecond intervals), that represents the number of milliseconds that <i>Time</i> specifies.</p>

## -remarks
<p>An absolute time value is a time value that specifies a specific date and time. Absolute times are relative to 00:00, January 1, 1601. If an absolute time value is passed to the system, the system adds the absolute time value to the time value that represents 00:00, January 1, 1601.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfcore.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>None</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfcore\nf-wdfcore-wdf-rel-timeout-in-ms.md">WDF_REL_TIMEOUT_IN_MS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_ABS_TIMEOUT_IN_MS function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>