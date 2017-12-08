---
UID: NS.prntfont._UNIFM_HDR
title: UNIFM_HDR
author: windows-driver-content
description: The UNIFM_HDR structure is used to define the contents of Unidrv font metrics files (.ufm files).
old-location: print\unifm_hdr.htm
old-project: print
ms.assetid: 9490d090-2156-4653-9e56-a233d23c2fb3
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: UNIFM_HDR, UNIFM_HDR, *PUNIFM_HDR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: prntfont.h
req.include-header: Prntfont.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UNIFM_HDR
req.alt-loc: prntfont.h
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
req.product: Windows 10 or later.
---

# UNIFM_HDR structure



## -description
<p>The UNIFM_HDR structure is used to define the contents of <a href="print.customized_font_management#ddk_unidrv_font_metrics_files_gg#ddk_unidrv_font_metrics_files_gg">Unidrv font metrics files</a> (.ufm files).</p>


## -syntax

````
typedef struct _UNIFM_HDR {
  DWORD dwSize;
  DWORD dwVersion;
  ULONG ulDefaultCodepage;
  LONG  lGlyphSetDataRCID;
  DWORD loUnidrvInfo;
  DWORD loIFIMetrics;
  DWORD loExtTextMetric;
  DWORD loWidthTable;
  DWORD loKernPair;
  DWORD dwReserved[2];
} UNIFM_HDR, *PUNIFM_HDR;
````


## -struct-fields
<dl>

### -field dwSize

<dd>
<p>Specifies the total size, in bytes, of the .ufm file. Note that this is the total size of all structures used to define the file. This value is not the size of the UNIFM_HDR structure.</p>
</dd>

### -field dwVersion

<dd>
<p>Specifies the file version number, as defined in prntfont.h by a constant with a name format of UNIFM_VERSION_<i>x</i>_<i>x</i>.</p>
</dd>

### -field ulDefaultCodepage

<dd>
<p>Specifies the code page identifier for the font's default code page. For more information, see the following Remarks section.</p>
</dd>

### -field lGlyphSetDataRCID

<dd>
<p>Specifies an RC_GTT resource identifier that identifies a .gtt (Glyph Translation Table) file, or one of the CC_-prefixed code conversion identifiers defined in prntfont.h. For more information, see the following Remarks section.</p>
</dd>

### -field loUnidrvInfo

<dd>
<p>Specifies the byte offset from the beginning of the .ufm (Unidrv Font Metrics) file to the location of the file's <a href="..\prntfont\ns-prntfont--unidrvinfo.md">UNIDRVINFO</a> structure.</p>
</dd>

### -field loIFIMetrics

<dd>
<p>Specifies the byte offset from the beginning of the .ufm file to the location of the file's <a href="..\prntfont\ns-prntfont--printifi32.md">PRINTIFI32</a> structure.</p>
</dd>

### -field loExtTextMetric

<dd>
<p>Specifies the byte offset from the beginning of the .ufm file to the location of the file's <a href="..\prntfont\ns-prntfont--exttextmetric.md">EXTTEXTMETRIC</a> structure.</p>
</dd>

### -field loWidthTable

<dd>
<p>Specifies the byte offset from the beginning of the .ufm file to the location of the file's <a href="..\prntfont\ns-prntfont--widthtable.md">WIDTHTABLE</a> structure.</p>
</dd>

### -field loKernPair

<dd>
<p>Specifies the byte offset from the beginning of the .ufm file to the location of the file's <a href="..\prntfont\ns-prntfont--kerndata.md">KERNDATA</a> structure.</p>
</dd>

### -field dwReserved

<dd>
<p>Not used.</p>
</dd>
</dl>

## -remarks
<p>A UNIFM_HDR structure must be the first structure contained in a .ufm file.</p>

<p>If <b>lGlyphSetDataRCID</b> is not CC_DEFAULT, then the following rules apply:</p>

<p>If <b>lGlyphSetDataRCID</b> contains an RC_GTT resource identifier, the code page number specified for <b>ulDefaultCodepage</b> must be the same code page number that is contained in the .gtt (Glyph Translation Table) file's first <a href="..\prntfont\ns-prntfont--uni-codepageinfo.md">UNI_CODEPAGEINFO</a> structure.</p>

<p>If <b>lGlyphSetDataRCID</b> contains one of the CC_-prefixed code conversion identifiers (other than CC_DEFAULT), the code page number specified for <b>ulDefaultCodepage</b> must be the code page number that is associated with the CC_-prefixed identifier. (These code page numbers are listed in Prntfont.h, next to each CC_-prefixed identifier.)</p>

<p>The character conversion codes predefined by the system, listed in Prntfont.h, are as follows:</p>

<p>If <b>lGlyphSetDataRCID</b> is CC_DEFAULT, there are no restrictions on the value specified for <b>ulDefaultCodepage</b>, but a default code page must be specified.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Prntfont.h (include Prntfont.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\prntfont\ns-prntfont--unidrvinfo.md">UNIDRVINFO</a>
</dt>
<dt>
<a href="..\prntfont\ns-prntfont--printifi32.md">PRINTIFI32</a>
</dt>
<dt>
<a href="..\prntfont\ns-prntfont--exttextmetric.md">EXTTEXTMETRIC</a>
</dt>
<dt>
<a href="..\prntfont\ns-prntfont--widthtable.md">WIDTHTABLE</a>
</dt>
<dt>
<a href="..\prntfont\ns-prntfont--kerndata.md">KERNDATA</a>
</dt>
<dt>
<a href="..\prntfont\ns-prntfont--uni-codepageinfo.md">UNI_CODEPAGEINFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20UNIFM_HDR structure%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>