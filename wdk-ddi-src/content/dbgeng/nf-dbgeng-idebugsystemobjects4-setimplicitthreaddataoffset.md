---
UID: NF.dbgeng.IDebugSystemObjects4.SetImplicitThreadDataOffset
title: IDebugSystemObjects4::SetImplicitThreadDataOffset
author: windows-driver-content
description: The SetImplicitThreadDataOffset method sets the implicit thread for the current process.
old-location: debugger\setimplicitthreaddataoffset.htm
old-project: debugger
ms.assetid: 1562a2f4-0eea-44fd-b350-ccc17d8cd65e
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugSystemObjects4, SetImplicitThreadDataOffset, IDebugSystemObjects4::SetImplicitThreadDataOffset
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
req.alt-api: IDebugSystemObjects2.SetImplicitThreadDataOffset,IDebugSystemObjects3.SetImplicitThreadDataOffset,IDebugSystemObjects4.SetImplicitThreadDataOffset
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
req.iface: IDebugSystemObjects4
---

# IDebugSystemObjects4::SetImplicitThreadDataOffset method



## -description
<p>The <b>SetImplicitThreadDataOffset</b> method sets the implicit thread for the current process.</p>


## -syntax

````
HRESULT SetImplicitThreadDataOffset(
  [in] ULONG64 Offset
);
````


## -parameters
<dl>

### -param Offset [in]

<dd>
<p>Specifies the location in the target's memory address space of the data structure of the system thread that is to become the implicit thread for the current process.  If this is zero, the implicit thread for the current process is set to the default implicit thread.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>In kernel-mode debugging, the data structure is the KTHREAD structure for the process.</p>

<p>In user-mode debugging, the data structure is the thread environment block (TEB) for the process.</p>

<p>For more information about the current implicit thread, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.  For details on the KTHREAD structure and TEB, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich.</p>

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