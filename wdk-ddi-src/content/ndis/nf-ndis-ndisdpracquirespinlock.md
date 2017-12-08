---
UID: NF.ndis.NdisDprAcquireSpinLock
title: NdisDprAcquireSpinLock
author: windows-driver-content
description: The NdisDprAcquireSpinLock function acquires a spin lock so the caller can synchronize access to resources shared among non-ISR driver functions in a multiprocessor-safe way.
old-location: netvista\ndisdpracquirespinlock.htm
old-project: netvista
ms.assetid: 2e21d2f8-467e-43d3-8261-2373a8b8daa4
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NdisDprAcquireSpinLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisDprAcquireSpinLock (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisDprAcquireSpinLock (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisDprAcquireSpinLock
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Synch_Function, SpinLock, SpinLockBalanced, SpinLockDpr, SpinLockDprRelease, SpinlockRelease
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: DISPATCH_LEVEL
req.iface: 
---

# NdisDprAcquireSpinLock function



## -description
<p>The 
  <b>NdisDprAcquireSpinLock</b> function acquires a spin lock so the caller can synchronize access to
  resources shared among non-ISR driver functions in a multiprocessor-safe way.</p>


## -syntax

````
VOID NdisDprAcquireSpinLock(
  _In_ PNDIS_SPIN_LOCK SpinLock
);
````


## -parameters
<dl>

### -param SpinLock [in]

<dd>
<p>Pointer to an opaque spin lock, already initialized by the caller.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The miniport driver must initialize a variable of type NDIS_SPIN_LOCK with 
    <a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a> before it calls
    any other 
    <b>Ndis..SpinLock</b> function. The driver must provide resident storage for the spin lock(s) it uses.</p>

<p><b>NdisDprAcquireSpinLock</b> is an optimized version of 
    <a href="..\ndis\nf-ndis-ndisacquirespinlock.md">NdisAcquireSpinLock</a> that a miniport
    driver can call only while running at IRQL = DISPATCH_LEVEL.</p>

<p>After acquiring a spin lock with 
    <b>NdisDprAcquireSpinLock</b>, the caller must release that lock with a call to 
    <a href="..\ndis\nf-ndis-ndisdprreleasespinlock.md">NdisDprReleaseSpinLock</a>. A miniport
    driver must call 
    <b>NdisDprReleaseSpinLock</b> following each call to 
    <b>NdisDprAcquireSpinLock</b>. Otherwise, a deadlock occurs, hanging the driver.</p>

<p>A spin lock acquired with 
    <b>NdisDprAcquireSpinLock</b> must be released with 
    <b>NdisDprReleaseSpinLock</b>. A spin lock acquired with 
    <b>NdisAcquireSpinLock</b> must be released with 
    <b>NdisReleaseSpinLock</b>.</p>

<p>A driver should never hold a spin lock for an extended period (more than a few instructions). Holding
    a spin lock for longer than 25 microseconds degrades both system and driver performance.</p>

<p>A miniport driver cannot use a spin lock to protect resources that its other functions share with the 
    <a href="..\ndis\nc-ndis-miniport-isr.md">MiniportInterrupt</a> and/or 
    <a href="..\ndis\nc-ndis-miniport-disable-interrupt.md">
    MiniportDisableInterruptEx</a> functions. Instead, a miniport driver must call 
    <a href="..\ndis\nf-ndis-ndismsynchronizewithinterruptex.md">
    NdisMSynchronizeWithInterruptEx</a> so that its 
    <a href="..\ndis\nc-ndis-miniport-synchronize-interrupt.md">
    MiniportSynchronizeInterrupt</a> function accesses such shared resources at the same DIRQL at which its
    
    <i>MiniportInterrupt</i> and/or 
    <i>MiniportDisableInterruptEx</i> functions do.</p>

<p>For more information about acquiring and releasing NDIS spin locks, see 
    <a href="netvista.synchronization_and_notification_in_network_drivers">Synchronization
    and Notification in Network Drivers</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/0ea9c973-95ea-419e-bac5-e69858c09627">NdisDprAcquireSpinLock (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisDprAcquireSpinLock (NDIS
   5.1)</b>) in Windows XP.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.ndis_irql_synch_function">Irql_Synch_Function</a>, <a href="devtest.ndis_spinlock">SpinLock</a>, <a href="devtest.ndis_spinlockbalanced">SpinLockBalanced</a>, <a href="devtest.ndis_spinlockdpr">SpinLockDpr</a>, <a href="devtest.ndis_spinlockdprrelease">SpinLockDprRelease</a>, <a href="devtest.ndis_spinlockrelease">SpinlockRelease</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport-disable-interrupt.md">MiniportDisableInterruptEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-isr.md">MiniportInterrupt</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-synchronize-interrupt.md">
   MiniportSynchronizeInterrupt</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-ndis-timer-function.md">NetTimerCallback</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisacquirespinlock.md">NdisAcquireSpinLock</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatespinlock.md">NdisAllocateSpinLock</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisdprreleasespinlock.md">NdisDprReleaseSpinLock</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismsynchronizewithinterruptex.md">
   NdisMSynchronizeWithInterruptEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisDprAcquireSpinLock function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>