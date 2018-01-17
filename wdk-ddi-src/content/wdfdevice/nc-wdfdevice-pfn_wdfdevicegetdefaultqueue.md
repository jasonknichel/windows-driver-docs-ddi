---
UID: NC:wdfdevice.PFN_WDFDEVICEGETDEFAULTQUEUE
title: PFN_WDFDEVICEGETDEFAULTQUEUE function
author: windows-driver-content
description: The WdfDeviceGetDefaultQueue method returns a handle to a device's default I/O queue.
old-location: wdf\wdfdevicegetdefaultqueue.htm
old-project: wdf
ms.assetid: 914c4ef8-2210-468c-8720-11f8adf9dce7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFDEVICEGETDEFAULTQUEUE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfDeviceGetDefaultQueue
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# PFN_WDFDEVICEGETDEFAULTQUEUE function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceGetDefaultQueue</b> method returns a handle to a device's default I/O queue.



## -syntax

````
WDFQUEUE WdfDeviceGetDefaultQueue(
  _In_ WDFDEVICE Device
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


## -returns
If the operation succeeds, the method returns a handle to a framework queue object. If the driver did not create a default I/O queue for the device, the method returns <b>NULL</b>.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
For more information about default I/O queues, see <a href="https://msdn.microsoft.com/03b09c94-6b72-4234-b21f-203f93b7a2e8">Creating I/O Queues</a>.

The following code example obtains a handle to a device's default I/O queue.</p>