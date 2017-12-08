---
UID: NF.dbgeng.IDebugControl5.GetBreakpointByGuid
title: IDebugControl5::GetBreakpointByGuid
author: windows-driver-content
description: The GetBreakpointByGuid method returns the breakpoint with the specified breakpoint GUID.
old-location: debugger\idebugcontrol5_getbreakpointbyguid.htm
old-project: debugger
ms.assetid: AC316591-CCF9-4040-B1A3-29AB2033B673
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugControl5, GetBreakpointByGuid, IDebugControl5::GetBreakpointByGuid
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugControl5.GetBreakpointByGuid
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
req.iface: IDebugControl5
---

# IDebugControl5::GetBreakpointByGuid method



## -description
<p>The GetBreakpointByGuid method returns the breakpoint with the specified breakpoint GUID.</p>


## -syntax

````
HRESULT GetBreakpointByGuid(
  [in]  LPGUID             Guid,
  [out] PDEBUG_BREAKPOINT3 *Bp
);
````


## -parameters
<dl>

### -param Guid [in]

<dd>
<p>Specifies the breakpoint GUID of the breakpoint to return.</p>
</dd>

### -param Bp [out]

<dd>
<p>Receives the breakpoint.</p>
</dd>
</dl>

## -returns
<p>This method can also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p><dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl><p>No breakpoint was found with the given GUID, or the breakpoint with the specified GUID does not belong to the current process, or the breakpoint with the given GUID is private (see <a href="debugger.getflags">GetFlags</a>). </p>

<p> </p>

## -remarks


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
<dt>Dbgeng.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol5.md">IDebugControl5</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl5::GetBreakpointByGuid method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>