---
UID: NF.dbgeng.IDebugSymbols3.GetScopeSymbolGroup
title: IDebugSymbols3::GetScopeSymbolGroup
author: windows-driver-content
description: The GetScopeSymbolGroup method returns a symbol group containing the symbols in the current target's scope.
old-location: debugger\getscopesymbolgroup.htm
old-project: debugger
ms.assetid: 002af3f1-4879-40e9-a5c6-bf62a3b26e02
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugSymbols3, GetScopeSymbolGroup, IDebugSymbols3::GetScopeSymbolGroup
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
req.alt-api: IDebugSymbols.GetScopeSymbolGroup,IDebugSymbols2.GetScopeSymbolGroup,IDebugSymbols3.GetScopeSymbolGroup
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

# IDebugSymbols3::GetScopeSymbolGroup method



## -description
<p>The <b>GetScopeSymbolGroup</b>  method returns a symbol group containing the symbols in the current target's scope.</p>


## -syntax

````
HRESULT GetScopeSymbolGroup(
  [in]           ULONG               Flags,
  [in, optional] PDEBUG_SYMBOL_GROUP Update,
  [out]          PDEBUG_SYMBOL_GROUP *Symbols
);
````


## -parameters
<dl>

### -param Flags [in]

<dd>
<p>Specifies a bit-set used to determine which symbols to include in the symbol group.  To include all symbols, set <i>Flags</i> to DEBUG_SCOPE_GROUP_ALL.  The following bit-flags determine which symbols are included.</p>
<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
<p>DEBUG_SCOPE_GROUP_ARGUMENTS</p>
</td>
<td>
<p>Include the function arguments for the current scope.</p>
</td>
</tr>
<tr>
<td>
<p>DEBUG_SCOPE_GROUP_LOCALS</p>
</td>
<td>
<p>Include the local variables for the current scope.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -param Update [in, optional]

<dd>
<p>Specifies a previously created symbol group that will be updated to reflect the current scope.  If <i>Update</i> is <b>NULL</b>, a new symbol group interface object is created.</p>
</dd>

### -param Symbols [out]

<dd>
<p>Receives the symbol group interface object for the current scope.  For details on this interface, see <a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a>
</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>The <i>Update</i> parameter allows for efficient updates when stepping through code. Instead of creating and populating a new symbol group, the old symbol group can be updated.</p>

<p>For more information about scopes and symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.</p>

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
<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a>
</dt>
<dt>
<a href="debugger.getscope">GetScope</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::GetScopeSymbolGroup method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>