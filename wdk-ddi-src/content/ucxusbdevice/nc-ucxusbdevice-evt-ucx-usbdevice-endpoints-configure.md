---
UID: NC.ucxusbdevice.EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE
title: EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE
author: windows-driver-content
description: The client driver's implementation that UCX calls to configure endpoints in the controller.
old-location: buses\evt_ucx_usbdevice_endpoints_configure.htm
old-project: usbref
ms.assetid: 2f374912-985d-47e0-9fda-b43242375cb5
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: STREAM_INFO, STREAM_INFO, *PSTREAM_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: PEVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE
req.alt-loc: ucxusbdevice.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE callback



## -description
<p>The client driver's implementation that UCX calls to configure endpoints in the controller.</p>


## -prototype

````
EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE EvtUcxUsbDeviceEndpointsConfigure;

VOID EvtUcxUsbDeviceEndpointsConfigure(
  _In_ UCXCONTROLLER UcxController,
  _In_ WDFREQUEST    Request
)
{ ... }

typedef EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE PEVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE;
````


## -parameters
<dl>

### -param UcxController [in]

<dd>
<p> A handle to the UCX controller that the client driver received in a previous call to  the <a href="buses._ucxcontrollercreate">UcxControllerCreate</a> method.</p>
</dd>

### -param Request [in]

<dd>
<p>Contains a structure of type <a href="..\ucxendpoint\ns-ucxendpoint--endpoints-configure.md">ENDPOINTS_CONFIGURE</a> structure.</p>
</dd>
</dl>

## -returns
<p>This callback function does not return a value.</p>

## -remarks
<p>The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a> method.</p>

<p>In the callback, the driver programs or deprograms the endpoints, as described in the <a href="..\ucxendpoint\ns-ucxendpoint--endpoints-configure.md">ENDPOINTS_CONFIGURE</a> structure.</p>

<p>This callback does not enable or disable the default endpoint. The default endpoint’s state is tied to the state of the device.   The driver implements enable and disable operations in the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt-ucx-usbdevice-disable.md">EVT_UCX_USBDEVICE_DISABLE</a> and <a href="..\ucxusbdevice\nc-ucxusbdevice-evt-ucx-usbdevice-enable.md">EVT_UCX_USBDEVICE_ENABLE</a> callback functions.</p>

<p>The client driver returns completion status in <i>Request</i>.  The driver can complete the WDFREQUEST asynchronously.</p>

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
<dt>Ucxusbdevice.h (include Ucxclass.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ucxendpoint\ns-ucxendpoint--endpoints-configure.md">ENDPOINTS_CONFIGURE</a>
</dt>
<dt>
<a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE callback function%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>