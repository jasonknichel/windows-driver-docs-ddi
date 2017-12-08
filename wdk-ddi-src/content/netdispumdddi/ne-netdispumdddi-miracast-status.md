---
UID: NE.netdispumdddi.MIRACAST_STATUS
title: MIRACAST_STATUS
author: windows-driver-content
description: Specifies status types that the user-mode display driver uses to report Miracast connection status.
old-location: display\miracast_status.htm
old-project: display
ms.assetid: 26949ef9-ddcd-496d-b7e2-7c971bfaf3fb
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: NDK_SRQ, NDK_SRQ
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MIRACAST_STATUS
req.alt-loc: Netdispumdddi.h
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
req.iface: 
---

# MIRACAST_STATUS enumeration



## -description
<p>Specifies status types  that the user-mode display driver uses to report Miracast connection status.</p>


## -syntax

````
typedef enum  { 
  MIRACAST_STATUS_CRITICAL_ERROR                    = 0,
  MIRACAST_STATUS_MISSING_KEEPALIVE                 = 1,
  MIRACAST_STATUS_SINK_DISOCNNECT_REQUEST           = 2,
  MIRACAST_STATUS_INSUFFICIENT_BANDWIDTH            = 3,
  MIRACAST_STATUS_SINK_FAILED_STANDARD_MODE_CHANGE  = 4,
  MIRACAST_STATUS_FORCE_UINT32                      = 0xffffffff
} MIRACAST_STATUS;
````


## -enum-fields
<dl>

### -field MIRACAST_STATUS_CRITICAL_ERROR

<dd>
<p>An unspecified error occurred, and the Miracast connected session cannot continue.</p>
</dd>

### -field MIRACAST_STATUS_MISSING_KEEPALIVE

<dd>
<p>The Miracast sink failed to respond to the protocol keep-alive message.</p>
</dd>

### -field MIRACAST_STATUS_SINK_DISOCNNECT_REQUEST

<dd>
<p>The Miracast sink requested that it be disconnected.</p>
</dd>

### -field MIRACAST_STATUS_INSUFFICIENT_BANDWIDTH

<dd>
<p>The bandwidth of the wireless connection has changed such that the current mode cannot be sustained.</p>
</dd>

### -field MIRACAST_STATUS_SINK_FAILED_STANDARD_MODE_CHANGE

<dd>
<p>The Miracast sink failed to set a standard Video Electronics Standards Association (VESA) setting, Consumer Electronics Association (CEA) standard setting, or a hand-held mode change.</p>
</dd>

### -field MIRACAST_STATUS_FORCE_UINT32

<dd>
<p>Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Netdispumdddi.h (include Netdispumdddi.h)</dt>
</dl>
</td>
</tr>
</table>