---
UID: NF.ucxusbdevice.UCX_USBDEVICE_EVENT_CALLBACKS_INIT
title: UCX_USBDEVICE_EVENT_CALLBACKS_INIT
author: windows-driver-content
description: Initializes a UCX_USBDEVICE_EVENT_CALLBACKS structure with the function pointers to client driver's callback functions.
old-location: buses\_ucx_usbdevice_event_callbacks_init.htm
old-project: usbref
ms.assetid: 594583B0-6CCB-469F-82AB-604825D85E2E
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: UCX_USBDEVICE_EVENT_CALLBACKS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: UCX_USBDEVICE_EVENT_CALLBACKS_INIT
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
req.irql: 
req.iface: 
req.product: Windows 10 or later.
---

# UCX_USBDEVICE_EVENT_CALLBACKS_INIT function



## -description
<p>Initializes a <a href="..\ucxusbdevice\ns-ucxusbdevice--ucx-usbdevice-event-callbacks.md">UCX_USBDEVICE_EVENT_CALLBACKS</a> structure with the function pointers to client driver's callback functions.</p>


## -syntax

````
__inline
void UCX_USBDEVICE_EVENT_CALLBACKS_INIT(
  _Out_ PUCX_USBDEVICE_EVENT_CALLBACKS          Callbacks,
  _In_  PEVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE  EvtUsbDeviceEndpointsConfigure,
  _In_  PEVT_UCX_USBDEVICE_ENABLE               EvtUsbDeviceEnable,
  _In_  PEVT_UCX_USBDEVICE_DISABLE              EvtUsbDeviceDisable,
  _In_  PEVT_UCX_USBDEVICE_RESET                EvtUsbDeviceReset,
  _In_  PEVT_UCX_USBDEVICE_ADDRESS              EvtUsbDeviceAddress,
  _In_  PEVT_UCX_USBDEVICE_UPDATE               EvtUsbDeviceUpdate,
  _In_  PEVT_UCX_USBDEVICE_HUB_INFO             EvtUsbDeviceHubInfo,
  _In_  PEVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD EvtUsbDeviceDefaultEndpointAdd,
  _In_  PEVT_UCX_USBDEVICE_ENDPOINT_ADD         EvtUsbDeviceEndpointAdd
);
````


## -parameters
<dl>

### -param Callbacks [out]

<dd>
<p>    A pointer to a <a href="..\ucxusbdevice\ns-ucxusbdevice--ucx-usbdevice-event-callbacks.md">UCX_USBDEVICE_EVENT_CALLBACKS</a> structure to initialize.</p>
</dd>

### -param EvtUsbDeviceEndpointsConfigure [in]

<dd>
<p>    A pointer to client driver's implementation of the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt-ucx-usbdevice-endpoints-configure.md">EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE</a> event callback function.</p>
</dd>

### -param EvtUsbDeviceEnable [in]

<dd>
<p>    A pointer to client driver's implementation of the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt-ucx-usbdevice-enable.md">EVT_UCX_USBDEVICE_ENABLE</a> event callback function.</p>
</dd>

### -param EvtUsbDeviceDisable [in]

<dd>
<p>    A pointer to client driver's implementation of the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt-ucx-usbdevice-disable.md">EVT_UCX_USBDEVICE_DISABLE</a> event callback function.</p>
</dd>

### -param EvtUsbDeviceReset [in]

<dd>
<p>    A pointer to client driver's implementation of the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt-ucx-usbdevice-reset.md">EVT_UCX_USBDEVICE_RESET</a> event callback function.</p>
</dd>

### -param EvtUsbDeviceAddress [in]

<dd>
<p>    A pointer to client driver's implementation of the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt-ucx-usbdevice-address.md">EVT_UCX_USBDEVICE_ADDRESS</a> event callback function.</p>
</dd>

### -param EvtUsbDeviceUpdate [in]

<dd>
<p>    A pointer to client driver's implementation of the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt-ucx-usbdevice-update.md">EVT_UCX_USBDEVICE_UPDATE</a> event callback function.</p>
</dd>

### -param EvtUsbDeviceHubInfo [in]

<dd>
<p>    A pointer to client driver's implementation of the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt-ucx-usbdevice-hub-info.md">EVT_UCX_USBDEVICE_HUB_INFO</a> event callback function.</p>
</dd>

### -param EvtUsbDeviceDefaultEndpointAdd [in]

<dd>
<p>    A pointer to client driver's implementation of the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt-ucx-usbdevice-default-endpoint-add.md">EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD</a> event callback function.</p>
</dd>

### -param EvtUsbDeviceEndpointAdd [in]

<dd>
<p>    A pointer to client driver's implementation of the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt-ucx-usbdevice-endpoint-add.md">EVT_UCX_USBDEVICE_ENDPOINT_ADD</a> event callback function.</p>
</dd>
</dl>

## -returns
<p>This function does not return a value.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum support</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\ucxusbdevice\ns-ucxusbdevice--ucx-usbdevice-event-callbacks.md">UCX_USBDEVICE_EVENT_CALLBACKS</a>
</dt>
<dt>
<a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdeviceinitseteventcallbacks.md">UcxUsbDeviceInitSetEventCallbacks</a>
</dt>
<dt>
<a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCX_USBDEVICE_EVENT_CALLBACKS_INIT function%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>