---
UID: NC.ndis.MINIPORT_DIRECT_OID_REQUEST
title: MINIPORT_DIRECT_OID_REQUEST
author: windows-driver-content
description: NDIS calls a miniport driver's MiniportDirectOidRequest function to handle a direct OID request to query or set information in the driver.
old-location: netvista\miniportdirectoidrequest.htm
old-project: netvista
ms.assetid: 60daba60-3e04-4e98-a458-4dc263f17761
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
req.alt-api: MiniportDirectOidRequest
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

# MINIPORT_DIRECT_OID_REQUEST callback



## -description
<p>NDIS calls a miniport driver's 
   <i>MiniportDirectOidRequest</i> function to handle a direct OID request to query or set information in the
   driver.</p>


## -prototype

````
MINIPORT_DIRECT_OID_REQUEST MiniportDirectOidRequest;

NDIS_STATUS MiniportDirectOidRequest(
  _In_ NDIS_HANDLE       MiniportAdapterContext,
  _In_ PNDIS_OID_REQUEST OidRequest
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

### -param OidRequest [in]

<dd>
<p>A pointer to an 
     <a href="..\ndis\ns-ndis--ndis-oid-request.md">NDIS_OID_REQUEST</a> structure that contains
     both the buffer and the request packet for the miniport driver to handle. Depending on the request, the
     driver returns requested information in the structure that is provided.</p>
</dd>
</dl>

## -returns
<p><i>MiniportDirectOidRequest</i> can return one of the following status values:</p><dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><p>The miniport driver set or obtained the data as requested.</p><dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl><p>The miniport driver will complete the request asynchronously. After the miniport driver has
       completed all processing, it must call the 
       <a href="..\ndis\nf-ndis-ndismdirectoidrequestcomplete.md">
       NdisMDirectOidRequestComplete</a> function to inform NDIS that the request is complete.</p><dl>
<dt><b>NDIS_STATUS_INVALID_OID</b></dt>
</dl><p>The request that 
       <i>OidRequest</i> specified was invalid or not recognized.</p><dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl><p>The request that 
       <i>OidRequest</i> specified was recognized, but the miniport driver does not support it.</p><dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl><p>The buffer that 
       <i>OidRequest</i> supplies was too small to hold the requested data.</p><dl>
<dt><b>NDIS_STATUS_INVALID_LENGTH</b></dt>
</dl><p>The value that was specified in the 
       <b>InformationBufferLength</b> member of the NDIS_OID_REQUEST structure at 
       <i>OidRequest</i> is incorrect for the specified OID_<i>Xxx</i> code.</p><dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl><p>One or more of the parameters that were specified for the request at 
       <i>OidRequest</i> were invalid.</p><dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl><p>After calling the 
       <a href="..\ndis\nc-ndis-miniport-device-pnp-event-notify.md">
       MiniportDevicePnPEventNotify</a> function to indicate a surprise removal, NDIS called the driver's 
       <a href="..\ndis\nc-ndis-miniport-halt.md">MiniportHaltEx</a> function. If the
       driver received any OID requests before NDIS calls 
       <i>MiniportHaltEx</i>, it should immediately complete such requests with a status value of
       NDIS_STATUS_NOT_ACCEPTED.</p><dl>
<dt><b>NDIS_STATUS_REQUEST_ABORTED</b></dt>
</dl><p>The miniport driver stopped processing the request. For example, NDIS called the 
       <a href="..\ndis\nc-ndis-miniport-reset.md">MiniportResetEx</a> function.</p><dl>
<dt><b>NDIS_STATUS_INDICATION_REQUIRED</b></dt>
</dl><p>The miniport driver will provide an OID completion status with a subsequent status indication. A
       miniport driver cannot return NDIS_STATUS_INDICATION_REQUIRED unless the particular OID allows it. To
       determine if this status is allowed, see the OID reference page.. For more information about
       NDIS_STATUS_INDICATION_REQUIRED, see 
       <a href="..\ndis\ns-ndis--ndis-oid-request.md">NDIS_OID_REQUEST</a> and 
       <a href="..\ndis\ns-ndis--ndis-status-indication.md">NDIS_STATUS_INDICATION</a>.</p>

<p> </p>

## -remarks
<p><i>MiniportDirectOidRequest</i> is an optional function. A miniport driver registers this function if it
    handles direct OID requests. A driver specifies the 
    <i>MiniportDirectOidRequest</i> entry point when it calls the 
    <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
    NdisMRegisterMiniportDriver</a> function. A miniport driver that registers the 
    <a href="..\ndis\nc-ndis-miniport-cancel-direct-oid-request.md">
    MiniportCancelDirectOidRequest</a> function must also register 
    <i>MiniportDirectOidRequest</i>.</p>

<p>NDIS calls the 
    <i>MiniportDirectOidRequest</i> function either on its own behalf or on behalf of a bound protocol driver
    that called the 
    <a href="..\ndis\nf-ndis-ndisdirectoidrequest.md">NdisDirectOidRequest</a> function.
    Miniport drivers should examine the request that is supplied at the 
    <i>OidRequest</i> parameter and take the action requested.</p>

<p>Note that NDIS does not validate the OID-specific contents at 
    <i>OidRequest</i>. Therefore, the driver itself must validate these contents. If the driver determines
    that the value to be set is out of bounds, it should fail the request and return
    NDIS_STATUS_INVALID_DATA.</p>

<p>NDIS does not serialize requests that it sends to 
    <i>MiniportDirectOidRequest</i> with other OID requests. The miniport driver must be able to handle
    multiple calls to 
    <i>MiniportDirectOidRequest</i> when other requests that are sent to 
    <a href="..\ndis\nc-ndis-miniport-oid-request.md">MiniportOidRequest</a> or 
    <i>MiniportDirectOidRequest</i> are outstanding.</p>

<p>NDIS calls 
    <i>MiniportDirectOidRequest</i> at IRQL &lt;= DISPATCH_LEVEL.</p>

<p>To define a <i>MiniportDirectOidRequest</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>MiniportDirectOidRequest</i> function that is named "MyDirectOidRequest", use the <b>MINIPORT_DIRECT_OID_REQUEST</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>MINIPORT_DIRECT_OID_REQUEST</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_DIRECT_OID_REQUEST</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

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
<a href="..\ndis\nc-ndis-miniport-halt.md">MiniportHaltEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-cancel-direct-oid-request.md">
   MiniportCancelDirectOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-device-pnp-event-notify.md">
   MiniportDevicePnPEventNotify</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-direct-oid-request.md">MiniportDirectOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-oid-request.md">MiniportOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-reset.md">MiniportResetEx</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--ndis-oid-request.md">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--ndis-status-indication.md">NDIS_STATUS_INDICATION</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisdirectoidrequest.md">NdisDirectOidRequest</a>
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
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_DIRECT_OID_REQUEST callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>