---
UID: NF:wdfresource.WdfIoResourceListGetCount
title: WdfIoResourceListGetCount function
author: windows-driver-content
description: The WdfIoResourceListGetCount method returns the number of resource descriptors that are contained in a resource requirements list's logical configuration.
old-location: wdf\wdfioresourcelistgetcount.htm
old-project: wdf
ms.assetid: d8f3d743-acc1-4884-b0ec-a6cea5d8e437
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFResourceObjectRef_19542c4c-aed9-412b-83c7-38209836a679.xml, WdfIoResourceListGetCount, WdfIoResourceListGetCount method, kmdf.wdfioresourcelistgetcount, wdf.wdfioresourcelistgetcount, wdfresource/WdfIoResourceListGetCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfresource.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfIoResourceListGetCount
product:
- Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# WdfIoResourceListGetCount function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceListGetCount</b> method returns the number of resource descriptors that are contained in a resource requirements list's <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a>.


## -parameters




### -param ResourceList [in]

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.


## -returns



<b>WdfIoResourceListGetCount</b> returns the number of resource descriptors that are contained in the logical configuration that <i>ResourceList</i> specifies.

A system bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about resource requirements lists and logical configurations, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

For a code example that uses <b>WdfIoResourceListGetCount</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548553">WdfIoResourceRequirementsListGetIoResList</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548553">WdfIoResourceRequirementsListGetIoResList</a>
 

 

