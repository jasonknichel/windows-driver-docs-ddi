---
UID: NS.d3dkmthk._D3DKMT_RENDERFLAGS
title: D3DKMT_RENDERFLAGS
author: windows-driver-content
description: The D3DKMT_RENDERFLAGS structure identifies the type of command buffer to be rendered in a call to the D3DKMTRender function.
old-location: display\d3dkmt_renderflags.htm
old-project: display
ms.assetid: 6a25528c-063b-4cd5-963d-82245009bb48
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_RENDERFLAGS, D3DKMT_RENDERFLAGS
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
req.alt-api: D3DKMT_RENDERFLAGS
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

# D3DKMT_RENDERFLAGS structure



## -description
<p>The D3DKMT_RENDERFLAGS structure identifies the type of command buffer to be rendered in a call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtrender.md">D3DKMTRender</a> function.</p>


## -syntax

````
typedef struct _D3DKMT_RENDERFLAGS {
  UINT ResizeCommandBuffer  :1;
  UINT ResizeAllocationList  :1;
  UINT ResizePatchLocationList  :1;
  UINT NullRendering  :1;
  UINT PresentRedirected  :1;
  UINT RenderKm  :1;
  UINT Reserved  :26;
} D3DKMT_RENDERFLAGS;
````


## -struct-fields
<dl>

### -field ResizeCommandBuffer

<dd>
<p>A UINT value that specifies whether to resize the command buffer. The driver puts the requested size in the <b>NewCommandBufferSize</b> member of the <a href="..\d3dkmthk\ns-d3dkmthk--d3dkmt-render.md">D3DKMT_RENDER</a> structure. Because a resize request by the driver might not be possible, the driver must always verify the size value that is returned.</p>
<p>Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).</p>
</dd>

### -field ResizeAllocationList

<dd>
<p>A UINT value that specifies whether to resize the allocation list. The driver puts the requested number of elements in the <b>NewAllocationListSize</b> member of the <a href="..\d3dkmthk\ns-d3dkmthk--d3dkmt-render.md">D3DKMT_RENDER</a> structure. Because a resize request by the driver might not be possible, the driver must always verify the size value that is returned.</p>
<p>Setting this member is equivalent to setting the second bit of a 32-bit value (0x00000002).</p>
</dd>

### -field ResizePatchLocationList

<dd>
<p>A UINT value that specifies whether to resize the patch-location list. The driver puts the requested number of elements in the <b>NewPatchLocationListSize</b> member of the <a href="..\d3dkmthk\ns-d3dkmthk--d3dkmt-render.md">D3DKMT_RENDER</a> structure. Because a resize request by the driver might not be possible, the driver must always verify the size value that is returned.</p>
<p>Setting this member is equivalent to setting the third bit of a 32-bit value (0x00000004).</p>
</dd>

### -field NullRendering

<dd>
<p>A UINT value that specifies whether the graphics processing unit (GPU) should process any commands for the rendering context. The <b>NullRendering</b> bit-field flag is set to inform the GPU not to process any commands for the rendering context. The <b>NullRendering</b> bit-field flag is set only during performance investigating and debugging to simulate an infinitely fast rendering engine that still must perform the overhead of DMA buffer submission and signaling. <b>NullRendering</b> is never set during typical operations. </p>
<p>Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008).</p>
</dd>

### -field PresentRedirected

<dd>
<p>A UINT value that specifies whether to redirect the present command. The command contains a completion of one frame even though the command was completed in the OpenGl ICD.</p>
<p>Setting this member is equivalent to setting the fifth bit of a 32-bit value (0x00000010).</p>
</dd>

### -field RenderKm

<dd>
<p>Supported in Windows 7 and later versions.</p>
<p>A UINT value that specifies whether the OpenGL ICD supplies a pointer to the command buffer to be rendered in the ICD's call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtrender.md">D3DKMTRender</a> function. If this flag is set, the runtime does not call the display miniport driver's <a href="display.dxgkddirender">DxgkDdiRender</a> function. If this flag is set, the runtime calls the display miniport driver's <a href="display.dxgkddirenderkm">DxgkDdiRenderKm</a> function. </p>
<p>Setting this member is equivalent to setting the sixth bit of a 32-bit value (0x00000020).</p>
</dd>

### -field Reserved

<dd>
<p>This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 26 bits (0xFFFFFFC0) of a 32-bit value to zeros.</p>
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
<a href="..\d3dkmthk\ns-d3dkmthk--d3dkmt-render.md">D3DKMT_RENDER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_RENDERFLAGS structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>