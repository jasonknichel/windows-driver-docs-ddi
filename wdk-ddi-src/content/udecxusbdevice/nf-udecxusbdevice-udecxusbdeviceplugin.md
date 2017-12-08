---
UID: NF.udecxusbdevice.UdecxUsbDevicePlugIn
title: UdecxUsbDevicePlugIn function
author: windows-driver-content
description: Notifies the USB device emulation class extension (UdeCx) that the USB device has been plugged in the specified port.
old-location: buses\udecxusbdeviceplugin.htm
old-project: usbref
ms.assetid: 6F1A1545-5B64-4481-B795-0B6433304C06
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: UdecxUsbDevicePlugIn
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.alt-api: UdecxUsbDevicePlugIn
req.alt-loc: Udecxstub.lib,Udecxstub.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# UdecxUsbDevicePlugIn function



## -description
Notifies the USB device emulation class extension (UdeCx) that the USB device has been plugged in the specified port.


## -syntax

````
FORCEINLINE NTSTATUS UdecxUsbDevicePlugIn(
  _In_ UDECXUSBDEVICE                    UdecxUsbDevice,
  _In_ PUDECX_USB_DEVICE_PLUG_IN_OPTIONS Options
);
````


## -parameters

### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="buses.udecxusbdevicecreate">UdecxUsbDeviceCreate</a>.

### -param Options [in]

A <a href="buses.udecx_usb_device_plug_in_options">UDECX_USB_DEVICE_PLUG_IN_OPTIONS</a>-type value that indicates the port to which the device is plugged. At most one of Usb20PortNumber, Usb30PortNumber can be non-zero. NULL disables plug-in options (use defaults).


## -returns
The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 

## -remarks
After the client driver calls this method, the class extension sends I/O requests and invokes callback functions on the endpoints and the device. 

## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.15
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>UdecxUsbDevice.h (include Udecx.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Udecxstub.lib</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="buses.usb_emulated_device__ude__architecture">Architecture: USB Device Emulation (UDE)</a>
</dt>
<dt>
<a href="buses.writing_a_ude_client_driver">Write a UDE client driver</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbDevicePlugIn function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>