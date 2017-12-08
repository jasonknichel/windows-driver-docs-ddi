---
UID: NF.dbgeng.IDebugBreakpoint2.SetOffsetExpression
title: IDebugBreakpoint2::SetOffsetExpression
author: windows-driver-content
description: The SetOffsetExpression methods set an expression string that evaluates to the location that triggers a breakpoint.
old-location: debugger\setoffsetexpression.htm
old-project: debugger
ms.assetid: 63cfb3f2-5240-4cb6-9c23-8cdb363f62a8
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugBreakpoint2, SetOffsetExpression, IDebugBreakpoint2::SetOffsetExpression
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
req.alt-api: IDebugBreakpoint.SetOffsetExpression,IDebugBreakpoint2.SetOffsetExpression
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
req.iface: IDebugBreakpoint2
---

# IDebugBreakpoint2::SetOffsetExpression method



## -description
<p>The <b>SetOffsetExpression</b>  methods set an expression string that evaluates to the location that triggers a breakpoint.</p>


## -syntax

````
HRESULT SetOffsetExpression(
  [in] PCSTR Expression
);
````


## -parameters
<dl>

### -param Expression [in]

<dd>
<p>The expression string that evaluates to the location on the target that triggers the breakpoint.  If the engine icannot evaluate the expression (for example, if the expression contains a symbol that cannot be interpreted), the breakpoint is flagged as deferred. (For more information about deferred breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.)  For more information about the expression syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.</p>
</dd>
</dl>

## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

<p>This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.</p>

## -remarks
<p>For more information about how to use breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.</p>

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