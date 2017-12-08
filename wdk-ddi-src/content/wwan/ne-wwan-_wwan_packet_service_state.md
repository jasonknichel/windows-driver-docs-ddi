---
UID: NE.wwan._WWAN_PACKET_SERVICE_STATE
title: _WWAN_PACKET_SERVICE_STATE
author: windows-driver-content
description: The WWAN_PACKET_SERVICE_STATE enumeration lists the different packet service attachment states that are supported by the MB device.
old-location: netvista\wwan_packet_service_state.htm
old-project: netvista
ms.assetid: 542a8a3b-7704-434c-ad81-0cf8e1f70015
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WWAN_PACKET_SERVICE_STATE, WWAN_PACKET_SERVICE_STATE, *PWWAN_PACKET_SERVICE_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WWAN_PACKET_SERVICE_STATE
req.alt-loc: wwan.h
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
req.product: Windows 10 or later.
---

# _WWAN_PACKET_SERVICE_STATE enumeration



## -description
The WWAN_PACKET_SERVICE_STATE enumeration lists the different packet service attachment states that
  are supported by the MB device.


## -syntax

````
typedef enum _WWAN_PACKET_SERVICE_STATE { 
  WwanPacketServiceStateUnknown    = 0,
  WwanPacketServiceStateAttaching,
  WwanPacketServiceStateAttached,
  WwanPacketServiceStateDetaching,
  WwanPacketServiceStateDetached
} WWAN_PACKET_SERVICE_STATE, *PWWAN_PACKET_SERVICE_STATE;
````


## -enum-fields

### -field WwanPacketServiceStateUnknown

Packet service state is unknown. The miniport driver should specify this state on a failure to set
     the MB packet service state.

### -field WwanPacketServiceStateAttaching

Packet service attach action is in progress.

### -field WwanPacketServiceStateAttached

Packet service is attached.

### -field WwanPacketServiceStateDetaching

Packet service detach action is in progress.

### -field WwanPacketServiceStateDetached

Packet service is detached.

## -remarks
The packet service attach or detach state is typically reflected in the device's user interface.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows 7 and later versions of Windows.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wwan.h (include Wwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.wwan_packet_service">WWAN_PACKET_SERVICE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PACKET_SERVICE_STATE enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>