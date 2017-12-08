---
UID: NF.rxprocs.RxMapSystemBuffer
title: RxMapSystemBuffer function
author: windows-driver-content
description: RxMapSystemBuffer returns the system buffer address from the IRP.
old-location: ifsk\rxmapsystembuffer.htm
old-project: ifsk
ms.assetid: dc549e51-2f25-45b5-925f-3481294e0b35
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RxMapSystemBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxprocs.h
req.include-header: Rxcontx.h, Rxprocs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxMapSystemBuffer
req.alt-loc: rxprocs.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# RxMapSystemBuffer function



## -description
<b>RxMapSystemBuffer</b> returns the system buffer address from the IRP. 


## -syntax

````
PVOID RxMapSystemBuffer(
  _In_ PRX_CONTEXT RxContext,
  _In_ PIRP        Irp
);
````


## -parameters

### -param RxContext [in]

A pointer to the RX_CONTEXT structure for this request.

### -param Irp [in]

A pointer to the IRP for this request.

## -returns
<b>RxMapSystemBuffer </b>returns a mapped address pointer. 

## -remarks
The <b>RxMapSystemBuffer</b> routine checks that <b>Irp-&gt;MdlAddress</b> is not <b>NULL</b> and returns the <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> when this is the case. 

On retail builds, <b>RxMapSystemBuffer</b> will call <b>MmGetSystemAddressForMdlSafe</b> to return the MDL from the IRP if <b>Irp-&gt;MdlAddress</b> is <b>NULL</b>. On checked builds, <b>RxMapSystemBuffer</b> causes the system to ASSERT if <b>Irp-&gt;MdlAddress</b> is <b>NULL</b>. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Rxprocs.h (include Rxcontx.h or Rxprocs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= APC_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>
</dt>
<dt>
<a href="ifsk.rxlowiocompletion">RxLowIoCompletion</a>
</dt>
<dt>
<a href="ifsk.rxlowiogetbufferaddress">RxLowIoGetBufferAddress</a>
</dt>
<dt>
<a href="ifsk.rxnewmapuserbuffer">RxNewMapUserBuffer</a>
</dt>
<dt>
<a href="ifsk.rx_context">RX_CONTEXT</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxMapSystemBuffer function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>