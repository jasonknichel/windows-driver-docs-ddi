---
UID: NS.acpiioct._ACPI_EVAL_INPUT_BUFFER_V2
title: ACPI_EVAL_INPUT_BUFFER_V2
author: windows-driver-content
description: This topic describes the ACPI_EVAL_INPUT_BUFFER_V2 structure.
old-location: acpi\acpi_eval_input_buffer_v2.htm
old-project: acpi
ms.assetid: EDB4862E-FAD4-4AB2-BF0C-CF4C6342F0E4
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: ACPI_EVAL_INPUT_BUFFER_V2, ACPI_EVAL_INPUT_BUFFER_V2, *PACPI_EVAL_INPUT_BUFFER_V2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709 and later versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ACPI_EVAL_INPUT_BUFFER_V2
req.alt-loc: Acpiioct.h
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
---

# ACPI_EVAL_INPUT_BUFFER_V2 structure



## -description
<p>This topic describes the  <b>ACPI_EVAL_INPUT_BUFFER_V2</b> structure.</p>


## -syntax

````
typedef struct _ACPI_EVAL_INPUT_BUFFER_V2 {
  ULONG Signature;
  union {
    UCHAR MethodName[4];
    ULONG MethodNameAsUlong;
  } DUMMYUNIONNAME;
} ACPI_EVAL_INPUT_BUFFER_V2, *PACPI_EVAL_INPUT_BUFFER_V2;
````


## -struct-fields
<dl>

### -field Signature

<dd>
<p>Defines the <b>ULONG</b> member <b>Signature</b>.</p>
</dd>

### -field DUMMYUNIONNAME

<dd>
<p>Defines the method name member of <b>DUMMYUNIONNAME</b>.</p>
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
<p>Windows 10, version 1709 and later versions.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Acpiioct.h (include Acpiioct.h)</dt>
</dl>
</td>
</tr>
</table>