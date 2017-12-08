---
UID: NF.vmbuskernelmodeclientlibapi.VmbClientChannelInitSetTargetPnp
title: VmbClientChannelInitSetTargetPnp function
author: windows-driver-content
description: The VmbClientChannelInitSetTargetPnp function sets a client channel's target by interface type and instance IDs.
old-location: netvista\vmbclientchannelinitsettargetpnp.htm
old-project: netvista
ms.assetid: 5525FD48-BE65-48CA-B3D5-C96AFD4ECF56
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: VmbClientChannelInitSetTargetPnp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.alt-api: VmbClientChannelInitSetTargetPnp
req.alt-loc: vmbkmcl.lib,vmbkmcl.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Vmbkmcl.lib
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# VmbClientChannelInitSetTargetPnp function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]
The <b>VmbClientChannelInitSetTargetPnp</b> function sets a client channel's target by interface type and instance IDs. If this
function is called, Kernel Mode Client Library (KMCL) uses PnP to find the VMBus Physical Device Object (PDO) that corresponds to the
provided interface. 


## -syntax

````
NTSTATUS VmbClientChannelInitSetTargetPnp(
  _In_     VMBCHANNEL                  Channel,
  _In_     LPCGUID                     InterfaceType,
  _In_opt_ LPCGUID                     InterfaceInstance,
  _In_opt_ PFN_VMB_CHANNEL_PNP_FAILURE PnpFailureCallback
);
````


## -parameters

### -param Channel [in]

A pointer to a channel.


### -param InterfaceType [in]

A pointer to the interface type GUID.
This GUID identifies the 
type of channel and the protocol that is used with the channel.  

### -param InterfaceInstance [in, optional]

A pointer to the instance type GUID. This is a 
specific instance of the service. If not
provided, any instance with the provided type is accepted.


### -param PnpFailureCallback [in, optional]

A pointer to an event callback to call if the
device asynchronously fails to connect even though the PnP device was
located.

## -returns
<b>VmbClientChannelInitSetTargetPnp</b> returns the following values: 
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>The <i>Channel</i> value was invalid or in an invalid state, such as Disabled.

 

## -remarks
If you 
have two paravirtual network interfaces, they will have the 
same <i>InterfaceType</i> but different <i>InterfaceInstance</i> values. 

## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 8.1
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2012 R2
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.13
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
<dt>VmbusKernelModeClientLibApi.h (include VmbusKernelModeClientLibApi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Vmbkmcl.lib</dt>
</dl>
</td>
</tr>
</table>