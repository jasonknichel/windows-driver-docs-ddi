---
UID: NF.rxcontx.RxResumeBlockedOperations_Serially
title: RxResumeBlockedOperations_Serially
author: windows-driver-content
description: RxResumeBlockedOperations_Serially wakes up the next waiting thread, if any, on the serialized blocking I/O queue.
old-location: ifsk\rxresumeblockedoperations_serially.htm
old-project: ifsk
ms.assetid: 8418ed17-39f0-4a3b-9eb5-453c7cc2ae98
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RxResumeBlockedOperations_Serially
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxcontx.h
req.include-header: Rxcontx.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxResumeBlockedOperations_Serially
req.alt-loc: rxcontx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# RxResumeBlockedOperations_Serially function



## -description
<p><b>RxResumeBlockedOperations_Serially </b>wakes up the next waiting thread, if any, on the serialized blocking I/O queue.</p>


## -syntax

````
VOID RxResumeBlockedOperations_Serially(
  _Inout_ PRX_CONTEXT RxContext,
  _Inout_ PLIST_ENTRY BlockingIoQ
);
````


## -parameters
<dl>

### -param RxContext [in, out]

<dd>
<p>A pointer to the RX_CONTEXT structure of the operation being synchronized. </p>
</dd>

### -param BlockingIoQ [in, out]

<dd>
<p>A pointer to the blocking I/O queue. </p>
</dd>
</dl>

## -returns
<p>None </p>

## -remarks
<p><b>RxResumeBlockedOperations_Serially </b>wakes up the next work item on a serialized blocking I/O queue, if one exists. The FCB structure must still be valid because of the reference that is being held by the I/O system on the file object, thereby preventing a close operation.</p>

<p>A serialized blocking I/O queue is one for which the <b>FlagsForLowIo</b> member of the RX_CONTEXT structure pointed to by <i>RxContext</i> has the RXCONTEXT_FLAG4LOWIO_PIPE_SYNC_OPERATION bit set. </p>

<p><b>RxResumeBlockedOperations_Serially </b>performs this operation by calling <b>RxFsdPostRequest</b> to post the operation to a worker thread. </p>

<p>The <b>RxResumeBlockedOperations_Serially </b>routine is normally not called directly by a network mini-redirector driver, but is called internally by RDBSS when processing synchronous read and write operations on a named pipe that requires a serialized queue. </p>

<p>A network mini-redirector may need to call <b>RxResumeBlockedOperations_Serially</b> if an RX_CONTEXT has been placed on a synchronization queue using <b>__RxSynchronizeBlockingOperations</b> or <b>__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</b>. </p>

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
<dt>Rxcontx.h (include Rxcontx.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxcompleterequest-real.md">RxCompleteRequest_Real</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx-rxcreaterxcontext.md">RxCreateRxContext</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx-rxdereferenceanddeleterxcontext-real.md">RxDereferenceAndDeleteRxContext_Real</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxfsdpostrequest.md">RxFsdPostRequest</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx-rxinitializecontext.md">RxInitializeContext</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx-rxpreparecontextforreuse.md">RxPrepareContextForReuse</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx---rxsynchronizeblockingoperations.md">__RxSynchronizeBlockingOperations</a>
</dt>
<dt>
<a href="ifsk.__rxsynchronizeblockingoperationsmaybedroppingfcblock">__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxResumeBlockedOperations_Serially  function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>