---
UID: NF.wdfusb.WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG
title: WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG
author: windows-driver-content
description: The WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG function initializes a WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure so that a driver can deconfigure a USB device.
old-location: wdf\wdf_usb_device_select_config_params_init_deconfig.htm
old-project: wdf
ms.assetid: cc7ee273-e445-4cdb-b96d-b63db6e433de
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG
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
req.alt-api: WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG
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
req.irql: 
req.iface: 
req.product: Windows 10 or later.
---

# WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</b> function initializes a <a href="..\wdfusb\ns-wdfusb--wdf-usb-device-select-config-params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure so that a driver can deconfigure a USB device. </p>


## -syntax

````
VOID WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG(
  _Out_ PWDF_USB_DEVICE_SELECT_CONFIG_PARAMS Params
);
````


## -parameters
<dl>

### -param Params [out]

<dd>
<p>A pointer to a driver-allocated <a href="..\wdfusb\ns-wdfusb--wdf-usb-device-select-config-params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</b> function zeros the <a href="..\wdfusb\ns-wdfusb--wdf-usb-device-select-config-params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure and sets the <b>Size</b> member to the size of the structure. It also sets the <b>Type</b> member to <b>WdfUsbTargetDeviceSelectConfigTypeDeconfig</b>.</p>

<p>To initialize a <a href="..\wdfusb\ns-wdfusb--wdf-usb-device-select-config-params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure, the driver must call one of the following functions:</p>

<p><b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</b></p>

<p>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-device-select-config-params-init-single-interface.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a>
</p>

<p>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-device-select-config-params-init-multiple-interfaces.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</a>
</p>

<p>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-device-select-config-params-init-interfaces-descriptors.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_INTERFACES_DESCRIPTORS</a>
</p>

<p>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-device-select-config-params-init-urb.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</a>
</p>

<p>The following code example initializes a <a href="..\wdfusb\ns-wdfusb--wdf-usb-device-select-config-params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure and then calls <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a> to deconfigure a device.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
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
<dt>Wdfusb.h (include Wdfusb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfusb\ns-wdfusb--wdf-usb-device-select-config-params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-device-select-config-params-init-deconfig.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-device-select-config-params-init-interfaces-descriptors.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_INTERFACES_DESCRIPTORS</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-device-select-config-params-init-multiple-interfaces.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-device-select-config-params-init-single-interface.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-device-select-config-params-init-urb.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>