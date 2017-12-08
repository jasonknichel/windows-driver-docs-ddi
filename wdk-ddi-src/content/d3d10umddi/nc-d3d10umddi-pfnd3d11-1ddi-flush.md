---
UID: NC.d3d10umddi.PFND3D11_1DDI_FLUSH
title: PFND3D11_1DDI_FLUSH
author: windows-driver-content
description: Submits outstanding hardware commands that are in the hardware command buffer to the display miniport driver. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\flush_d3d11_1_.htm
old-project: display
ms.assetid: 6f4bda19-2d51-4058-ba68-cbb5deb44a54
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Flush(D3D11_1)
req.alt-loc: d3d10umddi.h
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

# PFND3D11_1DDI_FLUSH callback



## -description
<p>Submits outstanding hardware commands that are in the hardware command buffer to the display miniport driver. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.</p>


## -prototype

````
PFND3D11_1DDI_FLUSH Flush(D3D11_1);

BOOL APIENTRY* Flush(D3D11_1)(
  _In_ D3D10DDI_HDEVICE hDevice,
  _In_ UINT             FlushFlags
)
{ ... }
````


## -parameters
<dl>

### -param hDevice [in]

<dd>
<p> A handle to the display device (graphics context).</p>
</dd>

### -param FlushFlags [in]

<dd>
<p> A value from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11-1-ddi-flush-flags.md">D3D11_1_DDI_FLUSH_FLAGS</a> enumeration that indicates whether the driver should  continue to submit command buffers if there have been no new commands.</p>
</dd>
</dl>

## -returns
<p>Returns <b>TRUE</b> if the hardware commands were successfully flushed. Otherwise returns <b>FALSE</b>.</p>

## -remarks
<p>After the <i>Flush(D3D11_1)</i> function completes, all previously issued commands no longer depend on actions that occur within the application's user-mode context. In addition, applications can safely suspend themselves without blocking rendering until the kernel restarts them (such as, when an asynchronous query is used).</p>

<p>The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-seterror-cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>Flush(D3D11_1)</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
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
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10-1ddi-devicefuncs.md">D3D10_1DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d11-1-ddi-flush-flags.md">D3D11_1_DDI_FLUSH_FLAGS</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-seterror-cb.md">pfnSetErrorCb</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_FLUSH callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>