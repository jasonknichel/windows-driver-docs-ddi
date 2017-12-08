---
UID: NE.ucxroothub._CONTROLLER_TYPE
title: CONTROLLER_TYPE
author: windows-driver-content
description: This enumeration specifies if the USB host controller is an eXtensible Host Controller Interface (xHCI) controller.
old-location: buses\_controller_type.htm
old-project: usbref
ms.assetid: E7DFBFFA-C65B-4757-8DB8-202760D6D3C6
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS, UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS, *PUCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucxroothub.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CONTROLLER_TYPE
req.alt-loc: ucxroothub.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# CONTROLLER_TYPE enumeration



## -description
<p>This enumeration specifies if the USB host controller is an eXtensible Host Controller Interface (xHCI) controller.</p>


## -syntax

````
typedef enum _CONTROLLER_TYPE { 
  ControllerTypeXhci,
  ControllerTypeSoftXhci
} CONTROLLER_TYPE;
````


## -enum-fields
<dl>

### -field ControllerTypeXhci

<dd>
<p>Indicates the USB host controller is an xHCI controller.</p>
</dd>

### -field ControllerTypeSoftXhci

<dd>
<p>Indicates the USB host controller is software an xHCI controller.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ucxroothub.h (include Ucxclass.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ucxroothub\ns-ucxroothub--roothub-info.md">ROOTHUB_INFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20CONTROLLER_TYPE enumeration%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>