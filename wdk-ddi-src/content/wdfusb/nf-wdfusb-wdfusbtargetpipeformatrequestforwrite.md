---
UID: NF.wdfusb.WdfUsbTargetPipeFormatRequestForWrite
title: WdfUsbTargetPipeFormatRequestForWrite function
author: windows-driver-content
description: The WdfUsbTargetPipeFormatRequestForWrite method builds a write request for a USB output pipe, but it does not send the request.
old-location: wdf\wdfusbtargetpipeformatrequestforwrite.htm
old-project: wdf
ms.assetid: cf880701-d1e9-4bda-8d6c-35f35b707e9b
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfUsbTargetPipeFormatRequestForWrite
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfUsbTargetPipeFormatRequestForWrite
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, RequestFormattedValid, RequestSendAndForgetNoFormatting, RequestSendAndForgetNoFormatting2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfUsbTargetPipeFormatRequestForWrite function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WdfUsbTargetPipeFormatRequestForWrite</b> method builds a write request for a USB output pipe, but it does not send the request.


## -syntax

````
NTSTATUS WdfUsbTargetPipeFormatRequestForWrite(
  _In_     WDFUSBPIPE        Pipe,
  _In_     WDFREQUEST        Request,
  _In_opt_ WDFMEMORY         WriteMemory,
  _In_opt_ PWDFMEMORY_OFFSET WriteOffset
);
````


## -parameters

### -param Pipe [in]

A handle to a framework pipe object that was obtained by calling <a href="wdf.wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>. 

### -param Request [in]

A handle to a framework request object. For more information, see the following Remarks section.

### -param WriteMemory [in, optional]

A handle to a framework memory object. This object represents a buffer that contains data that will be sent to the pipe. For more information about this buffer, see the following Remarks section.

### -param WriteOffset [in, optional]

A pointer to a caller-allocated <a href="wdf.wdfmemory_offset">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. The framework uses these values to determine the beginning address and length, within the write buffer, for the data transfer. If this pointer is <b>NULL</b>, the data transfer begins at the beginning of the buffer, and the transfer size is the buffer size.

## -returns
<b>WdfUsbTargetPipeFormatRequestForWrite</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was detected.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Insufficient memory was available.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>An invalid memory descriptor was specified, the pipe's type was not valid, the transfer direction was invalid, or the specified I/O request was already queued to an I/O target.
<dl>
<dt><b>STATUS_INTEGER_OVERFLOW</b></dt>
</dl>The offset that the <i>Offset</i> parameter specified was invalid.
<dl>
<dt><b>STATUS_REQUEST_NOT_ACCEPTED</b></dt>
</dl>The I/O request packet (<a href="kernel.irp">IRP</a>) that the <i>Request</i> parameter represents does not provide enough <a href="kernel.io_stack_location">IO_STACK_LOCATION</a> structures to allow the driver to forward the request.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks
Use <b>WdfUsbTargetPipeFormatRequestForWrite</b>, followed by <a href="wdf.wdfrequestsend">WdfRequestSend</a>, to send write requests either synchronously or asynchronously. Alternatively, use the <a href="wdf.wdfusbtargetpipewritesynchronously">WdfUsbTargetPipeWriteSynchronously</a> method to send write requests synchronously. 

The specified pipe must be an output pipe, and the pipe's <a href="wdf.wdf_usb_pipe_type">type</a> must be <b>WdfUsbPipeTypeBulk</b> or <b>WdfUsbPipeTypeInterrupt</b>.

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request. In either case, the framework requires a request object and some buffer space.

To forward an I/O request that your driver received in an I/O queue:

Specify the received request's handle for the <b>WdfUsbTargetPipeFormatRequestForWrite</b> method's <i>Request</i> parameter.

Use the received request's input buffer for the <b>WdfUsbTargetPipeFormatRequestForWrite</b> method's <i>WriteMemory</i> parameter.

The driver must call <a href="wdf.wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a> to obtain a handle to a framework memory object that represents the request's input buffer and use that handle as the value for <i>WriteMemory</i>.

