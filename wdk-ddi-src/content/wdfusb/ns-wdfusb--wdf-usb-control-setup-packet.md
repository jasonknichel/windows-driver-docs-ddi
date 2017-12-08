---
UID: NS.wdfusb._WDF_USB_CONTROL_SETUP_PACKET
title: WDF_USB_CONTROL_SETUP_PACKET
author: windows-driver-content
description: The WDF_USB_CONTROL_SETUP_PACKET structure describes a setup packet for a USB control transfer.
old-location: wdf\wdf_usb_control_setup_packet.htm
old-project: wdf
ms.assetid: f50ee559-3df7-4e15-b5a6-d6b85277c461
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_USB_CONTROL_SETUP_PACKET, WDF_USB_CONTROL_SETUP_PACKET, *PWDF_USB_CONTROL_SETUP_PACKET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_USB_CONTROL_SETUP_PACKET
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

# WDF_USB_CONTROL_SETUP_PACKET structure



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WDF_USB_CONTROL_SETUP_PACKET</b> structure describes a setup packet for a USB control transfer.</p>


## -syntax

````
typedef union _WDF_USB_CONTROL_SETUP_PACKET {
  struct {
    union {
      struct {
        BYTE Recipient  :2;
        BYTE Reserved  :3;
        BYTE Type  :2;
        BYTE Dir  :1;
      } Request;
      BYTE   Byte;
    } bm;
    BYTE   bRequest;
    union {
      struct {
        BYTE LowByte;
        BYTE HiByte;
      } Bytes;
      USHORT Value;
    } wValue;
    union {
      struct {
        BYTE LowByte;
        BYTE HiByte;
      } Bytes;
      USHORT Value;
    } wIndex;
    USHORT wLength;
  } Packet;
  struct {
    BYTE Bytes[8];
  } Generic;
} WDF_USB_CONTROL_SETUP_PACKET, *PWDF_USB_CONTROL_SETUP_PACKET;
````


## -struct-fields
<dl>

### -field Packet

<dd>
<dl>

### -field bm

<dd>
<dl>

### -field Request

<dd>
<dl>

### -field Recipient

<dd>
<p>A bit field that is specified by a <a href="..\wdfusb\ne-wdfusb--wdf-usb-bmrequest-recipient.md">WDF_USB_BMREQUEST_RECIPIENT</a>-typed value.</p>
</dd>

### -field Reserved

<dd>
<p>A reserved bit field. Do not use this member.</p>
</dd>

### -field Type

<dd>
<p>A bit field that is specified by a <a href="..\wdfusb\ne-wdfusb--wdf-usb-bmrequest-type.md">WDF_USB_BMREQUEST_TYPE</a>-typed value.</p>
</dd>

### -field Dir

<dd>
<p>A bit field that is specified by a <a href="..\wdfusb\ne-wdfusb--wdf-usb-bmrequest-direction.md">WDF_USB_BMREQUEST_DIRECTION</a>-typed value.</p>
</dd>
</dl>
</dd>

### -field Byte

<dd>
<p>A byte-sized bitmap that contains the <b>Request.Recipient</b>, <b>Request.Reserved</b>, <b>Request.Type</b>, and <b>Request.Dir</b> bit fields. Use this member as an alternative to specifying the individual bit fields.</p>
</dd>
</dl>
</dd>

### -field bRequest

<dd>
<p>A request type. Request type constants are defined in <i>Usb100.h</i>. For more information about request types, see the USB specification.</p>
</dd>

### -field wValue

<dd>
<dl>

### -field Bytes

<dd>
<dl>

### -field LowByte

<dd>
<p>The low byte of a 2-byte, request-specific value. For more information about specifying <b>wValue</b>, see the USB specification.</p>
</dd>

### -field HiByte

<dd>
<p>The high byte of a 2-byte, request-specific value. </p>
</dd>
</dl>
</dd>

### -field Value

<dd>
<p>A 2-byte value that contains the <b>Bytes.LowByte</b> and <b>Bytes.HiByte</b> values. Use this member as an alternative to specifying individual low-byte and high-byte values.</p>
</dd>
</dl>
</dd>

### -field wIndex

<dd>
<dl>

### -field Bytes

<dd>
<dl>

### -field LowByte

<dd>
<p>The low byte of a 2-byte, request-specific value. For more information about specifying <b>wValue</b>, see the USB specification.</p>
</dd>

### -field HiByte

<dd>
<p>The high byte of a 2-byte, request-specific value. </p>
</dd>
</dl>
</dd>

### -field Value

<dd>
<p>A 2-byte value that contains the <b>Bytes.LowByte</b> and <b>Bytes.HiByte</b> values. Use this member as an alternative to specifying individual low-byte and high-byte values.</p>
</dd>
</dl>
</dd>

### -field wLength

<dd>
<p>The number of bytes to transfer, if applicable. For more information about this value, see the USB specification. The framework sets this value.</p>
</dd>
</dl>
</dd>

### -field Generic

<dd>
<dl>

### -field Bytes

<dd>
<p>An 8-byte value that represents the entire setup packet. You can use this member as an alternative to specifying individual structure members.</p>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p>The <b>WDF_USB_CONTROL_SETUP_PACKET</b> structure is used as input to the <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicesendcontroltransfersynchronously.md">WdfUsbTargetDeviceSendControlTransferSynchronously</a> and <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforcontroltransfer.md">WdfUsbTargetDeviceFormatRequestForControlTransfer</a> methods.</p>

<p>To initialize a <b>WDF_USB_CONTROL_SETUP_PACKET</b> structure, the driver should call one of the following functions:</p>

<p>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-control-setup-packet-init.md">WDF_USB_CONTROL_SETUP_PACKET_INIT</a>
</p>

<p>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-control-setup-packet-init-class.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS</a>
</p>

<p>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-control-setup-packet-init-feature.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE</a>
</p>

<p>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-control-setup-packet-init-get-status.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</a>
</p>

<p>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-control-setup-packet-init-vendor.md">WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</a>
</p>

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
<a href="..\wdfusb\ne-wdfusb--wdf-usb-bmrequest-direction.md">WDF_USB_BMREQUEST_DIRECTION</a>
</dt>
<dt>
<a href="..\wdfusb\ne-wdfusb--wdf-usb-bmrequest-recipient.md">WDF_USB_BMREQUEST_RECIPIENT</a>
</dt>
<dt>
<a href="..\wdfusb\ne-wdfusb--wdf-usb-bmrequest-type.md">WDF_USB_BMREQUEST_TYPE</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforcontroltransfer.md">WdfUsbTargetDeviceFormatRequestForControlTransfer</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicesendcontroltransfersynchronously.md">WdfUsbTargetDeviceSendControlTransferSynchronously</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_CONTROL_SETUP_PACKET union%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>