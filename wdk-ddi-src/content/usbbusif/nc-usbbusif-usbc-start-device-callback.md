---
UID: NC.usbbusif.USBC_START_DEVICE_CALLBACK
title: USBC_START_DEVICE_CALLBACK
author: windows-driver-content
description: The USBC_START_DEVICE_CALLBACK routine allows a USB client driver to provide a custom definition of the interface collections on a device.
old-location: buses\usbc_start_device_callback.htm
old-project: usbref
ms.assetid: f9a9510a-b55c-4566-83ce-4ed7ccafb543
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: USBD_VERSION_INFORMATION, USBD_VERSION_INFORMATION, *PUSBD_VERSION_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: usbbusif.h
req.include-header: Usbbusif.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UsbcStartDeviceCallback
req.alt-loc: usbbusif.h
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

# USBC_START_DEVICE_CALLBACK callback



## -description
<p>The <b>USBC_START_DEVICE_CALLBACK</b> routine allows a USB client driver to provide a custom definition of the interface collections on a device.</p>


## -prototype

````
USBC_START_DEVICE_CALLBACK UsbcStartDeviceCallback;

NTSTATUS UsbcStartDeviceCallback(
  _In_  PUSB_DEVICE_DESCRIPTOR        DeviceDescriptor,
  _In_  PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor,
  _Out_ PUSBC_FUNCTION_DESCRIPTOR     *FunctionDescriptorBuffer,
  _Out_ PULONG                        FunctionDescriptorBufferLength,
  _In_  PDEVICE_OBJECT                FdoDeviceObject,
  _In_  PDEVICE_OBJECT                PdoDeviceObject
)
{ ... }
````


## -parameters
<dl>

### -param DeviceDescriptor [in]

<dd>
<p>The device descriptor of the device.</p>
</dd>

### -param ConfigurationDescriptor [in]

<dd>
<p>The configuration of the device.</p>
</dd>

### -param FunctionDescriptorBuffer [out]

<dd>
<p>Pointer to a buffer that contains an array of function descriptors (<a href="..\usbbusif\ns-usbbusif--usbc-function-descriptor.md">USBC_FUNCTION_DESCRIPTOR</a>).</p>
</dd>

### -param FunctionDescriptorBufferLength [out]

<dd>
<p>The length in bytes of the buffer that <i>FunctionDescriptorBuffer</i> points to.</p>
</dd>

### -param FdoDeviceObject [in]

<dd>
<p>The function device object for the device.</p>
</dd>

### -param PdoDeviceObject [in]

<dd>
<p>The physical device object for the device.</p>
</dd>
</dl>

## -returns
<p>If the operation succeeds, the vendor-supplied callback routine must return STATUS_SUCCESS.</p>

## -remarks
<p>For a general description of the callback routine mechanism, see <a href="buses.custom_enumeration_of_interface_collections_by_vendor_supplied_callbac">Customizing Enumeration of Interface Collections for Composite Devices</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Usbbusif.h (include Usbbusif.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\usbbusif\ns-usbbusif--usbc-device-configuration-interface-v1.md">USBC_DEVICE_CONFIGURATION_INTERFACE_V1</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBC_START_DEVICE_CALLBACK callback function%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>