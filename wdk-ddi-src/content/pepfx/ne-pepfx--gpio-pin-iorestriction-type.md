---
UID: NE.pepfx._GPIO_PIN_IORESTRICTION_TYPE
title: GPIO_PIN_IORESTRICTION_TYPE
author: windows-driver-content
description: The GPIO_PIN_IORESTRICTION_TYPE enumeration describes the functions that a GPIO pin is limited to performing.
old-location: kernel\gpio_pin_iorestriction_type.htm
old-project: kernel
ms.assetid: 381A59EE-BA1C-4810-842B-1D3E4D964486
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: VPCI_PNP_ID, VPCI_PNP_ID, *PVPCI_PNP_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GPIO_PIN_IORESTRICTION_TYPE
req.alt-loc: pepfx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks.
req.iface: 
---

# GPIO_PIN_IORESTRICTION_TYPE enumeration



## -description
<p>The <b>GPIO_PIN_IORESTRICTION_TYPE</b> enumeration describes the functions that a GPIO pin is limited to performing.</p>


## -syntax

````
typedef enum _GPIO_PIN_IORESTRICTION_TYPE { 
  IoRestrictionNone,
  IoRestrictionInputOnly,
  IoRestrictionOutputOnly,
  IoRestrictionNoneAndPreserve
} GPIO_PIN_IORESTRICTION_TYPE;
````


## -enum-fields
<dl>

### -field IoRestrictionNone

<dd>
<p>Indicates that the GPIO pin is not restricted to either input or output. When no IO restriction is described, it is assumed to be <b>IoRestrictionNone</b>. </p>
</dd>

### -field IoRestrictionInputOnly

<dd>
<p>Indicates that the GPIO pin is restricted to input. </p>
</dd>

### -field IoRestrictionOutputOnly

<dd>
<p>Indicates that the GPIO pin is restricted to output. </p>
</dd>

### -field IoRestrictionNoneAndPreserve

<dd>
<p>Indicates that the GPIO pin is not restricted to either input or output and that the mode should be preserved when the driver is unloaded. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 10.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Pepfx.h</dt>
</dl>
</td>
</tr>
</table>