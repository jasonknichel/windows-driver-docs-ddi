---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_ReasonId
title: IPrinterExtensionEventArgs::get_ReasonId method
author: windows-driver-content
description: Gets the reason why the printer extension was activated.
old-location: print\iprinterextensioneventargs_reasonid.htm
old-project: print
ms.assetid: 404E9893-97BA-48A7-87CE-0B4AF46692CE
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterExtensionEventArgs, IPrinterExtensionEventArgs interface [Print Devices], ReasonId property, IPrinterExtensionEventArgs.ReasonId, IPrinterExtensionEventArgs::get_ReasonId, ReasonId property [Print Devices], ReasonId property [Print Devices], IPrinterExtensionEventArgs interface, get_ReasonId, get_ReasonId,IPrinterExtensionEventArgs.get_ReasonId, print.iprinterextensioneventargs_reasonid, printerextension/IPrinterExtensionEventArgs::ReasonId, printerextension/IPrinterExtensionEventArgs::get_ReasonId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrinterExtensionEventArgs.ReasonId
-	IPrinterExtensionEventArgs.get_ReasonId
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionEventArgs::get_ReasonId method


## -description


Gets the reason why the printer extension was activated.

This property is read-only.


## -parameters


## -remarks




<ul>
<li>
In this mode, preferences for a print job or default print preferences is expected to be displayed.

Guid = {EC8F261F-267C-469F-B5D6-3933023C29CC}

<b>PRINTER_EXTENSION_REASON_PRINT_PREFERENCES</b> = { 0xec8f261f, 0x267c, 0x469f, 0xb5, 0xd6, 0x39, 0x33, 0x2, 0x3c, 0x29, 0xcc };


</li>
<li>
In this mode a status monitor for the print queue is expected to be displayed

Guid = {23BB1328-63DE-4293-915B-A6A23D929ACB}

<b>PRINTER_EXTENSION_REASON_DRIVER_EVENT</b> = { 0x23bb1328, 0x63de, 0x4293, 0x91, 0x5b, 0xa6, 0xa2, 0x3d, 0x92, 0x9a, 0xcb };

</li>
</ul>





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh973209">DetailedReasonId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh973207">IPrinterExtensionEventArgs</a>
 

 

