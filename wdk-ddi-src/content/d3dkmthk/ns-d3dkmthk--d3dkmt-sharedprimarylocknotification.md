---
UID: NS.d3dkmthk._D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION
title: D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION
author: windows-driver-content
description: The D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION structure describes the shared primary surface that an application is about to lock.
old-location: display\d3dkmt_sharedprimarylocknotification.htm
old-project: display
ms.assetid: 4e7766bb-eb5b-4f79-b9b8-89f7dcb98569
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION, D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION
req.alt-loc: d3dkmthk.h
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

# D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION structure



## -description
<p>The D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION structure describes the shared primary surface that an application is about to lock.</p>


## -syntax

````
typedef struct _D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION {
  LUID                           AdapterLuid;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  RECTL                          LockRect;
} D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION;
````


## -struct-fields
<dl>

### -field AdapterLuid

<dd>
<p>[in] The locally unique identifier (<a href="kernel.luid">LUID</a>) of the graphics adapter on which the GDI shared primary surface exists. </p>
</dd>

### -field VidPnSourceId

<dd>
<p>[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology on which the GDI shared primary surface exists. </p>
</dd>

### -field LockRect

<dd>
<p>[in] A <a href="display.rectl">RECTL</a> structure that indicates the upper-left and lower-right points of a rectangle on the shared primary surface; the operating system disables all sprites that intersect with this rectangle. If the OpenGL ICD specifies zero for each member of RECTL, the operating system disables all sprites on the shared primary surface.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsharedprimarylocknotification.md">D3DKMTSharedPrimaryLockNotification</a>
</dt>
<dt>
<a href="display.rectl">RECTL</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SHAREDPRIMARYLOCKNOTIFICATION structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>