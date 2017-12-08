---
UID: NS.printoem._OEMDMPARAM
title: OEMDMPARAM
author: windows-driver-content
description: The OEMDMPARAM structure is used as an input parameter to the IPrintOemUI::DevMode, IPrintOemUni::DevMode, and IPrintOemPS::DevMode methods.
old-location: print\oemdmparam.htm
old-project: print
ms.assetid: 625980d1-47eb-4427-a9e8-967b1873bbd6
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: OEMDMPARAM, OEMDMPARAM, *POEMDMPARAM
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
req.alt-api: OEMDMPARAM
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

# OEMDMPARAM structure



## -description
<p>The OEMDMPARAM structure is used as an input parameter to the <a href="print.iprintoemui_devmode">IPrintOemUI::DevMode</a>, <a href="print.iprintoemuni_devmode">IPrintOemUni::DevMode</a>, and <a href="print.iprintoemps_devmode">IPrintOemPS::DevMode</a> methods.</p>


## -syntax

````
typedef struct _OEMDMPARAM {
  DWORD    cbSize;
  PVOID    pdriverobj;
  HANDLE   hPrinter;
  HANDLE   hModule;
  PDEVMODE pPublicDMIn;
  PDEVMODE pPublicDMOut;
  PVOID    pOEMDMIn;
  PVOID    pOEMDMOut;
  DWORD    cbBufSize;
} OEMDMPARAM, *POEMDMPARAM;
````


## -struct-fields
<dl>

### -field cbSize

<dd>
<p>Contains the size of the OEMDMPARAM structure. Supplied by the Unidrv or Pscript5 driver.</p>
</dd>

### -field pdriverobj

<dd>
<p></p>
<dl>

### -field For IPrintOemUI::DevMode:

<dd>
<p>Not used.</p>
</dd>

### -field For IPrintOemUni::DevMode and IPrintOemPS::DevMode:

<dd>
<p>Pointer to a <a href="..\printoem\ns-printoem--devobj.md">DEVOBJ</a> structure.</p>
</dd>
</dl>
</dd>

### -field hPrinter

<dd>
<p>Handle to the printer device. Supplied by the Unidrv or Pscript5 driver.</p>
</dd>

### -field hModule

<dd>
<p>Handle to the user interface plug-in module. Supplied by the Unidrv or Pscript5 driver.</p>
</dd>

### -field pPublicDMIn

<dd>
<p>Pointer to the printer device's public DEVMODEW structure. Supplied by the Unidrv or Pscript5 driver. (Valid if the <b>DevMode</b> method's <i>dwMode</i> value is OEMDM_DEFAULT, OEMDM_CONVERT, or OEMDM_MERGE.)</p>
</dd>

### -field pPublicDMOut

<dd>
<p>Pointer to a location to receive public DEVMODEW structure contents. Supplied by the Unidrv or Pscript5 driver. (Valid if the <b>DevMode</b> method's <i>dwMode</i> value is OEMDM_CONVERT or OEMDM_MERGE.)</p>
</dd>

### -field pOEMDMIn

<dd>
<p>Pointer to a set of private DEVMODEW members. Supplied by the Unidrv or Pscript5 driver. (Valid if the <b>DevMode</b> method's <i>dwMode</i> value is OEMDM_CONVERT or OEMDM_MERGE.)</p>
</dd>

### -field pOEMDMOut

<dd>
<p>Pointer to memory allocated to receive modified private DEVMODEW contents. Supplied by the Unidrv or Pscript5 driver. (Valid if the <b>DevMode</b> method's <i>dwMode</i> value is OEMDM_DEFAULT, OEMDM_CONVERT or OEMDM_MERGE.)</p>
</dd>

### -field cbBufSize

<dd>
<p>On input, contains the caller-supplied size of memory space pointed to by <b>pOEMDMOut</b>. (Not valid if the <b>DevMode</b> method's <i>dwMode</i> value is OEMDM_SIZE.)</p>
<p>On output, contains the method-supplied size of the current version of the private DEVMODEW section. (Only used if the <b>DevMode</b> method's <i>dwMode</i> value is OEMDM_SIZE.)</p>
</dd>
</dl>

## -remarks
<p>For more information about the use of OEMDMPARAM structure members, see the description of the <a href="print.iprintoemui_devmode">IPrintOemUI::DevMode</a> method.</p>

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