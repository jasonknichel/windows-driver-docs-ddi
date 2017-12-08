---
UID: NS.printoem._GETINFO_GLYPHSTRING
title: GETINFO_GLYPHSTRING
author: windows-driver-content
description: The GETINFO_GLYPHSTRING structure is used as input to the UNIFONTOBJ_GetInfo callback function.
old-location: print\getinfo_glyphstring.htm
old-project: print
ms.assetid: ebcc1ada-af6f-46c3-a025-97079eb08816
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: GETINFO_GLYPHSTRING, GETINFO_GLYPHSTRING, *PGETINFO_GLYPHSTRING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GETINFO_GLYPHSTRING
req.alt-loc: printoem.h
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
req.iface: IPrintSchemaTicket2
req.product: Windows 10 or later.
---

# GETINFO_GLYPHSTRING structure



## -description
<p>The GETINFO_GLYPHSTRING structure is used as input to the <a href="print.unifontobj_getinfo">UNIFONTOBJ_GetInfo</a> callback function.</p>


## -syntax

````
typedef struct _GETINFO_GLYPHSTRING {
  DWORD dwSize;
  DWORD dwCount;
  DWORD dwTypeIn;
  PVOID pGlyphIn;
  DWORD dwTypeOut;
  PVOID pGlyphOut;
  DWORD dwGlyphOutSize;
} GETINFO_GLYPHSTRING, *PGETINFO_GLYPHSTRING;
````


## -struct-fields
<dl>

### -field dwSize

<dd>
<p>Specifies the size, in bytes, of the GETINFO_GLYPHSTRING structure. This value is supplied by the <a href="print.unifontobj_getinfo">UNIFONTOBJ_GetInfo</a> caller.</p>
</dd>

### -field dwCount

<dd>
<p>Specifies the number of elements in the arrays pointed to by <b>pGlyphIn</b> and <b>pGlyphOut</b>. This value is supplied by the <a href="print.unifontobj_getinfo">UNIFONTOBJ_GetInfo</a> caller.</p>
</dd>

### -field dwTypeIn

<dd>
<p>Specifies the type of glyph specifier array pointed to by <b>pGlyphIn</b>. Valid values are as follows:</p>
<table>
<tr>
<th>Value</th>
<th>Definition</th>
</tr>
<tr>
<td>
<p>TYPE_GLYPHHANDLE</p>
</td>
<td>
<p>The <b>pGlyphIn</b> array elements are of type HGLYPH, or handle to a device font glyph. For this value of <b>dwTypeIn</b>, valid values for <b>dwTypeOut</b> are either TYPE_UNICODE or TYPE_TRANSDATA.</p>
</td>
</tr>
<tr>
<td>
<p>TYPE_GLYPHID</p>
</td>
<td>
<p>The <b>pGlyphIn</b> array elements are of type DWORD, and contain glyph identifiers for downloaded TrueType font glyphs. For this value of <b>dwTypeIn</b>, valid values for <b>dwTypeOut</b> are either TYPE_UNICODE or TYPE_GLYPHHANDLE.</p>
</td>
</tr>
</table>
<p> </p>
<p>Supplied by the <a href="print.unifontobj_getinfo">UNIFONTOBJ_GetInfo</a> caller.</p>
</dd>

### -field pGlyphIn

<dd>
<p>Pointer to an array of glyph specifiers. The array element type is indicated by <b>dwTypeIn</b>. This value is supplied by the <a href="print.unifontobj_getinfo">UNIFONTOBJ_GetInfo</a> caller.</p>
</dd>

### -field dwTypeOut

