---
UID: NF.dbgeng.IDebugDataSpaces.ReadIo
title: IDebugDataSpaces::ReadIo
author: windows-driver-content
description: The ReadIo method reads from the system and bus I/O memory.
old-location: debugger\readio.htm
old-project: debugger
ms.assetid: d690cf53-63a6-487c-a952-07035786d19c
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugDataSpaces, ReadIo, IDebugDataSpaces::ReadIo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugDataSpaces.ReadIo,IDebugDataSpaces2.ReadIo,IDebugDataSpaces3.ReadIo,IDebugDataSpaces4.ReadIo
req.alt-loc: dbgeng.h
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
req.iface: IDebugDataSpaces
---

# IDebugDataSpaces::ReadIo method



## -description
<p>The <b>ReadIo</b> method reads from the system and bus I/O memory.</p>


## -syntax

````
HRESULT ReadIo(
  [in]            ULONG   InterfaceType,
  [in]            ULONG   BusNumber,
  [in]            ULONG   AddressSpace,
  [in]            ULONG64 Offset,
  [out]           PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesRead
);
````


## -parameters
<dl>

### -param InterfaceType [in]

<dd>
<p>Specifies the interface type of the I/O bus.  This parameter may take values in the INTERFACE_TYPE enumeration defined in wdm.h.</p>
</dd>

### -param BusNumber [in]

<dd>
<p>Specifies the system-assigned number of the bus.  This is usually zero, unless the system has more than one bus of the same interface type.</p>
</dd>

### -param AddressSpace [in]

<dd>
<p>This parameter must be equal to one.</p>
</dd>

### -param Offset [in]

<dd>
<p>Specifies the I/O address within the address space.</p>
</dd>

### -param Buffer [out]

<dd>
<p>Receives the data read from the I/O bus.</p>
</dd>

### -param BufferSize [in]

<dd>
<p>Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be read.  At present, this must be 1, 2, or 4. </p>
</dd>

### -param BytesRead [out, optional]

<dd>
<p>Receives the number of bytes returned read from the I/O bus.  If <i>BytesRead</i> is <b>NULL</b>, this information is not returned.</p>
</dd>
</dl>

## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

<p>This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p>

## -remarks
<p>This method is only available in kernel-mode debugging.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>