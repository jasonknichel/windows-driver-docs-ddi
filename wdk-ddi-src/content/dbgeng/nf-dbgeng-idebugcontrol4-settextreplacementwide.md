---
UID: NF.dbgeng.IDebugControl4.SetTextReplacementWide
title: IDebugControl4::SetTextReplacementWide
author: windows-driver-content
description: The SetTextReplacementWide method sets the value of a user-named alias.
old-location: debugger\settextreplacementwide.htm
old-project: debugger
ms.assetid: bbd3fbc0-6dbe-4200-8fe8-e7ca9e4c9478
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugControl4, SetTextReplacementWide, IDebugControl4::SetTextReplacementWide
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
req.alt-api: IDebugControl4.SetTextReplacementWide
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
req.iface: IDebugControl4
---

# IDebugControl4::SetTextReplacementWide method



## -description
<p>The <b>SetTextReplacementWide</b>  method sets the value of a user-named alias.  </p>


## -syntax

````
HRESULT SetTextReplacementWide(
  [in]           PCWSTR SrcText,
  [in, optional] PCWSTR DstText
);
````


## -parameters
<dl>

### -param SrcText [in]

<dd>
<p>Specifies the name of the user-named alias.  The <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a> makes a copy of this string.  If <i>SrcText</i> is the same as the name of an automatic alias, the automatic alias is hidden by the new user-named alias.</p>
</dd>

### -param DstText [in, optional]

<dd>
<p>Specifies the value of the user-named alias.  The debugger engine makes a copy of this string.  If <i>DstText</i> is <b>NULL</b>, the user-named alias is removed.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>Before executing commands or evaluating expressions, the debugger engine will replace the alias specified by <i>SrcText</i> with the value of the alias (specified by <i>DstText</i>).</p>

<p>If <i>SrcText</i> is an asterisk (<b>*</b>) and <i>DstText</i> is <b>NULL</b>, all user-named aliases are removed.  This is the same behavior as the <a href="debugger.removetextreplacements">RemoveTextReplacements</a> method.</p>

<p>When an alias is changed by this method, the event callbacks are notified by passing the DEBUG_CES_TEXT_REPLACEMENTS flag to the <a href="debugger.idebugeventcallbacks_changeenginestate">IDebugEventCallbacks::ChangeEngineState</a> callback method.</p>

<p>For an overview of aliases used by the <a href="debugger.introduction#debugger_engine#debugger_engine">debugger engine</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560047">Using Aliases</a>.  For more information about using aliases with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551041">Interacting with the Engine</a>.</p>

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
<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>
</dt>
<dt>
<a href="debugger.gettextreplacement">GetTextReplacement</a>
</dt>
<dt>
<a href="debugger.removetextreplacements">RemoveTextReplacements</a>
</dt>
<dt>
<a href="debugger.outputtextreplacements">OutputTextReplacements</a>
</dt>
<dt>
<a href="debugger.settextmacro">SetTextMacro</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/6e42122b-5a18-403b-a19a-1346bea8da12">as, aS (Set Alias)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537997">ad (Delete Alias)</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::SetTextReplacementWide method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>