<dd>
<p>Specifies the type of glyph specifier array pointed to by <b>pGlyphOut</b>. Valid values are as follows:</p>
<table>
<tr>
<th>Value</th>
<th>Definition</th>
</tr>
<tr>
<td>
<p>TYPE_GLYPHHANDLE</p>
</td>
<td>
<p>The <b>pGlyphOut</b> array elements are of type HGLYPH, or handle to a device font glyph. This value is valid only when <b>dwTypeIn</b> has been set to TYPE_GLYPHID.</p>
</td>
</tr>
<tr>
<td>
<p>TYPE_TRANSDATA</p>
</td>
<td>
<p>The <b>pGlyphOut</b> array elements are of type <a href="..\prntfont\ns-prntfont--transdata.md">TRANSDATA</a>. This value is valid only when <b>dwTypeIn</b> has been set to TYPE_GLYPHHANDLE.</p>
</td>
</tr>
<tr>
<td>
<p>TYPE_UNICODE</p>
</td>
<td>
<p>The <i>pGlyph</i> array elements are of type WCHAR. This value is valid when <b>dwTypeIn</b> has been set to either TYPE_GLYPHHANDLE or TYPE_GLYPHID.</p>
</td>
</tr>
</table>
<p> </p>
<dl>
<dd>
<p>Supplied by the <a href="print.unifontobj_getinfo">UNIFONTOBJ_GetInfo</a> caller.</p>
</dd>
</dl>
</dd>

### -field pGlyphOut

<dd>
<p>Caller-supplied pointer to an empty array of glyph specifiers. The array is filled in by Unidrv's <a href="print.unifontobj_getinfo">UNIFONTOBJ_GetInfo</a> callback function. The array element type is indicated by <b>dwTypeOut</b>. This pointer is supplied by the <u>UNIFONTOBJ_GetInfo</u> caller.</p>
</dd>

### -field dwGlyphOutSize

<dd>
<p>Specifies the size, in bytes, of the buffer pointed to by <b>pGlyphOut</b>. This member is used only when <b>dwTypeIn</b> has been set to TYPE_GLYPHHANDLE and <b>dwTypeOut</b> has been set to TYPE_TRANSDATA. See the following Remarks section for more information.</p>
</dd>
</dl>

## -remarks
<p>To convert an array of glyph specifiers from one type to another, a rendering plug-in can supply the address of a GETINFO_GLYPHSTRING structure when calling Unidrv's <a href="print.unifontobj_getinfo">UNIFONTOBJ_GetInfo</a> callback function.</p>

<p>If the conversion is from TYPE_GLYPHHANDLE to TYPE_TRANSDATA, <a href="print.unifontobj_getinfo">UNIFONTOBJ_GetInfo</a> must be called twice.</p>

<p>Before the first call to <a href="print.unifontobj_getinfo">UNIFONTOBJ_GetInfo</a>, the rendering plug-in fills in the <b>dwSize</b>, <b>dwCount</b>, <b>dwTypeIn</b>, and <b>pGlyphIn</b> members and sets <b>dwGlyphOutSize</b> member to zero. </p>

<p>After <a href="print.unifontobj_getinfo">UNIFONTOBJ_GetInfo</a> returns, the <b>dwGlyphOutSize</b> member contains the size, in bytes, of the buffer needed to store the converted string.</p>

<p>The plug-in allocates a block of memory of the size received in the <b>dwGlyphOutSize</b> member, sets the <b>pGlyphOut</b> member to point to this memory block, and calls <a href="print.unifontobj_getinfo">UNIFONTOBJ_GetInfo</a> once more. UNIDRV then converts the string from TYPE_GLYPHHANDLE to TYPE_TRANSDATA.</p>

<p>The values that a rendering plug-in specifies for the <b>dwTypeIn </b>and <b>pGlyphIn</b> members typically are those that were previously received as the <b>dwType </b>and <i>pGlyph</i> parameters to the <a href="print.iprintoemuni_outputcharstr">IPrintOemUni::OutputCharStr</a> method.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Printoem.h (include Printoem.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.unifontobj_getinfo">UNIFONTOBJ_GetInfo</a>
</dt>
<dt>
<a href="print.iprintoemuni_outputcharstr">IPrintOemUni::OutputCharStr</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20GETINFO_GLYPHSTRING structure%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>