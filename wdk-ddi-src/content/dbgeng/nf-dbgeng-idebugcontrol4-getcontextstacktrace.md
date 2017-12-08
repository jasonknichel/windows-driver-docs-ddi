---
UID: NF.dbgeng.IDebugControl4.GetContextStackTrace
title: IDebugControl4::GetContextStackTrace
author: windows-driver-content
description: The GetContextStackTrace method returns the frames at the top of the call stack, starting with an arbitrary register context and returning the reconstructed register context for each stack frame.
old-location: debugger\getcontextstacktrace.htm
old-project: debugger
ms.assetid: 8d7a461e-46bf-4556-b13c-805bb5af572e
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugControl4, GetContextStackTrace, IDebugControl4::GetContextStackTrace
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: Dbgeng.h, Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugControl4.GetContextStackTrace
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

# IDebugControl4::GetContextStackTrace method



## -description
<p>The <b>GetContextStackTrace</b> method returns the frames at the top of the call stack, starting with an arbitrary <a href="debugger.changing_contexts#register_context#register_context">register context</a> and returning the reconstructed register context for each stack frame.</p>


## -syntax

````
HRESULT GetContextStackTrace(
  [in, optional]  PVOID              StartContext,
  [in]            ULONG              StartContextSize,
  [out, optional] PDEBUG_STACK_FRAME Frames,
  [in]            ULONG              FramesSize,
  [out, optional] PVOID              FrameContexts,
  [in]            ULONG              FrameContextsSize,
  [in]            ULONG              FrameContextsEntrySize,
  [out, optional] PULONG             FramesFilled
);
````


## -parameters
<dl>

### -param StartContext [in, optional]

<dd>
<p>Specifies the register context for the top of the stack.</p>
</dd>

### -param StartContextSize [in]

<dd>
<p>Specifies the size, in bytes, of the <i>StartContext</i> register context.</p>
</dd>

### -param Frames [out, optional]

<dd>
<p>Receives the stack frames.  The number of elements this array holds is <i>FrameSize</i>.  If <i>Frames</i> is <b>NULL</b>, this information is not returned.</p>
</dd>

### -param FramesSize [in]

<dd>
<p>Specifies the number of items in the array <i>Frames</i>.</p>
</dd>

### -param FrameContexts [out, optional]

<dd>
<p>Receives the reconstructed register context for each frame in the stack.  The entries in this array correspond to the entries in the <i>Frames</i> array.  The type of the thread context is the CONTEXT structure for the target's effective processor.  If <i>FrameContexts</i> is <b>NULL</b>, this information is not returned.</p>
</dd>

### -param FrameContextsSize [in]

<dd>
<p>Specifies the size, in bytes, of the memory pointed to by <i>FrameContexts</i>.  The number of stack frames returned equals the number of contexts returned, and <i>FrameContextsSize</i> must equal <i>FramesSize</i> times <i>FrameContextsEntrySize</i>.</p>
</dd>

### -param FrameContextsEntrySize [in]

<dd>
<p>Specifies the size, in bytes, of each frame context in <i>FrameContexts</i>.</p>
</dd>

### -param FramesFilled [out, optional]

<dd>
<p>Receives the number of frames that were placed in the array <i>Frames</i> and contexts in <i>FrameContexts</i>.  If <i>FramesFilled</i> is <b>NULL</b>, this information is not returned.</p>
</dd>
</dl>

## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

<p>This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.</p>

## -remarks
<p>The stack trace returned to <i>Frames</i> and <i>FrameContexts</i> can be printed using <a href="debugger.outputcontextstacktrace">OutputContextStackTrace</a>.</p>

<p>It is common for stack unwinds to restore only a subset of the registers.  For example, stack unwinds will not always restore the volatile register state because the volatile registers are scratch registers and code does not need to preserve them.  Registers that are not restored on unwind are left as the last value restored, so care should be taken when using the register state that might not be restored by an unwind.</p>

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
<dt>Dbgeng.h (include Dbgeng.h or Ntddk.h)</dt>
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
<a href="debugger.getstacktrace">GetStackTrace</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/1061015f-cb0c-490b-b256-e0dedb659f22">k, kb, kc, kd, kp, kP, kv (Display Stack Backtrace)</a>
</dt>
<dt>
<a href="debugger.outputcontextstacktrace">OutputContextStackTrace</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetContextStackTrace method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>