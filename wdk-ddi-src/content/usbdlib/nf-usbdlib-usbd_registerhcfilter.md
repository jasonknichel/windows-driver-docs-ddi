---
UID: NF:usbdlib.USBD_RegisterHcFilter
title: USBD_RegisterHcFilter function
author: windows-driver-content
description: The USBD_RegisterHcFilter routine has been deprecated in Windows XP and later operating systems.
old-location: buses\usbd_registerhcfilter.htm
old-project: usbref
ms.assetid: 2cc24024-75ec-45ba-867c-efc8e7da7587
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: USBD_RegisterHcFilter, USBD_RegisterHcFilter routine [Buses], buses.usbd_registerhcfilter, usbdlib/USBD_RegisterHcFilter, usbfunc_de494163-188c-4356-bd91-c6fa38693d55.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Universal
req.target-min-winverclnt: Deprecated.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Usbd.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Usbd.lib
-	Usbd.dll
api_name:
-	USBD_RegisterHcFilter
product:
- Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---

# USBD_RegisterHcFilter function


## -description


The <b>USBD_RegisterHcFilter</b> routine has been deprecated in Windows XP and later operating systems. Do not use. 

On  Windows XP and later operating systems, a filter driver that is installed between the root hub FDO and PDO sees all USB traffic for a USB device after it has been enumerated.  There is no supported mechanism for filtering descriptor requests that occur during the enumeration of a USB device, because those requests originate and remain in the port driver (usbport.sys) and not the hub driver.


## -parameters




### -param DeviceObject [in]

Pointer to the device object that is the current top of the stack as reported by <a href="https://msdn.microsoft.com/library/windows/hardware/ff548300">IoAttachDeviceToDeviceStack</a>.


### -param FilterDeviceObject [in]

Pointer to the filter device object created by the filter driver for its operations.


## -returns



None. 




## -remarks



USB bus filter drivers must call this routine after attaching their device object to the device object stack for the host controller driver.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548300">IoAttachDeviceToDeviceStack</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540134">USB device driver programming reference</a>
 

 

