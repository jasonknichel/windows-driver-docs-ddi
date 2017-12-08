---
UID: NF.stiusd.IStiUSD.SetNotificationHandle
title: IStiUSD::SetNotificationHandle
author: windows-driver-content
description: A still image minidriver's IStiUSD::SetNotificationHandle method specifies an event handle that the minidriver should use to inform the caller of device events.
old-location: image\istiusd_setnotificationhandle.htm
old-project: image
ms.assetid: 096e9b7a-fc50-46a2-b67a-7128dba13321
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IStiUSD, SetNotificationHandle, IStiUSD::SetNotificationHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: stiusd.h
req.include-header: Stiusd.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IStiUSD.SetNotificationHandle
req.alt-loc: stiusd.h
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
req.iface: IStiUSD
req.product: Windows 10 or later.
---

# IStiUSD::SetNotificationHandle method



## -description
<p>A still image minidriver's <b>IStiUSD::SetNotificationHandle</b> method specifies an event handle that the minidriver should use to inform the caller of device events.</p>


## -syntax

````
HRESULT SetNotificationHandle(
   HANDLE hEvent
);
````


## -parameters
<dl>

### -param hEvent 

<dd>
<p>Caller-supplied handle to a Win32 event, created by calling <b>CreateEvent</b>.</p>
</dd>
</dl>

## -returns
<p>If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.</p>

## -remarks
<p>If the driver (and device) supports asynchronous notification of <a href="https://msdn.microsoft.com/5f9be89c-8442-4894-b2f6-a4d3558464bf">Still Image Device Events</a>, the minidriver's <b>IStiUSD::SetNotificationHandle</b> method is the means by which the event monitor requests the driver to notify it when an event occurs.</p>

<p>If <i>hEvent</i> is an event handle, the <b>IStiUSD::SetNotificationHandle</b> method should store the handle and use it as an input argument to <b>SetEvent</b> (described in the Microsoft Windows SDK documentation). The driver should call <b>SetEvent</b> each time a device event is detected, to notify the event monitor that an event has occurred.</p>

<p>If <i>hEvent</i> is <b>NULL</b>, the method should disable notification of device events.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Stiusd.h (include Stiusd.h)</dt>
</dl>
</td>
</tr>
</table>