---
UID: NS:usbspec._USB_DEVICE_QUALIFIER_DESCRIPTOR
title: "_USB_DEVICE_QUALIFIER_DESCRIPTOR"
author: windows-driver-content
description: The USB_DEVICE_QUALIFIER_DESCRIPTOR structure is used by USB client drivers to retrieve a USB-defined device qualifier descriptor.
old-location: buses\usb_device_qualifier_descriptor.htm
old-project: usbref
ms.assetid: f96e4305-ec07-4df8-8fdf-f840598dd938
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUSB_DEVICE_QUALIFIER_DESCRIPTOR, PUSB_DEVICE_QUALIFIER_DESCRIPTOR, PUSB_DEVICE_QUALIFIER_DESCRIPTOR structure pointer [Buses], USB_DEVICE_QUALIFIER_DESCRIPTOR, USB_DEVICE_QUALIFIER_DESCRIPTOR structure [Buses], _USB_DEVICE_QUALIFIER_DESCRIPTOR, buses.usb_device_qualifier_descriptor, usbspec/PUSB_DEVICE_QUALIFIER_DESCRIPTOR, usbspec/USB_DEVICE_QUALIFIER_DESCRIPTOR, usbstrct_af615085-b822-4342-b1dd-950a0ff61d99.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbspec.h
req.include-header: Usb200.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbspec.h
api_name:
-	USB_DEVICE_QUALIFIER_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: USB_DEVICE_QUALIFIER_DESCRIPTOR, *PUSB_DEVICE_QUALIFIER_DESCRIPTOR
req.product: Windows 10 or later.
---

# _USB_DEVICE_QUALIFIER_DESCRIPTOR structure


## -description


The <b>USB_DEVICE_QUALIFIER_DESCRIPTOR</b> structure is used by USB client drivers to retrieve a USB-defined device qualifier descriptor.


## -struct-fields




### -field bLength

Specifies the length, in bytes, of this descriptor.


### -field bDescriptorType

Specifies the descriptor type. Must be set to <b>USB_DEVICE_QUALIFIER_DESCRIPTOR_TYPE</b>.


### -field bcdUSB

Identifies the version of the USB specification that this descriptor structure complies with. This value is a binary-coded decimal number.


### -field bDeviceClass

Specifies the class code of the device as assigned by the USB specification group.


### -field bDeviceSubClass

Specifies the subclass code of the device as assigned by the USB specification group.


### -field bDeviceProtocol

Specifies the protocol code of the device as assigned by the USB specification group.


### -field bMaxPacketSize0

Specifies the maximum packet size, in bytes, for endpoint zero of the device. The value must be set to 8, 16, 32, or 64.


### -field bNumConfigurations

Specifies the total number of possible configurations for the device.


### -field bReserved

Reserved.


## -remarks



This structure is similar to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539280">USB_DEVICE_DESCRIPTOR</a>, but it contains only those members that can change when the device switches from full-speed operation to high-speed operation or vice versa. If the device is operating at full speed, querying for this descriptor will contain information about how the device would operate at high-speed. If, on the other hand, the device is operating at high-speed, this descriptor will contain information about how the device would operate at full-speed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538943">UsbBuildGetDescriptorRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540357">_URB_CONTROL_DESCRIPTOR_REQUEST</a>
 

 

