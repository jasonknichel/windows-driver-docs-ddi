---
UID: NC.ndis.MINIPORT_CANCEL_DIRECT_OID_REQUEST
title: MINIPORT_CANCEL_DIRECT_OID_REQUEST
author: windows-driver-content
description: NDIS calls a miniport driver's MiniportCancelDirectOidRequest function to cancel a direct OID request.
old-location: netvista\miniportcanceldirectoidrequest.htm
old-project: netvista
ms.assetid: 88639bb4-89f3-4e7f-9cce-ea541224572d
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MiniportCancelDirectOidRequest
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# MINIPORT_CANCEL_DIRECT_OID_REQUEST callback



## -description
<p>NDIS calls a miniport driver's 
   <i>MiniportCancelDirectOidRequest</i> function to cancel a direct OID request.</p>


## -prototype

````
MINIPORT_CANCEL_DIRECT_OID_REQUEST MiniportCancelDirectOidRequest;

VOID MiniportCancelDirectOidRequest(
  _In_ NDIS_HANDLE MiniportAdapterContext,
  _In_ PVOID       RequestId
)
{ ... }
````


## -parameters
<dl>

### -param MiniportAdapterContext [in]

<dd>
<p>A handle to a context area that the miniport driver allocated in its 
     <a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for a miniport adapter.</p>
</dd>

### -param RequestId [in]

<dd>
<p>A cancellation identifier for the request. This identifier specifies the direct OID requests that
     match this value in the 
     <b>RequestId</b> member of the 
     <a href="..\ndis\ns-ndis--ndis-oid-request.md">NDIS_OID_REQUEST</a> structure.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p><i>MiniportCancelDirectOidRequest</i> is an optional function. A miniport driver registers this function
    if it handles direct OID requests. A driver specifies the 
    <i>MiniportCancelDirectOidRequest</i> entry point when it calls the 
    <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
    NdisMRegisterMiniportDriver</a> function. A miniport driver that registers the 
    <a href="..\ndis\nc-ndis-miniport-direct-oid-request.md">
    MiniportDirectOidRequest</a> function must also register 
    <i>MiniportCancelDirectOidRequest</i>.</p>

<p>When NDIS calls 
    <i>MiniportCancelDirectOidRequest</i>, the miniport driver should attempt to call 
    <a href="..\ndis\nf-ndis-ndismdirectoidrequestcomplete.md">
    NdisMDirectOidRequestComplete</a> function as soon as possible.</p>

<p>NDIS calls 
    <i>MiniportCancelDirectOidRequest</i> when the originator of the request cancels the request. For direct
    OID requests, NDIS does not call 
    <i>MiniportCancelDirectOidRequest</i> if the time-out expires. (The time-out is specified at the 
    <b>Timeout</b> member of each 
    <a href="..\ndis\ns-ndis--ndis-oid-request.md">NDIS_OID_REQUEST</a> structure.)</p>

<p>If the request processing is still not complete in a miniport driver, the driver calls the 
    <b>NdisMDirectOidRequestComplete</b> function with the status set to NDIS_STATUS_REQUEST_ABORTED.</p>

<p>If the request processing is still not complete in an intermediate driver and the request was
    propagated to an underlying driver, the intermediate driver calls the 
    <a href="..\ndis\nf-ndis-ndiscanceldirectoidrequest.md">
    NdisCancelDirectOidRequest</a> function with the 
    <i>OidRequest</i> parameter set to the value that it sent to the underlying driver.</p>

<p>NDIS calls 
    <i>MiniportCancelDirectOidRequest</i> at IRQL &lt;= DISPATCH_LEVEL.</p>

<p>To define a <i>MiniportCancelDirectOidRequest</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>MiniportCancelDirectOidRequest</i> function that is named "MyCancelDirectOidRequest", use the <b>MINIPORT_CANCEL_DIRECT_OID_REQUEST</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>MINIPORT_CANCEL_DIRECT_OID_REQUEST</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_CANCEL_DIRECT_OID_REQUEST</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.1 and later.</p>
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
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-direct-oid-request.md">MiniportDirectOidRequest</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--ndis-oid-request.md">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscanceldirectoidrequest.md">NdisCancelDirectOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismdirectoidrequestcomplete.md">
   NdisMDirectOidRequestComplete</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_CANCEL_DIRECT_OID_REQUEST callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>