For more information about forwarding an I/O request, see <a href="wdf.forwarding_i_o_requests">Forwarding I/O Requests</a>.

Drivers often divide received I/O requests into smaller requests that they send to an I/O target, so your driver might create new requests.

To create a new I/O request:

Create a new request object and supply its handle for the <b>WdfUsbTargetPipeFormatRequestForWrite</b> method's <i>Request</i> parameter.

Call <a href="wdf.wdfrequestcreate">WdfRequestCreate</a> to preallocate one or more request objects. You can reuse these request objects by calling <a href="wdf.wdfrequestreuse">WdfRequestReuse</a>. Your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function can preallocate request objects for a device.

Provide buffer space, and supply the buffer's handle for the <b>WdfUsbTargetPipeFormatRequestForWrite</b> method's <i>WriteMemory</i> parameter.

Your driver must specify this buffer space as a WDFMEMORY handle to framework-managed memory. Your driver can do either of the following:

Note that if your driver calls <a href="wdf.wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a> and passes the memory handle to <b>WdfUsbTargetPipeFormatRequestForWrite</b>, the driver must not complete the received I/O request until after the driver deletes, reuses, or reformats the new, driver-created request object. (<b>WdfUsbTargetPipeFormatRequestForWrite</b> increments the memory object's reference count. Deleting, reusing, or reformatting a request object decrements the memory object's reference count.)

After calling <b>WdfUsbTargetPipeFormatRequestForWrite</b> to format an I/O request, the driver must call <a href="wdf.wdfrequestsend">WdfRequestSend</a> to send the request (either synchronously or asynchronously) to an I/O target.

Multiple calls to <b>WdfUsbTargetPipeFormatRequestForWrite</b> that use the same request do not cause additional resource allocations. Therefore, to reduce the chance that <a href="wdf.wdfrequestcreate">WdfRequestCreate</a> will return STATUS_INSUFFICIENT_RESOURCES, your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function can call <b>WdfRequestCreate</b> to preallocate one or more request objects for a device. The driver can subsequently reuse (call <a href="wdf.wdfrequestreuse">WdfRequestReuse</a>), reformat (call <b>WdfUsbTargetPipeFormatRequestForWrite</b>), and resend (call <a href="wdf.wdfrequestsend">WdfRequestSend</a>) each request object without risking a STATUS_INSUFFICIENT_RESOURCES return value from a later call to <b>WdfRequestCreate</b>. All subsequent calls to <b>WdfUsbTargetPipeFormatRequestForWrite</b> for the reused request object will return STATUS_SUCCESS, if parameter values do not change. (If the driver does not call the same request-formatting method each time, additional resources might be allocated.)

For information about obtaining status information after an I/O request completes, see <a href="wdf.completing_i_o_requests#obtaining_completion_information#obtaining_completion_information">Obtaining Completion Information</a>.

For more information about the <b>WdfUsbTargetPipeFormatRequestForWrite</b> method and USB I/O targets, see <a href="wdf.usb_i_o_targets">USB I/O Targets</a>.

The following code example is from the <a href="wdf.sample_kmdf_drivers">kmdf_fx2</a> sample driver. This example is an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_write.md">EvtIoWrite</a> callback function that forwards a write request to a USB pipe. The example calls <a href="wdf.wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a> to obtain the request's input buffer, and then it formats the write request so that the request can be sent to a USB pipe. Next, the example registers a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function. Finally, it sends the request to the USB pipe.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.0
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
<dt>Wdfusb.h (include Wdfusb.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;=DISPATCH_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>, <a href="devtest.kmdf_requestformattedvalid">RequestFormattedValid</a>, <a href="devtest.kmdf_requestsendandforgetnoformatting">RequestSendAndForgetNoFormatting</a>, <a href="devtest.kmdf_requestsendandforgetnoformatting2">RequestSendAndForgetNoFormatting2</a>, <a href="devtest.kmdf_usbkmdfirql">UsbKmdfIrql</a>, <a href="devtest.kmdf_usbkmdfirql2">UsbKmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfusbtargetpipeformatrequestforread">WdfUsbTargetPipeFormatRequestForRead</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetPipeFormatRequestForWrite method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>