---
UID: NI:ntddstor.IOCTL_STORAGE_RESET_DEVICE
title: IOCTL_STORAGE_RESET_DEVICE
author: windows-driver-content
description: If possible, resets a non-SCSI storage device without affecting other devices on the bus.
old-location: storage\ioctl_storage_reset_device.htm
old-project: storage
ms.assetid: 85ada0f2-5690-4686-86e5-0e1cdc6b2054
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_STORAGE_RESET_DEVICE, IOCTL_STORAGE_RESET_DEVICE control code [Storage Devices], k307_489c36aa-d120-4d01-b5bd-29adca082064.xml, ntddstor/IOCTL_STORAGE_RESET_DEVICE, storage.ioctl_storage_reset_device
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddstor.h
api_name:
-	IOCTL_STORAGE_RESET_DEVICE
product:
- Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_RESET_DEVICE IOCTL


## -description



If possible, resets a non-SCSI storage device without affecting other devices on the bus. Device reset for SCSI devices is not supported. The caller requires only read access to issue a device reset and, to comply, the device must be capable of responding to I/O requests. If the device reset succeeds, pending I/O requests are canceled. 




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES, STATUS_NOT_IMPLEMENTED, or STATUS_INVALID_DEVICE_REQUEST.

