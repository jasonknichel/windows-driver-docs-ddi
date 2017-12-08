---
UID: NF.wdfio.WdfIoQueuePurgeSynchronously
title: WdfIoQueuePurgeSynchronously function
author: windows-driver-content
description: The WdfIoQueuePurgeSynchronously method causes the framework to stop queuing I/O requests to an I/O queue and to cancel unprocessed requests and driver-owned cancellable requests.
old-location: wdf\wdfioqueuepurgesynchronously.htm
old-project: wdf
ms.assetid: 705faf80-79c4-4f2a-a399-d9a26bde54cf
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfIoQueuePurgeSynchronously
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfIoQueuePurgeSynchronously
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: ChangeQueueState, DriverCreate, EvtSurpriseRemoveNoSuspendQueue, KmdfIrql, KmdfIrql2, NoCancelFromEvtSurpriseRemove
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# WdfIoQueuePurgeSynchronously function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WdfIoQueuePurgeSynchronously</b> method causes the framework to stop queuing I/O requests to an I/O queue and to cancel unprocessed requests and driver-owned cancellable requests.


## -syntax

````
VOID WdfIoQueuePurgeSynchronously(
  _In_ WDFQUEUE Queue
);
````


## -parameters

### -param Queue [in]

A handle to a framework queue object.

## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks
After a driver calls <b>WdfIoQueuePurgeSynchronously</b>, the framework stops adding I/O requests to the specified queue. The framework cancels all requests that it has not delivered to the driver. If the framework receives additional requests for the queue, it completes them with a completion status value of STATUS_INVALID_DEVICE_STATE.

<b>WdfIoQueuePurgeSynchronously</b> returns after all the unprocessed and driver-owned requests are completed or canceled.

After a driver has purged an I/O queue, it can restart the queue by calling <a href="wdf.wdfioqueuestart">WdfIoQueueStart</a>.

Do not call <b>WdfIoQueuePurgeSynchronously</b> from the following queue object event callback functions, regardless of the queue with which the event callback function is associated:

For more information about the <b>WdfIoQueuePurgeSynchronously</b> method, see <a href="wdf.managing_i_o_queues">Managing I/O Queues</a>.

The following code example purges a specified I/O queue.

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
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfio.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.kmdf_changequeuestate">ChangeQueueState</a>, <a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_evtsurpriseremovenosuspendqueue">EvtSurpriseRemoveNoSuspendQueue</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>, <a href="devtest.kmdf_nocancelfromevtsurpriseremove">NoCancelFromEvtSurpriseRemove</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfioqueuepurge">WdfIoQueuePurge</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoQueuePurgeSynchronously method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>