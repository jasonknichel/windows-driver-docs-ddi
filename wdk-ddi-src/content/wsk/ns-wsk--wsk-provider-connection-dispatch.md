---
UID: NS.wsk._WSK_PROVIDER_CONNECTION_DISPATCH
title: WSK_PROVIDER_CONNECTION_DISPATCH
author: windows-driver-content
description: The WSK_PROVIDER_CONNECTION_DISPATCH structure specifies the WSK subsystem's table of functions for a connection-oriented socket.
old-location: netvista\wsk_provider_connection_dispatch.htm
old-project: netvista
ms.assetid: 70a86809-07f2-4723-9e50-4dbdd31ff900
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WSK_PROVIDER_CONNECTION_DISPATCH, WSK_PROVIDER_CONNECTION_DISPATCH, *PWSK_PROVIDER_CONNECTION_DISPATCH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WSK_PROVIDER_CONNECTION_DISPATCH
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

# WSK_PROVIDER_CONNECTION_DISPATCH structure



## -description
<p>The WSK_PROVIDER_CONNECTION_DISPATCH structure specifies the WSK subsystem's table of functions for a
  connection-oriented socket.</p>


## -syntax

````
typedef struct _WSK_PROVIDER_CONNECTION_DISPATCH {
  WSK_PROVIDER_BASIC_DISPATCH          Basic;
  PFN_WSK_BIND                         WskBind;
  PFN_WSK_CONNECT                      WskConnect;
  PFN_WSK_GET_LOCAL_ADDRESS            WskGetLocalAddress;
  PFN_WSK_GET_REMOTE_ADDRESS           WskGetRemoteAddress;
  PFN_WSK_SEND                         WskSend;
  PFN_WSK_RECEIVE                      WskReceive;
  PFN_WSK_DISCONNECT                   WskDisconnect;
  PFN_WSK_RELEASE_DATA_INDICATION_LIST WskRelease;
  PFN_WSK_CONNECT_EX                   WskConnectEx;
} WSK_PROVIDER_CONNECTION_DISPATCH, *PWSK_PROVIDER_CONNECTION_DISPATCH;
````


## -struct-fields
<dl>

### -field Basic

<dd>
<p>The members of the 
     <a href="..\wsk\ns-wsk--wsk-provider-basic-dispatch.md">
     WSK_PROVIDER_BASIC_DISPATCH</a> structure are included as members of the 
     <b>WSK_PROVIDER_CONNECTION_DISPATCH</b> structure.</p>
</dd>

### -field WskBind

<dd>
<p>A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn-wsk-bind.md">WskBind</a> function for the socket.</p>
</dd>

### -field WskConnect

<dd>
<p>A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn-wsk-connect.md">WskConnect</a> function for the socket.</p>
</dd>

### -field WskGetLocalAddress

<dd>
<p>A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn-wsk-get-local-address.md">WskGetLocalAddress</a> function for the
     socket.</p>
</dd>

### -field WskGetRemoteAddress

<dd>
<p>A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn-wsk-get-remote-address.md">WskGetRemoteAddress</a> function for the
     socket.</p>
</dd>

### -field WskSend

<dd>
<p>A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn-wsk-send.md">WskSend</a> function for the socket.</p>
</dd>

### -field WskReceive

<dd>
<p>A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn-wsk-receive.md">WskReceive</a> function for the socket.</p>
</dd>

### -field WskDisconnect

<dd>
<p>A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn-wsk-disconnect.md">WskDisconnect</a> function for the
     socket.</p>
</dd>

### -field WskRelease

<dd>
<p>A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn-wsk-release-data-indication-list.md">WskRelease</a> function for the socket.</p>
</dd>

### -field WskConnectEx

<dd>
<p>A pointer to the WSK subsystem's 
     <a href="..\wsk\nc-wsk-pfn-wsk-connect-ex.md">WskConnectEx</a> function for the
     socket.</p>
</dd>
</dl>

## -remarks
<p>The member list of the WSK_PROVIDER_CONNECTION_DISPATCH structure includes an unnamed 
    <a href="..\wsk\ns-wsk--wsk-provider-basic-dispatch.md">
    WSK_PROVIDER_BASIC_DISPATCH</a> structure. The compiler that is included with the WDK supports a
    Microsoft-specific extension to the C language that allows unnamed structures within structure
    declarations. The result is that the structure members of the WSK_PROVIDER_BASIC_DISPATCH structure are
    included in the WSK_PROVIDER_CONNECTION_DISPATCH structure as if they were native members of the
    WSK_PROVIDER_CONNECTION_DISPATCH structure.</p>

<p>A WSK application receives a pointer to a WSK_PROVIDER_CONNECTION_DISPATCH structure in one of the
    following ways:</p>

<p>The WSK application calls the 
      <a href="..\wsk\nc-wsk-pfn-wsk-socket.md">WskSocket</a> function to create a
      connection-oriented socket.</p>

<p>The WSK application calls the 
      <a href="..\wsk\nc-wsk-pfn-wsk-socket-connect.md">WskSocketConnect</a> function to create,
      bind, and connect a connection-oriented socket.</p>

<p>The WSK application calls the 
      <a href="..\wsk\nc-wsk-pfn-wsk-accept.md">WskAccept</a> function to accept an incoming
      connection-oriented socket on a listening socket.</p>

<p>The WSK subsystem calls the WSK application's 
      <a href="..\wsk\nc-wsk-pfn-wsk-accept-event.md">WskAcceptEvent</a> event callback function to
      notify the WSK application that an incoming connection-oriented socket has been accepted on a listening
      socket.</p>

<p>The pointer to the WSK_PROVIDER_CONNECTION_DISPATCH structure is contained in the 
    <b>Dispatch</b> member of the 
    <a href="..\wsk\ns-wsk--wsk-socket.md">WSK_SOCKET</a> structure that is received from the
    WSK subsystem.</p>

## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-accept.md">WskAccept</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-bind.md">WskBind</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-close-socket.md">WskCloseSocket</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-connect.md">WskConnect</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-control-socket.md">WskControlSocket</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-disconnect.md">WskDisconnect</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-get-local-address.md">WskGetLocalAddress</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-get-remote-address.md">WskGetRemoteAddress</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-receive.md">WskReceive</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-release-data-indication-list.md">WskRelease</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-send.md">WskSend</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-socket.md">WskSocket</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-socket-connect.md">WskSocketConnect</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-accept-event.md">WskAcceptEvent</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk--wsk-client-connection-dispatch.md">
   WSK_CLIENT_CONNECTION_DISPATCH</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk--wsk-provider-basic-dispatch.md">WSK_PROVIDER_BASIC_DISPATCH</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk--wsk-socket.md">WSK_SOCKET</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_PROVIDER_CONNECTION_DISPATCH structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>