---
UID: NS.d3dhal._D3DHAL_DP2BUFFERBLT
title: D3DHAL_DP2BUFFERBLT
author: windows-driver-content
description: DirectX 8.0 and later versions only. D3DHAL_DP2BUFFERBLT is used for vertex or index buffer blts when D3dDrawPrimitives2 responds to the D3DDP2OP_BUFFERBLT command token.
old-location: display\d3dhal_dp2bufferblt.htm
old-project: display
ms.assetid: 3c2cb5c2-7461-40fc-a6c7-e4a107b24f74
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DHAL_DP2BUFFERBLT, D3DHAL_DP2BUFFERBLT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DHAL_DP2BUFFERBLT
req.alt-loc: d3dhal.h
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

# D3DHAL_DP2BUFFERBLT structure



## -description
<p>
   DirectX 8.0 and later versions only.
   </p>
<p>D3DHAL_DP2BUFFERBLT is used for vertex or index buffer blts when <a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a> responds to the D3DDP2OP_BUFFERBLT command token.</p>


## -syntax

````
typedef struct _D3DHAL_DP2BUFFERBLT {
  DWORD    dwDDDestSurface;
  DWORD    dwDDSrcSurface;
  DWORD    dwOffset;
  D3DRANGE rSrc;
  DWORD    dwFlags;
} D3DHAL_DP2BUFFERBLT, *LPD3DHAL_DP2BUFFERBLT;
````


## -struct-fields
<dl>

### -field dwDDDestSurface

<dd>
<p>Specifies the handle to the destination vertex or index buffer.</p>
</dd>

### -field dwDDSrcSurface

<dd>
<p>Specifies the handle to the source vertex or index buffer.</p>
</dd>

### -field dwOffset

<dd>
<p>Specifies the offset, in bytes, of the destination buffer the copy should be directed into.</p>
</dd>

### -field rSrc

<dd>
<p>Specifies what range of the source buffer should be copied. This is a D3DRANGE structure, which is described in the Microsoft Windows SDK documentation, and contains a UINT offset in bytes and a UINT size in bytes.</p>
</dd>

### -field dwFlags

<dd>
<p>Unused.</p>
</dd>
</dl>

## -remarks
<p>The <a href="display.created3dbuffer">CreateD3DBuffer</a> callback creates the small integer handles to the vertex or index buffers that can be used as source and destination buffers for buffer blts.</p>

<p>See Remarks for <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2texblt.md">D3DHAL_DP2TEXBLT</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dhal.h (include D3dhal.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.created3dbuffer">CreateD3DBuffer</a>
</dt>
<dt>D3DDP2OP_BUFFERBLT</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2BUFFERBLT structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>