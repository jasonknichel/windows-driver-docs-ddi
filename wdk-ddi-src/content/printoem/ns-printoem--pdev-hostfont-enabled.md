---
UID: NS.printoem._PDEV_HOSTFONT_ENABLED
title: PDEV_HOSTFONT_ENABLED
author: windows-driver-content
description: The PDEV_HOSTFONT_ENABLED structure indicates whether the Hostfont feature is enabled.
old-location: print\pdev_hostfont_enabled.htm
old-project: print
ms.assetid: f7fc7e33-e80b-449e-a1d1-a93740cd967c
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: PDEV_HOSTFONT_ENABLED, PDEV_HOSTFONT_ENABLED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
req.include-header: Prcomoem.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PDEV_HOSTFONT_ENABLED
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

# PDEV_HOSTFONT_ENABLED structure



## -description
<p>The PDEV_HOSTFONT_ENABLED structure indicates whether the Hostfont feature is enabled.</p>


## -syntax

````
typedef struct _PDEV_HOSTFONT_ENABLED {
  BOOL bHostfontEnabled;
} PDEV_HOSTFONT_ENABLED;
````


## -struct-fields
<dl>

### -field bHostfontEnabled

<dd>
<p>Specifies whether the Hostfont feature is enabled. If set to <b>TRUE</b>, the Hostfont feature is enabled. Otherwise, this feature is disabled.</p>
</dd>
</dl>

## -remarks
<p>This structure is available in Windows XP and later. </p>

<p>The <i>pBuf</i> parameter of the <a href="print.iprintoemps2_getpdevadjustment">IPrintOemPS2::GetPDEVAdjustment</a> method can point to a structure of this type.</p>

<p>Hostfont support is designed to improve the performance of a PostScript interpreter running on a host computer system, rather than on a physical printer. When the Hostfont feature is enabled, the Pscript5 driver stops converting and downloading host font data when there is already an identical font resident on the host on which the interpreter is running. This applies only to the following fonts:</p>

<p>a TrueType Font (TTF) converted to either a PostScript Type 42 or CID2 font</p>

<p>an OpenType Font (OTF) converted to either a PostScript Type 1 or CID0 font</p>

<p>a Printer Font Binary (PFB)</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Printoem.h (include Prcomoem.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.iprintoemps2_getpdevadjustment">IPrintOemPS2::GetPDEVAdjustment</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20PDEV_HOSTFONT_ENABLED structure%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>