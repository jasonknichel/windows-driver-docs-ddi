---
UID: NF.ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlPostStackOverflow~r2
title: FsRtlPostStackOverflow function
author: windows-driver-content
description: The FsRtlPostStackOverflow routine posts a stack overflow item to the stack overflow thread.
old-location: ifsk\fsrtlpoststackoverflow.htm
old-project: ifsk
ms.assetid: fbd6f3b5-ecf7-438e-8e28-a06eaa141fc3
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FsRtlPostStackOverflow
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later versions of Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlPostStackOverflow
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
---

# FsRtlPostStackOverflow function



## -description
The <b>FsRtlPostStackOverflow</b> routine posts a stack overflow item to the stack overflow thread.


## -syntax

````
VOID FsRtlPostStackOverflow(
  _In_ PVOID                         Context,
  _In_ PKEVENT                       Event,
  _In_ PFSRTL_STACK_OVERFLOW_ROUTINE StackOverflowRoutine
);
````


## -parameters

### -param Context [in]

A context pointer to be passed to the stack overflow callback routine.

### -param Event [in]

A pointer to a caller-allocated notification event to pass to the stack overflow callback routine. Must have been initialized as nonsignaled by calling <a href="kernel.keinitializeevent">KeInitializeEvent</a>.

### -param StackOverflowRoutine [in]

A pointer to a callback routine to be invoked when processing the request in the overflow thread.

## -returns
None

## -remarks
A file system typically calls <b>FsRtlPostStackOverflow</b> during a file I/O operation when the amount of remaining stack space returned by <a href="kernel.iogetremainingstacksize">IoGetRemainingStackSize</a> is below the file system's stack overflow threshold for the operation. <b>FsRtlPostStackOverflow</b> posts the I/O request to a special stack overflow work queue. When the I/O operation has been completed, the caller's <i>Event</i> is set to a signaled state. 

File system filter drivers should use <a href="kernel.ioqueueworkitem">IoQueueWorkItem</a> instead of <b>FsRtlPostStackOverflow</b>, because <b>IoQueueWorkItem</b> ensures that the device object that is associated with the specified work item is available for the processing of the work item. 

If a pool allocation failure occurs, <b>FsRtlPostStackOverflow</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. To gain control if this pool allocation failure occurs, the driver should wrap the call to <b>FsRtlPostStackOverflow</b> in a <b>try-except</b> or <b>try-finally</b> statement.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
This routine is available on Microsoft Windows 2000 and later versions of Windows operating systems. 
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include FltKernel.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fsrtlpostpagingfilestackoverflow">FsRtlPostPagingFileStackOverflow</a>
</dt>
<dt>
<a href="kernel.iogetremainingstacksize">IoGetRemainingStackSize</a>
</dt>
<dt>
<a href="kernel.ioqueueworkitem">IoQueueWorkItem</a>
</dt>
<dt>
<a href="kernel.keinitializeevent">KeInitializeEvent</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlPostStackOverflow routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>