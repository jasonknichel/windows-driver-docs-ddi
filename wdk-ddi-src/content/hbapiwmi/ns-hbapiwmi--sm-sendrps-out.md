---
UID: NS.hbapiwmi._SM_SendRPS_OUT
title: SM_SendRPS_OUT
author: windows-driver-content
description: The SM_SendRPS_OUT structure is used to receive output parameters from the SM_SendRPS method.
old-location: storage\sm_sendrps_out.htm
old-project: storage
ms.assetid: e202a292-df26-4829-be51-b8427d2dee20
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: SM_SendRPS_OUT, SM_SendRPS_OUT, *PSM_SendRPS_OUT
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
req.alt-api: SM_SendRPS_OUT
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

# SM_SendRPS_OUT structure



## -description
<p>The SM_SendRPS_OUT structure is used to receive output parameters from the SM_SendRPS method.</p>


## -syntax

````
typedef struct _SM_SendRPS_OUT {
  ULONG HBAStatus;
  ULONG TotalRespBufferSize;
  ULONG OutRespBufferSize;
  UCHAR RespBuffer[1];
} SM_SendRPS_OUT, *PSM_SendRPS_OUT;
````


## -struct-fields
<dl>

### -field HBAStatus

<dd>
<p>The status of the operation. For a list of allowed values and their descriptions, see <a href="storage.hba_status">HBA_STATUS</a>.</p>
</dd>

### -field TotalRespBufferSize

<dd>
<p>The size, in bytes, of the results common transport (CT) command.</p>
</dd>

### -field OutRespBufferSize

<dd>
<p>The size, in bytes, of the data that was actually retrieved.</p>
</dd>

### -field RespBuffer

<dd>
<p>The results of the common transport command.</p>
</dd>
</dl>

## -remarks
<p>The WMI tool suite generates a declaration of the SM_SendRPS_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.</p>

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