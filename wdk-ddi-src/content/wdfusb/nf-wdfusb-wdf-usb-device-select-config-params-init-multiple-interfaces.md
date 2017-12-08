---
UID: NF.wdfusb.WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES
title: WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES
author: windows-driver-content
description: The WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES function initializes a WDF_USB_DEVICE_SELECT_CONFIG_PARAMS structure so that a driver can configure a device to use multiple interfaces.
old-location: wdf\wdf_usb_device_select_config_params_init_multiple_interfaces.htm
old-project: wdf
ms.assetid: e8f33c5d-50a4-43ad-a69e-d667500044a7
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES
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
req.alt-api: WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES
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

# WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b> function initializes a <a href="..\wdfusb\ns-wdfusb--wdf-usb-device-select-config-params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure so that a driver can configure a device to use multiple interfaces.</p>


## -syntax

````
VOID WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES(
  _Inout_  PWDF_USB_DEVICE_SELECT_CONFIG_PARAMS Params,
  _In_opt_ UCHAR                                NumberInterfaces,
  _In_opt_ PWDF_USB_INTERFACE_SETTING_PAIR      SettingPairs
);
````


## -parameters
<dl>

### -param Params [in, out]

<dd>
<p>A pointer to a driver-allocated <a href="..\wdfusb\ns-wdfusb--wdf-usb-device-select-config-params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure.</p>
</dd>

### -param NumberInterfaces [in, optional]

<dd>
<p>The number of elements in the <i>SettingPairs</i> array. If <i>SettingPairs</i> is not <b>NULL</b>, this parameter must be greater than zero. </p>
</dd>

### -param SettingPairs [in, optional]

<dd>
<p>An array of <a href="..\wdfusb\ns-wdfusb--wdf-usb-interface-setting-pair.md">WDF_USB_INTERFACE_SETTING_PAIR</a> structures. This parameter is optional and can be <b>NULL</b>.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>Your driver can use the <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b> function to select a configuration if the device interfaces are specified by handles to USB interface objects. </p>

<p>Your driver can use this function if your device has one or more USB interfaces.</p>

<p>The <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b> function zeros the <a href="..\wdfusb\ns-wdfusb--wdf-usb-device-select-config-params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure and sets the <b>Size</b> member to the size of the structure. </p>

<p>If either <i>numInterfaces</i> or <i>SettingPairs</i> is <b>NULL</b>, <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b> sets the <b>Type</b> member to <b>WdfUsbTargetDeviceSelectConfigTypeMultiInterface</b>. In this case, the framework determines the number of interfaces you have and enables alternate setting zero on each. Use this setting if you would like to default to alternate setting zero on all interfaces.</p>

<p>
If the <i>numInterfaces</i> parameter and the <i>SettingPairs</i> parameter are both not <b>NULL</b>, this function sets the <b>Type</b> member of the <a href="..\wdfusb\ns-wdfusb--wdf-usb-device-select-config-params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure to <b>WdfUsbTargetDeviceSelectConfigTypeInterfacesPairs</b>. In this case, you can specify an alternate setting on any of the interfaces.</p>

<p>To initialize a <a href="..\wdfusb\ns-wdfusb--wdf-usb-device-select-config-params.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS</a> structure, the driver must call one of the following functions:</p>

<p>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-device-select-config-params-init-deconfig.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_DECONFIG</a>
</p>

<p>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-device-select-config-params-init-single-interface.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a>
</p>

<p><b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b></p>

<p>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-device-select-config-params-init-interfaces-descriptors.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_INTERFACES_DESCRIPTORS</a>
</p>

<p>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-device-select-config-params-init-urb.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_URB</a>
</p>

<p>The following code example calls either <a href="..\wdfusb\nf-wdfusb-wdf-usb-device-select-config-params-init-single-interface.md">WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_SINGLE_INTERFACE</a> or <b>WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES</b>, based on the number of interfaces that the device configuration supports. Then, the example calls <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceselectconfig.md">WdfUsbTargetDeviceSelectConfig</a> to select a configuration.</p>

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
<dt>
<a href="..\wdfusb\ns-wdfusb--wdf-usb-interface-setting-pair.md">WDF_USB_INTERFACE_SETTING_PAIR</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_DEVICE_SELECT_CONFIG_PARAMS_INIT_MULTIPLE_INTERFACES function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>