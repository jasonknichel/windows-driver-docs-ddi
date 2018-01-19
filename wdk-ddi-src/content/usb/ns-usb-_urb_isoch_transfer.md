---
UID : NS:usb._URB_ISOCH_TRANSFER
title : _URB_ISOCH_TRANSFER
author : windows-driver-content
description : The _URB_ISOCH_TRANSFER structure is used by USB client drivers to send data to or retrieve data from an isochronous transfer pipe.
old-location : buses\_urb_isoch_transfer.htm
old-project : usbref
ms.assetid : b021211a-3f72-47ff-9e69-bbf3807f4ec4
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _URB_ISOCH_TRANSFER,
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : usb.h
req.include-header : Usb.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : _URB_ISOCH_TRANSFER
req.alt-loc : usb.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : 
req.product : Windows 10 or later.
---

# _URB_ISOCH_TRANSFER structure
The <b>_URB_ISOCH_TRANSFER</b> structure is used by USB client drivers to send data to or retrieve data from an isochronous transfer pipe.

## Syntax
````
struct _URB_ISOCH_TRANSFER {
  struct URB_HEADER  Hdr;
  USBD_PIPE_HANDLE           PipeHandle;
  ULONG                      TransferFlags;
  ULONG                      TransferBufferLength;
  PVOID                      TransferBuffer;
  PMDL                       TransferBufferMDL;
  struct URB  *UrbLink;
  struct URB_HCD_AREA  hca;
  ULONG                      StartFrame;
  ULONG                      NumberOfPackets;
  ULONG                      ErrorCount;
  USBD_ISO_PACKET_DESCRIPTOR IsoPacket[1];
};
````

## Members

        
            `ErrorCount`

            Contains the number of packets that completed with an error condition on return from the host controller driver.
        
            `hca`

            Reserved. Do not use.
        
            `Hdr`

            A pointer to a <a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be URB_FUNCTION_ISOCH_TRANSFER, and <b>Hdr.Length</b> must be the size of this variable-length data structure.
        
            `IsoPacket`

            Contains a variable-length array of <a href="..\usb\ns-usb-_usbd_iso_packet_descriptor.md">USBD_ISO_PACKET_DESCRIPTOR</a> structures that describe the isochronous transfer packets to be transferred on the USB bus.  For more information about this member see the Remarks section.
        
            `NumberOfPackets`

            Specifies the number of packets that are described by the variable-length array member <b>IsoPacket</b>.
        
            `PipeHandle`

            Specifies an opaque handle to the isochronous pipe. The host controller driver returns this handle when the client driver selects the device configuration with a URB of type URB_FUNCTION_SELECT_CONFIGURATION or when the client driver changes the settings for an interface with a URB of type URB_FUNCTION_SELECT_INTERFACE.
        
            `StartFrame`

            Specifies the frame number that the transfer should begin on. This variable must be within a system-defined range of the current frame. The range is specified by the constant USBD_ISO_START_FRAME_RANGE.

If START_ISO_TRANSFER_ASAP is set in <b>TransferFlags</b>, this member contains the frame number that the transfer began on, when the request is returned by the host controller driver. Otherwise, this member must contain the frame number that this transfer begins on.
        
            `TransferBuffer`

            A pointer to a resident buffer for the transfer is <b>NULL</b> if an MDL is supplied in <b>TransferBufferMDL</b>. The contents of this buffer depend on the value of <b>TransferFlags</b>. If USBD_TRANSFER_DIRECTION_IN is specified, this buffer will contain data that is read from the device on return from the host controller driver. Otherwise, this buffer contains driver-supplied data for transfer to the device.
        
            `TransferBufferLength`

            Specifies the length, in bytes, of the buffer specified in <b>TransferBuffer</b> or described in <b>TransferBufferMDL</b>. The host controller driver returns the number of bytes that are sent to or read from the pipe in this member.
        
            `TransferBufferMDL`

            A pointer to an MDL that describes a resident buffer is <b>NULL</b> if a buffer is supplied in <b>TransferBuffer</b>. The contents of the buffer depend on the value of <b>TransferFlags</b>. If USBD_TRANSFER_DIRECTION_IN is specified, the described buffer will contain data that is read from the device on return from the host controller driver. Otherwise, the buffer contains driver-supplied data for transfer to the device. This MDL must be allocated from nonpaged pool.
        
            `TransferFlags`

            Specifies zero, one, or a combination of the following flags:



<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
        
            `UrbLink`

            Reserved. Do not use.

    ## Remarks
        The USB bus driver always returns a value of USBD_STATUS_SUCCESS in <b>Hdr.Status</b>, unless  every packet in the transfer generated an error or the request was not well-formed and could not be executed at all. The following table includes possible error codes returned in <b>Hdr.Status</b>.

USBD_STATUS_ISOCH_REQUEST_FAILED

Indicates that every packet of an isochronous request was completed with errors. 

USBD_STATUS_BAD_START_FRAME

Indicates that the requested start frame is not within USBD_ISO_START_FRAME_RANGE of the current USB frame. 

USBD_ISO_NOT_ACCESSED_LATE

Indicates that every packet was submitted too late for the packet to be sent, based on the requested start frame. 

USBD_STATUS_INVALID_PARAMETER

Indicates that one of the URB parameters was incorrect. 

