---
UID: NE.wdfusb._WDF_USB_BMREQUEST_DIRECTION
title: WDF_USB_BMREQUEST_DIRECTION
author: windows-driver-content
description: The WDF_USB_BMREQUEST_DIRECTION enumeration identifies the data transfer direction for a USB control transfer.
old-location: wdf\wdf_usb_bmrequest_direction.htm
old-project: wdf
ms.assetid: e39748b8-d84c-4f9e-a790-bff192a6769c
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_TIMER_CONFIG, WDF_TIMER_CONFIG, *PWDF_TIMER_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_USB_BMREQUEST_DIRECTION
req.alt-loc: wdfusb.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# WDF_USB_BMREQUEST_DIRECTION enumeration



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WDF_USB_BMREQUEST_DIRECTION</b> enumeration identifies the data transfer direction for a USB control transfer. </p>


## -syntax

````
typedef enum _WDF_USB_BMREQUEST_DIRECTION { 
  BmRequestHostToDevice  = BMREQUEST_HOST_TO_DEVICE,
  BmRequestDeviceToHost  = BMREQUEST_DEVICE_TO_HOST
} WDF_USB_BMREQUEST_DIRECTION;
````


## -enum-fields
<dl>

### -field BmRequestHostToDevice

<dd>
<p>The data transfer direction is from the host system to the device.</p>
</dd>

### -field BmRequestDeviceToHost

<dd>
<p>The data transfer direction is from the device to the host system.</p>
</dd>
</dl>

## -remarks
<p>The <b>WDF_USB_BMREQUEST_DIRECTION</b> enumeration is used in the <a href="..\wdfusb\ns-wdfusb--wdf-usb-control-setup-packet.md">WDF_USB_CONTROL_SETUP_PACKET</a> structure.</p>

<p>For more information about the data transfer direction for a USB control transfer, see the USB specification.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfusb.h (include Wdfusb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfusb\ns-wdfusb--wdf-usb-control-setup-packet.md">WDF_USB_CONTROL_SETUP_PACKET</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_BMREQUEST_DIRECTION enumeration%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>