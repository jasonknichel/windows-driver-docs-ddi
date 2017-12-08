---
UID: NS.d3dkmddi._DXGK_GDIARG_CLEARTYPEBLEND
title: DXGK_GDIARG_CLEARTYPEBLEND
author: windows-driver-content
description: The DXGK_GDIARG_CLEARTYPEBLEND structure describes the characteristics of a GDI hardware-accelerated ClearType and antialiased text pixel blending operation.
old-location: display\dxgk_gdiarg_cleartypeblend.htm
old-project: display
ms.assetid: 1e67bb33-c2e5-4f3c-9ea6-feeb4a1fe645
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_GDIARG_CLEARTYPEBLEND, DXGK_GDIARG_CLEARTYPEBLEND
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_GDIARG_CLEARTYPEBLEND
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# DXGK_GDIARG_CLEARTYPEBLEND structure



## -description
<p>The DXGK_GDIARG_CLEARTYPEBLEND structure describes the characteristics of a GDI hardware-accelerated ClearType and antialiased text pixel blending operation.</p>


## -syntax

````
typedef struct _DXGK_GDIARG_CLEARTYPEBLEND {
  RECT DstRect;
  UINT TmpSurfAllocationIndex;
  UINT GammaSurfAllocationIndex;
  UINT AlphaSurfAllocationIndex;
  UINT DstAllocationIndex;
  INT  DstToAlphaOffsetX;
  INT  DstToAlphaOffsetY;
  UINT Color;
  UINT Gamma;
  UINT NumSubRects;
  RECT *pSubRects;
  UINT AlphaSurfPitch;
  UINT Color2;
} DXGK_GDIARG_CLEARTYPEBLEND;
````


## -struct-fields
<dl>

### -field DstRect

<dd>
<p>[in] A <a href="display.rect">RECT</a> structure that defines the rectangular area to be modified. This rectangle is specified in the coordinate system of the destination surface and is defined by two points: upper left and lower right. The rectangle is lower-right exclusive; that is, its lower and right edges are not a part of the bit-block transfer. The two points that define the rectangle are always well ordered. </p>
<p>The destination rectangle defined by <b>DstRect</b> can exceed the bounds of the destination surface, but sub-rectangles cannot. Additionally, all sub-rectangles are guaranteed to fit inside the destination surface. Sub-rectangles can be constrained further by a bounding rectangle that is smaller than the destination rectangle.</p>
</dd>

### -field TmpSurfAllocationIndex

<dd>
<p>
      [in] An index of the element in the allocation list that specifies a temporary surface. This surface can be used to read the destination before executing a pixel shader.
     </p>
</dd>

### -field GammaSurfAllocationIndex

<dd>
<p>
      [in] An index of the element in the allocation list that specifies a gamma table of type <a href="..\d3dkmdt\ne-d3dkmdt--d3dkmdt-gdisurfacetype.md">D3DKMDT_GDISURFACETYPE</a>. The format of the gamma lookup allocation is 8 bits per pixel, and the resolution is 512 x 16 pixels. Each row of the allocation contains two tables: gamma and inverse gamma. Each table has 256 entries.
     </p>
</dd>

### -field AlphaSurfAllocationIndex

<dd>
<p>
      [in] An index of the element in the allocation list that specifies alpha values of a surface. The alpha surface is in the same coordinate space as the destination surface space that is bounded by the <b>DstRect</b> destination rectangle.
     </p>
</dd>

### -field DstAllocationIndex

<dd>
<p>
      [in] An index of the element in the allocation list that specifies the allocation that is referenced by the <b>DstRect</b> destination rectangle.
     </p>
</dd>

### -field DstToAlphaOffsetX

<dd>
<p>
      [in] An offset in the x direction that transforms the destination rectangle coordinate space to the alpha surface coordinate space.
     </p>
</dd>

### -field DstToAlphaOffsetY

<dd>
<p>
      [in] An offset in the y direction that transforms the destination rectangle coordinate space to the alpha surface coordinate space.
     </p>
</dd>

### -field Color

<dd>
<p>
      [in] The foreground color, in 32-bit ARGB unsigned pixel format (as defined by the D3DDDIFMT_A8R8G8B8 value of the <a href="..\d3dukmdt\ne-d3dukmdt--d3dddiformat.md">D3DDDIFORMAT</a> enumeration), corrected for gamma.
     </p>
</dd>

### -field Gamma

<dd>
<p>
      [in] An index of the element in the allocation list that specifies the gamma lookup table. Gamma values are in the range of [0, 15], otherwise gamma is 0xFFFFFFFF (the value of D3DKM_INVALID_GAMMA_INDEX). See Remarks for more information on how gamma is used in ClearType blending.
     </p>
</dd>

### -field NumSubRects

<dd>
<p>
      The number of sub-rectangles in the destination surface space that is bounded by the <b>DstRect</b> destination rectangle.
     </p>
</dd>

### -field pSubRects

<dd>
<p>
      A pointer to the sub-rectangles in the destination surface space that is bounded by the <b>DstRect</b> destination rectangle.
     </p>
</dd>

### -field AlphaSurfPitch

<dd>
<p>
      The pitch, in bytes, of the alpha surface referenced by <b>AlphaSurfAllocationIndex</b>.
     </p>
</dd>

### -field Color2

<dd>
<p>
      [in] The foreground color, in 32-bit ARGB unsigned pixel format (as defined by the D3DDDIFMT_A8R8G8B8 value of the <a href="..\d3dukmdt\ne-d3dukmdt--d3dddiformat.md">D3DDDIFORMAT</a> enumeration), not corrected for gamma.
     </p>
</dd>
</dl>

## -remarks
<p>The value of <b>Gamma</b> should be in the range of [0, 15] unless set to 0xFFFFFFFF (the value of D3DKM_INVALID_GAMMA_INDEX). The value of <b>Gamma</b> is the index of a row in the gamma allocation.</p>

<p>When gamma is in the range of [0, 15], the following per-pixel blending is performed.</p>

<p>When gamma is equal to 0xFFFFFFFF (the value of D3DKM_INVALID_GAMMA_INDEX), the following per-pixel blending is performed.</p>

<p>Where the following parameters are in the D3DDDIFMT_A8R8G8B8 format defined in the <a href="..\d3dukmdt\ne-d3dukmdt--d3dddiformat.md">D3DDDIFORMAT</a> enumeration:</p>

<p><b>Color</b> = gamma-corrected foreground color, as defined by the <b>Color</b> member</p>

<p><b>Color2</b> = foreground color, not gamma corrected, as defined by the <b>Color2</b> member</p>

<p>
       D = destination pixel color</p>

<p>
       A = alpha surface color</p>

<p>The display miniport driver must ensure that when a component of A is zero, the corresponding output component is the same as the background color component (D).</p>

<p>The driver must also ensure that when a component of A is 0xFF, the corresponding output component is the same as the foreground color component (<b>Color2</b>).</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 7 and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt--d3dddiformat.md">D3DDDIFORMAT</a>
</dt>
<dt>
<a href="..\d3dkmdt\ne-d3dkmdt--d3dkmdt-gdisurfacetype.md">D3DKMDT_GDISURFACETYPE</a>
</dt>
<dt>
<a href="display.rect">RECT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_GDIARG_CLEARTYPEBLEND structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>