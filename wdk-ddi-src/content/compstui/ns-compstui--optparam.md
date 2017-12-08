---
UID: NS.compstui._OPTPARAM
title: OPTPARAM
author: windows-driver-content
description: An array of OPTPARAM structures is used by CPSUI applications (including printer interface DLLs) for describing all the parameter values associated with a property sheet option. The array's address is included in an OPTTYPE structure.
old-location: print\optparam.htm
old-project: print
ms.assetid: d0cd2867-783c-4a41-a819-e919d4ffc1e3
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: OPTPARAM, OPTPARAM, *POPTPARAM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: compstui.h
req.include-header: Compstui.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OPTPARAM
req.alt-loc: compstui.h
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

# OPTPARAM structure



## -description
<p>An array of OPTPARAM structures is used by CPSUI applications (including printer interface DLLs) for describing all the parameter values associated with a <a href="https://msdn.microsoft.com/572330d6-1a1b-46fd-bfb4-be2b0990bca4">property sheet option</a>. The array's address is included in an <a href="..\compstui\ns-compstui--opttype.md">OPTTYPE</a> structure.</p>


## -syntax

````
typedef struct _OPTPARAM {
  WORD      cbSize;
  BYTE      Flags;
  BYTE      Style;
  LPTSTR    pData;
  ULONG_PTR IconID;
  LPARAM    lParam;
  ULONG_PTR dwReserved[2];
} OPTPARAM, *POPTPARAM;
````


## -struct-fields
<dl>

### -field cbSize

<dd>
<p>Size, in bytes, of the OPTPARAM structure.</p>
</dd>

### -field Flags

<dd>
<p>Optional bit flags that modify the parameter's characteristics. The following flags can be set in any combination:</p>
<p></p>
<dl>

### -field OPTPF_DISABLED

<dd>
<p>If set, the parameter is not user-selectable. Can be used with the following option types:</p>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562825">TVOT_2STATES</a>
</p>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562827">TVOT_3STATES</a>
</p>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562833">TVOT_COMBOBOX</a>
</p>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562839">TVOT_LISTBOX</a>
</p>
</dd>
</dl>
<p></p>
<dl>

### -field OPTPF_HIDE

<dd>
<p>If set, the parameter not displayed in the treeview. Can be used with the following option types:</p>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562827">TVOT_3STATES</a>
</p>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562833">TVOT_COMBOBOX</a>
</p>
<p>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562839">TVOT_LISTBOX</a>
</p>
</dd>
</dl>
<p></p>
<dl>

### -field OPTPF_ICONID_AS_HICON

<dd>
<p>If set, the <b>IconID</b> member contains an icon handle.</p>
<p>If not set, the <b>IconID</b> member contains an icon resource identifier.</p>
</dd>
</dl>
<p></p>
<dl>

### -field OPTPF_OVERLAY_NO_ICON

<dd>
<p>If set, CPSUI overlays its IDI_CPSUI_NO icon onto the icon identified by the <b>IconID</b> member.</p>
</dd>
</dl>
<p></p>
<dl>

### -field OPTPF_OVERLAY_STOP_ICON

<dd>
<p>If set, CPSUI overlays the IDI_CPSUI_STOP icon onto the icon identified by the <b>IconID</b> member.</p>
</dd>
</dl>
<p></p>
<dl>

### -field OPTPF_OVERLAY_WARNING_ICON

<dd>
<p>If set, CPSUI overlays its IDI_CPSUI_WARNING icon onto the icon identified by the <b>IconID</b> member.</p>
</dd>
</dl>
<p></p>
<dl>

### -field OPTPF_USE_HDLGTEMPLATE

<dd>
<p>If set, <b>lParam</b> contains a template handle.</p>
<p>If not set, <b>lParam</b> contains a template resource identifier.</p>
<p>(Used only if <b>Style</b> is PUSHBUTTON_TYPE_DLGPROC.)</p>
</dd>
</dl>
</dd>

### -field Style

<dd>
<p>Push button style, used only for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562844">TVOT_PUSHBUTTON</a> option type.</p>
</dd>

### -field pData

<dd>
<p>Pointer to the parameter's value. Use of this member is dependent on the <a href="https://msdn.microsoft.com/3b3c002c-a201-4f81-b208-30864343409b">CPSUI option type</a>.</p>
</dd>

### -field IconID

<dd>
<p>Usually identifies the icon to be associated with the option parameter, but is sometimes used for other purposes. Use of this member is dependent on the <a href="https://msdn.microsoft.com/3b3c002c-a201-4f81-b208-30864343409b">CPSUI option type</a>.</p>
</dd>

### -field lParam

<dd>
<p>Use of this member is dependent on the <a href="https://msdn.microsoft.com/3b3c002c-a201-4f81-b208-30864343409b">CPSUI option type</a>.</p>
</dd>

### -field dwReserved

<dd>
<p>Reserved, must be initialized to zero.</p>
</dd>
</dl>

## -remarks
<p>If the OPTPF_HIDE flag is set in all the OPTPARAM structures associated with an option, CPSUI hides the entire option.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Compstui.h (include Compstui.h)</dt>
</dl>
</td>
</tr>
</table>