Before the host controller sends an isochronous request to a USB device, it requires information about the device's endpoint to which it must send or receive data. This information is stored in endpoint descriptors (<a href="..\usbspec\ns-usbspec-_usb_endpoint_descriptor.md">USB_ENDPOINT_DESCRIPTOR</a>) that are retrieved from the selected configuration descriptor. 
After the bus driver gets the endpoint descriptor, it creates an isochronous transfer pipe to set up the data transfer. The pipe's attributes are stored in the <a href="..\usb\ns-usb-_usbd_pipe_information.md">USBD_PIPE_INFORMATION</a> structure. For isochronous transfers, the members are set as follows:<ul>
<li>The  <b>PipeType</b> member specifies the type of transfer and is set to UsbdPipeTypeIsochronous.</li>
<li>The <b>MaximumPacketSize</b> member specifies the amount of data, in bytes, that constitutes one packet. For isochronous transfers, the packet size is fixed and can be a value from 0-1024. The packet size either equals or is less than the <b>wMaxPacketSize</b> value of the endpoint descriptor.</li>
<li>The <b>Interval</b> member is derived from the <b>bInterval</b> value of the endpoint descriptor. This value is used to calculate the polling period that indicates the frequency at which data is sent on the bus. For full speed devices, the period is measured in units of 1 millisecond frames; for high speed devices, the period is measured in microframes.</li>
</ul>The host controller also determines the amount of data that can be transferred (within a frame or a microframe) depending on the type of device. This information is available in bits <b>12.. 11</b> of  <b>wMaxPacketSize</b> in the endpoint descriptor. 

For full-speed devices, only one packet can be transferred within a frame; bits <b>12.. 11</b> are reserved and set to zero. 

For high speed devices, data can be transferred in a single packet or might span multiple packets, within a microframe. 
If bits <b>12.. 11</b> are set to <i>n</i>,  you can transfer <code>(n+1)*MaximumPacketSize</code> bytes per microframe. Bits <b>12.. 11</b> set to zero indicate that only one packet can be transferred in a microframe. If bits <b>12.. 11</b> are set to 1,  the host controller can transfer two packets in a microframe.


The <b>IsoPacket</b> member of <b>_URB_ISOCH_TRANSFER</b> is an array of <a href="..\usb\ns-usb-_usbd_iso_packet_descriptor.md">USBD_ISO_PACKET_DESCRIPTOR</a> that describes the transfer buffer layout. Each element in the array correlates to data that is transferred in one microframe. If <b>IsoPacket</b> has <i>n</i> elements,  the host controller transfers use <i>n</i> frames (for full speed devices) or microframes (for high speed devices) to transfer data. The <b>IsoPacket[</b>i<b>].Offset</b> member is used to track the amount of data to send or receive. This is done  by setting a byte offset from the start of the entire transfer buffer for the request. 

For example, there are five microframes available to transfer 1024 byte-sized packets.

If bits <b>12.. 11</b> are set to zero (indicating a single packet per microframe transfer),  <b>IsoPacket</b> contains the following entries:

Microframe 1<code> IsoPacket.Element[0].Offset = 0</code> (start address) 

Microframe 2<code> IsoPacket.Element[1].Offset = 1024</code>

Microframe 3<code> IsoPacket.Element[2].Offset = 2048</code>

Microframe 4<code> IsoPacket.Element[3].Offset = 3072</code>

Microframe 5<code> IsoPacket.Element[4].Offset = 4096</code>

If bits <b>12.. 11</b> are set to 1 (indicating two packets per microframe),  <b>IsoPacket</b> contains the following entries:

Microframe 2<code> IsoPacket.Element[1].Offset = 2048</code>

Microframe 3<code> IsoPacket.Element[2].Offset = 4096</code>

Microframe 4<code> IsoPacket.Element[3].Offset = 6144</code>

Microframe 5<code> IsoPacket.Element[4].Offset = 8192</code>

<b>Note</b>  For multiple packets, the offset value indicates sizes for all the packets within the microframe.

The <b>IsoPacket[</b>i<b>].Length</b> member is updated by the host controller to indicate the actual number of bytes  that are received from the device for isochronous IN transfers. <b>IsoPacket[</b>i<b>].Length</b> is not used for isochronous OUT transfers.

Drivers can use the <a href="..\usbdlib\nf-usbdlib-get_iso_urb_size.md">GET_ISO_URB_SIZE</a> macro to determine the size that is needed to hold the entire URB. If the length is too small to fill the space set aside for this packet, the bus driver leaves a gap from the end of the retrieved data to the offset for the next packet. The bus driver will not adjust the offsets to avoid wasting buffer space. 

The <b>TransferBuffer</b> or <b>TransferBufferMDL</b> members must specify a virtually contiguous buffer.

Treat other members that are part of this structure but not described here as opaque. They are reserved for system use.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usb.h (include Usb.h) |

    ## See Also

        <dl>
<dt>
<a href="..\usbdlib\nf-usbdlib-usbd_isochurballocate.md">USBD_IsochUrbAllocate</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_usbd_iso_packet_descriptor.md">USBD_ISO_PACKET_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb.md">URB</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406225">How to Transfer Data to USB Isochronous Endpoints</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20_URB_ISOCH_TRANSFER structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>