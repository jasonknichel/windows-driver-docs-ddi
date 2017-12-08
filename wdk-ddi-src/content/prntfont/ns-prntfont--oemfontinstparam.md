---
UID: NS.prntfont._OEMFONTINSTPARAM
title: OEMFONTINSTPARAM
author: windows-driver-content
description: The OEMFONTINSTPARAM structure is used as an input parameter to a user interface plug-in's IPrintOemUI::FontInstallerDlgProc method.
old-location: print\oemfontinstparam.htm
old-project: print
ms.assetid: cdd3ed28-a077-4b89-9222-ba282b9c7205
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: OEMFONTINSTPARAM, OEMFONTINSTPARAM, *POEMFONTINSTPARAM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: prntfont.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OEMFONTINSTPARAM
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

# OEMFONTINSTPARAM structure



## -description
<p>The OEMFONTINSTPARAM structure is used as an input parameter to a user interface plug-in's <a href="print.iprintoemui_fontinstallerdlgproc">IPrintOemUI::FontInstallerDlgProc</a> method.</p>


## -syntax

````
typedef struct _OEMFONTINSTPARAM {
  DWORD  cbSize;
  HANDLE hPrinter;
  HANDLE hModule;
  HANDLE hHeap;
  DWORD  dwFlags;
  PWSTR  pFontInstallerName;
} OEMFONTINSTPARAM, *POEMFONTINSTPARAM;
````


## -struct-fields
<dl>

### -field cbSize

<dd>
<p>Size, in bytes, of the OEMFONTINSTPARAM structure.</p>
</dd>

### -field hPrinter

<dd>
<p>Unidrv-supplied printer handle.</p>
</dd>

### -field hModule

<dd>
<p>Unidrv-supplied handle to the user interface plug-in.</p>
</dd>

### -field hHeap

<dd>
<p>Unidrv-supplied handle to a heap from which space can be allocated by calling the <b>HeapAlloc</b> function (described in the Microsoft Windows SDK documentation).</p>
</dd>

### -field dwFlags

<dd>
<p>Unidrv-supplied flags. The only defined flag is FG_CANCHANGE which, if set, indicates the user interface should allow the user to change the installed fonts. Otherwise the user interface should be displayed in read-only mode.</p>
</dd>

### -field pFontInstallerName

<dd>
<p>Pointer to a string representing the font installer's name. The <a href="print.iprintoemui_fontinstallerdlgproc">IPrintOemUI::FontInstallerDlgProc</a> method must supply this string if the received message is WM_USER+WM_FI_NAME. The string must be placed in memory allocated using <b>hHeap</b>.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Prntfont.h (include Printoem.h)</dt>
</dl>
</td>
</tr>
</table>