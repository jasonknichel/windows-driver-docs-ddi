---
UID : NE:usbfnbase._USBFN_DEVICE_STATE
title : _USBFN_DEVICE_STATE
author : windows-driver-content
description : Defines the Universal Serial Bus (USB) device states for the device/controller. These states correspond to the USB device states as defined in section 9.1 of the USB 2.0 Specification.
old-location : buses\usbfn_device_state.htm
old-project : usbref
ms.assetid : B367D0F7-5026-4C88-B88A-69068F76B675
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _USBFN_DEVICE_STATE, USBFN_DEVICE_STATE, *PUSBFN_DEVICE_STATE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : usbfnbase.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : USBFN_DEVICE_STATE
req.alt-loc : usbfnbase.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : USBFN_DEVICE_STATE, *PUSBFN_DEVICE_STATE
req.product : Windows 10 or later.
---

# _USBFN_DEVICE_STATE Enumeration
Defines the Universal Serial Bus (USB) device states for the device/controller.  These states correspond to the USB device states as defined in section 9.1 of the USB 2.0 Specification.

## Syntax
````
typedef enum _USBFN_DEVICE_STATE { 
  UsbfnDeviceStateMinimum       = 0x0,
  UsbfnDeviceStateAttached,
  UsbfnDeviceStateDefault,
  UsbfnDeviceStateDetached,
  UsbfnDeviceStateAddressed,
  UsbfnDeviceStateConfigured,
  UsbfnDeviceStateSuspended,
  UsbfnDeviceStateStateMaximum
} USBFN_DEVICE_STATE;
````

## Constants

<table>

<tr>
<td>UsbfnDeviceStateAddressed</td>
<td>Device has been assigned a non-default USB address by the host.</td>
</tr>

<tr>
<td>UsbfnDeviceStateAttached</td>
<td>Device is attached to an upstream port.</td>
</tr>

<tr>
<td>UsbfnDeviceStateConfigured</td>
<td>Device has been configured by the host.</td>
</tr>

<tr>
<td>UsbfnDeviceStateDefault</td>
<td>Device is attached and connected to an upstream port but has not been reset.</td>
</tr>

<tr>
<td>UsbfnDeviceStateDetached</td>
<td>Device is not attached to an upstream port.</td>
</tr>

<tr>
<td>UsbfnDeviceStateMinimum</td>
<td>The minimum value of the enumeration.</td>
</tr>

<tr>
<td>UsbfnDeviceStateStateMaximum</td>
<td>The maximum value of the enumeration.</td>
</tr>

<tr>
<td>UsbfnDeviceStateSuspended</td>
<td>Device has been suspended.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usbfnbase.h |