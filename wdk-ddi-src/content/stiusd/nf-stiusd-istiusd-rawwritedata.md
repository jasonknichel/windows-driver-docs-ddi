---
UID: NF.stiusd.IStiUSD.RawWriteData
title: IStiUSD::RawWriteData
author: windows-driver-content
description: A still image minidriver's IStiUSD::RawWriteData method writes data to a still image device.
old-location: image\istiusd_rawwritedata.htm
old-project: image
ms.assetid: 82700669-b98f-486c-a7a6-cd7138300f11
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IStiUSD, RawWriteData, IStiUSD::RawWriteData
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
req.alt-api: IStiUSD.RawWriteData
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

# IStiUSD::RawWriteData method



## -description
<p>A still image minidriver's <b>IStiUSD::RawWriteData</b> method writes data to a still image device.</p>


## -syntax

````
HRESULT RawWriteData(
   LPVOID       lpBuffer,
   DWORD        dwNumberOfBytes,
   LPOVERLAPPED lpOverlapped
);
````


## -parameters
<dl>

### -param lpBuffer 

<dd>
<p>Caller-supplied pointer to a buffer containing data to be sent to the device.</p>
</dd>

### -param dwNumberOfBytes 

<dd>
<p>Caller-supplied number of bytes to be written. This is the number of bytes in the buffer pointed to by <i>lpBuffer</i>.</p>
</dd>

### -param lpOverlapped 

<dd>
<p>Optional, caller-supplied pointer to an OVERLAPPED structure (described in the Microsoft Windows SDK documentation).</p>
</dd>
</dl>

## -returns
<p>If the operation succeeds, the method should return S_OK. Otherwise, it should return one of the STIERR-prefixed error codes defined in <i>stierr.h</i>.</p>

## -remarks
<p>A still image minidriver typically implements this method by calling <b>WriteFile</b> (described in the Windows SDK documentation).</p>

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

## -see-also
<dl>
<dt>
<a href="image.istidevice_rawwritedata">IStiDevice::RawWriteData</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IStiUSD::RawWriteData method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>