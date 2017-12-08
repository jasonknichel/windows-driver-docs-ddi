---
UID: NS.wdfusb._WDF_USB_INTERFACE_SELECT_SETTING_PARAMS
title: WDF_USB_INTERFACE_SELECT_SETTING_PARAMS
author: windows-driver-content
description: The WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure contains selection information for a USB interface.
old-location: wdf\wdf_usb_interface_select_setting_params.htm
old-project: wdf
ms.assetid: fad8a205-8427-48c5-b4b5-b125aa9fe85c
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_USB_INTERFACE_SELECT_SETTING_PARAMS, WDF_USB_INTERFACE_SELECT_SETTING_PARAMS, *PWDF_USB_INTERFACE_SELECT_SETTING_PARAMS
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
req.alt-api: WDF_USB_INTERFACE_SELECT_SETTING_PARAMS
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

# WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</b> structure contains selection information for a USB interface.</p>


## -syntax

````
typedef struct _WDF_USB_INTERFACE_SELECT_SETTING_PARAMS {
  ULONG                               Size;
  WdfUsbTargetDeviceSelectSettingType Type;
  union {
    struct {
      PUSB_INTERFACE_DESCRIPTOR InterfaceDescriptor;
    } Descriptor;
    struct {
      UCHAR SettingIndex;
    } Interface;
    struct {
      PURB Urb;
    } Urb;
  } Types;
} WDF_USB_INTERFACE_SELECT_SETTING_PARAMS, *PWDF_USB_INTERFACE_SELECT_SETTING_PARAMS;
````


## -struct-fields
<dl>

### -field Size

<dd>
<p>The size, in bytes, of this structure.</p>
</dd>

### -field Type

<dd>
<p>A <a href="..\wdfusb\ne-wdfusb--wdfusbtargetdeviceselectsettingtype.md">WdfUsbTargetDeviceSelectSettingType</a>-typed value that identifies a technique for specifying a device interface.</p>
</dd>

### -field Types

<dd>
<dl>

### -field Descriptor

<dd>
<dl>

### -field InterfaceDescriptor

<dd>
<p>If the <b>Type</b> member is <b>WdfUsbInterfaceSelectSettingTypeDescriptor</b>, this member contains a pointer to a <a href="..\usbspec\ns-usbspec--usb-interface-descriptor.md">USB_INTERFACE_DESCRIPTOR</a> structure that identifies a device interface.</p>
</dd>
</dl>
</dd>

### -field Interface

<dd>
<dl>

### -field SettingIndex

<dd>
<p>If the <b>Type</b> member is <b>WdfUsbInterfaceSelectSettingTypeSetting</b>, this member contains an index value that identifies an alternate setting for the interface. (The interface is identified by an interface object handle that the driver passes to <a href="..\wdfusb\nf-wdfusb-wdfusbinterfaceselectsetting.md">WdfUsbInterfaceSelectSetting</a>.) </p>
</dd>
</dl>
</dd>

### -field Urb

<dd>
<dl>

### -field Urb

<dd>
<p>If the <b>Type</b> member is <b>WdfUsbInterfaceSelectSettingTypeUrb</b>, this member contains a pointer to a <a href="..\usb\ns-usb--urb.md">URB</a> structure that describes a device interface. The URB structure's <b>Function</b> member must be URB_FUNCTION_SELECT_INTERFACE, and other members must be initialized as appropriate for the interface.</p>
</dd>
</dl>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p>The <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</b> structure is used as input to the <a href="..\wdfusb\nf-wdfusb-wdfusbinterfaceselectsetting.md">WdfUsbInterfaceSelectSetting</a> method. </p>

<p>To initialize a <b>WDF_USB_INTERFACE_SELECT_SETTING_PARAMS</b> structure, your driver must call one of the following functions:</p>

<p>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-interface-select-setting-params-init-descriptor.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_DESCRIPTOR</a>
</p>

<p>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-interface-select-setting-params-init-setting.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_SETTING</a>
</p>

<p>
<a href="..\wdfusb\nf-wdfusb-wdf-usb-interface-select-setting-params-init-urb.md">WDF_USB_INTERFACE_SELECT_SETTING_PARAMS_INIT_URB</a>
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
<a href="..\usb\ns-usb--urb.md">URB</a>
</dt>
<dt>
<a href="..\usbspec\ns-usbspec--usb-interface-descriptor.md">USB_INTERFACE_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbinterfaceselectsetting.md">WdfUsbInterfaceSelectSetting</a>
</dt>
<dt>
<a href="..\wdfusb\ne-wdfusb--wdfusbtargetdeviceselectsettingtype.md">WdfUsbTargetDeviceSelectSettingType</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_INTERFACE_SELECT_SETTING_PARAMS structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>