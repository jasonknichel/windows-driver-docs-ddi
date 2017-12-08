---
UID: NS.hbapiwmi._SM_SendECHO_OUT
title: SM_SendECHO_OUT
author: windows-driver-content
description: The SM_SendECHO_OUT structure is used to receive output parameters from the SM_SendECHO method.
old-location: storage\sm_sendecho_out.htm
old-project: storage
ms.assetid: b3f948e0-4066-487c-aaa9-de29c0023f10
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: SM_SendECHO_OUT, SM_SendECHO_OUT, *PSM_SendECHO_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SM_SendECHO_OUT
req.alt-loc: hbapiwmi.h
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
req.iface: 
---

# SM_SendECHO_OUT structure



## -description
<p>The SM_SendECHO_OUT structure is used to receive output parameters from the SM_SendECHO method.</p>


## -syntax

````
typedef struct _SM_SendECHO_OUT {
  ULONG HBAStatus;
  ULONG OutRespBufferSize;
  UCHAR RespBuffer[1];
} SM_SendECHO_OUT, *PSM_SendECHO_OUT;
````


## -struct-fields
<dl>

### -field HBAStatus

<dd>
<p>The status of the operation. For a list of allowed values and their descriptions, see <a href="storage.hba_status">HBA_STATUS</a>.</p>
</dd>

### -field OutRespBufferSize

<dd>
<p>The output response size.</p>
</dd>

### -field RespBuffer

<dd>
<p>The result of the operation.</p>
</dd>
</dl>

## -remarks
<p>The WMI tool suite generates a declaration of the SM_SendECHO_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>