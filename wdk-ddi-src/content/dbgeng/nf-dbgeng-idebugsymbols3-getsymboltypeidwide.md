---
UID: NF.dbgeng.IDebugSymbols3.GetSymbolTypeIdWide
title: IDebugSymbols3::GetSymbolTypeIdWide
author: windows-driver-content
description: The GetSymbolTypeIdWide method returns the type ID and module of the specified symbol.
old-location: debugger\getsymboltypeidwide.htm
old-project: debugger
ms.assetid: b68a5f89-1623-4cab-84bf-3cc6e4031d9b
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugSymbols3, GetSymbolTypeIdWide, IDebugSymbols3::GetSymbolTypeIdWide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugSymbols3.GetSymbolTypeIdWide
req.alt-loc: dbgeng.h
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
req.iface: IDebugSymbols3
---

# IDebugSymbols3::GetSymbolTypeIdWide method



## -description
<p>The <b>GetSymbolTypeIdWide</b>  method returns the type ID and module of the specified symbol.</p>


## -syntax

````
HRESULT GetSymbolTypeIdWide(
  [in]            PCWSTR   Symbol,
  [out]           PULONG   TypeId,
  [out, optional] PULONG64 Module
);
````


## -parameters
<dl>

### -param Symbol [in]

<dd>
<p>Specifies the expression whose type ID is requested.  See the Remarks section for details on the syntax of this expression.</p>
</dd>

### -param TypeId [out]

<dd>
<p>Receives the type ID.</p>
</dd>

### -param Module [out, optional]

<dd>
<p>Receives the base address of the module containing the symbol.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.  If <i>Module</i> is <b>NULL</b>, this information is not returned.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful</p>

<p> </p>

## -remarks
<p>The <i>Symbol</i> expression may contain structure fields, pointer dereferencing, and array dereferencing -- for example <b>my_struct.some_field[0]</b>.</p>

<p>For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.</p>

## -requirements
<table>
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
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="debugger.gettypeid">GetTypeId</a>
</dt>
<dt>
<a href="debugger.getsymboltypeid">GetSymbolTypeId</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetSymbolTypeIdWide method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>