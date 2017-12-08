---
UID: NC.wsk.PFN_WSK_DISCONNECT
title: PFN_WSK_DISCONNECT
author: windows-driver-content
description: The WskDisconnect function disconnects a connection-oriented or stream socket from a remote transport address.
old-location: netvista\wskdisconnect.htm
old-project: netvista
ms.assetid: 499ff5d0-2030-472c-8de2-44dcd253d7b9
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WPP_TRIAGE_INFO, WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WskDisconnect
req.alt-loc: wsk.h
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
req.product: Windows 10 or later.
---

# PFN_WSK_DISCONNECT callback



## -description
<p>The 
  <b>WskDisconnect</b> function disconnects a connection-oriented or stream socket from a remote transport
  address.</p>


## -prototype

````
NTSTATUS WSKAPI * WskDisconnect(
  _In_     PWSK_SOCKET Socket,
  _In_opt_ PWSK_BUF    Buffer,
  _In_     ULONG       Flags,
  _Inout_  PIRP        Irp
);
````


## -parameters
<dl>

### -param Socket [in]

<dd>
<p>A pointer to a 
     <a href="..\wsk\ns-wsk--wsk-socket.md">WSK_SOCKET</a> structure that specifies the socket
     object for the socket that is being disconnected.</p>
</dd>

### -param Buffer [in, optional]

<dd>
<p>A pointer to a 
     <a href="..\wsk\ns-wsk--wsk-buf.md">WSK_BUF</a> structure. This structure describes a data
     buffer that contains data to be transmitted by the WSK subsystem to the remote transport address before
     the socket is disconnected. If there is no such data to be transmitted, the WSK application sets this
     pointer to <b>NULL</b>. If WSK_FLAG_ABORTIVE is specified in the 
     <i>Flags</i> parameter, the 
     <i>Buffer</i> parameter must be <b>NULL</b>.</p>
</dd>

### -param Flags [in]

<dd>
<p>A ULONG value that contains the following flag, or zero:
     </p>
<p></p>
<dl>

### -param WSK_FLAG_ABORTIVE

<dd>
<p>Directs the WSK subsystem to perform an abortive disconnect of the socket. If a WSK application
       does not specify this flag, the WSK subsystem will perform a graceful disconnect of the socket.</p>
</dd>
</dl>
</dd>

### -param Irp [in, out]

<dd>
<p>A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the disconnect
     operation asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="netvista.using_irps_with_winsock_kernel_functions">Using IRPs with Winsock
     Kernel Functions</a>.</p>
</dd>
</dl>

## -returns
<p><b>WskDisconnect</b> returns one of the following NTSTATUS codes:</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The socket was successfully disconnected from the remote transport address. The IRP will be
       completed with success status.</p><dl>
<dt><b>STATUS_PENDING</b></dt>
</dl><p>The WSK subsystem could not disconnect the socket immediately. The WSK subsystem will complete
       the IRP after it has disconnected the socket from the remote transport address. The status of the
       disconnect operation will be returned in the 
       <b>IoStatus.Status</b> field of the IRP.</p><dl>
<dt><b>STATUS_FILE_FORCED_CLOSED</b></dt>
</dl><p>The socket is no longer functional. The IRP will be completed with failure status. The WSK
       application must call the 
       <a href="..\wsk\nc-wsk-pfn-wsk-close-socket.md">WskCloseSocket</a> function to close the
       socket as soon as possible.</p><dl>
<dt><b>Other status codes</b></dt>
</dl><p>An error occurred. The IRP will be completed with failure status.</p>

<p> </p>

## -remarks
<p>A WSK application can call the 
    <b>WskDisconnect</b> function only on a connection-oriented or stream socket that it previously connected to a
    remote transport address or on a socket that it accepted on a listening socket.</p>

<p><b>WskDisconnect</b> causes the WSK subsystem to notify the remote transport address, through whatever
    means is appropriate for the underlying transport, that the connection is being disconnected. If the 
    <i>Buffer</i> parameter is non-<b>NULL</b>, the WSK subsystem transmits the data in the buffer to the remote
    transport address before disconnecting the socket.</p>

<p>If a graceful disconnect is performed, the WSK subsystem waits until all outstanding transmit data has
    been sent before disconnecting the socket. After the socket has been disconnected, the WSK application
    cannot send any additional data to the remote transport address. However, the WSK application can still
    receive additional data from the remote transport address until the remote application disconnects its
    end of the socket.</p>

<p>Note that not all transports support half-open connections. If a transport does not support half-open
    connections, the WSK application will not receive any additional data from the remote transport address
    after a graceful disconnect has been performed.</p>

<p>With a graceful disconnect, the IRP is completed only when the disconnect operation is fully completed
    by the transport protocol. For some transport protocols, the IRP might not complete if there is a problem
    transmitting data to the remote transport address. In this situation, the WSK application can recover by
    either calling the 
    <b>WskDisconnect</b> function again and specifying the WSK_FLAG_ABORTIVE flag or by calling the 
    <a href="..\wsk\nc-wsk-pfn-wsk-close-socket.md">WskCloseSocket</a> function. In either
    situation, the WSK subsystem will abortively disconnect the socket and force completion of the pending
    IRP.</p>

<p>If an abortive disconnect is performed, the WSK subsystem cancels all in-progress and pending transmit
    operations and does not wait to disconnect the socket. After an abortive disconnect, the WSK application
    cannot send any additional data to the remote transport address or receive any additional data from the
    remote transport address.</p>

<p>A WSK application can completely close the connection by calling the 
    <b>WskCloseSocket</b> function.</p>

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
<p>Available in Windows Vista and later versions of the Windows operating
   systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wsk.h (include Wsk.h)</dt>
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
<a href="..\wsk\nc-wsk-pfn-wsk-close-socket.md">WskCloseSocket</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-connect.md">WskConnect</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-socket-connect.md">WskSocketConnect</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-disconnect-event.md">WskDisconnectEvent</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk--wsk-buf.md">WSK_BUF</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk--wsk-provider-connection-dispatch.md">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk--wsk-provider-stream-dispatch.md">WSK_PROVIDER_STREAM_DISPATCH</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk--wsk-socket.md">WSK_SOCKET</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_DISCONNECT callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>