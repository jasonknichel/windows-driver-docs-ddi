---
UID: NF.dbgeng.IDebugSystemObjects3.SetCurrentThreadId
title: IDebugSystemObjects3::SetCurrentThreadId
author: windows-driver-content
description: The SetCurrentThreadId method makes the specified thread the current thread.
old-location: debugger\setcurrentthreadid.htm
old-project: debugger
ms.assetid: 965c2fe0-5be5-4036-b649-a25fcc6e2dc2
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugSystemObjects3, SetCurrentThreadId, IDebugSystemObjects3::SetCurrentThreadId
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
req.alt-api: IDebugSystemObjects.SetCurrentThreadId,IDebugSystemObjects2.SetCurrentThreadId,IDebugSystemObjects3.SetCurrentThreadId,IDebugSystemObjects4.SetCurrentThreadId
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
req.iface: IDebugSystemObjects3
---

# IDebugSystemObjects3::SetCurrentThreadId method



## -description
<p>The <b>SetCurrentThreadId</b> method makes the specified thread the current thread.</p>


## -syntax

````
HRESULT SetCurrentThreadId(
  [in] ULONG Id
);
````


## -parameters
<dl>

### -param Id [in]

<dd>
<p>Specifies the engine thread ID of the thread that is to become the current thread.</p>
</dd>
</dl>

## -returns
<p>This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p><dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl><p>No thread with the specified ID was found.</p>

<p> </p>

## -remarks
<p>This method may also change the current process, current target, and current computer.</p>

<p>If the thread is changed, the callback <a href="debugger.idebugeventcallbacks_changeenginestate">IDebugEventCallbacks::ChangeEngineState</a> will be called with the DEBUG_CES_CURRENT_THREAD bit set.</p>

<p>For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on monitoring events, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552239">Monitoring Events</a>.</p>

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