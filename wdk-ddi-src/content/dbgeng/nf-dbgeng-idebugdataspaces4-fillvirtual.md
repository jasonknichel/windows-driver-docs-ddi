---
UID: NF.dbgeng.IDebugDataSpaces4.FillVirtual
title: IDebugDataSpaces4::FillVirtual
author: windows-driver-content
description: The FillVirtual method writes a pattern of bytes to the target's virtual memory. The pattern is written repeatedly until the specified memory range is filled.
old-location: debugger\fillvirtual.htm
old-project: debugger
ms.assetid: d55ccd38-00c7-491b-aadf-8b42b5e89600
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugDataSpaces4, FillVirtual, IDebugDataSpaces4::FillVirtual
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
req.alt-api: IDebugDataSpaces2.FillVirtual,IDebugDataSpaces3.FillVirtual,IDebugDataSpaces4.FillVirtual
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
req.iface: IDebugDataSpaces4
---

# IDebugDataSpaces4::FillVirtual method



## -description
<p>The <b>FillVirtual</b> method writes a pattern of bytes to the target's virtual memory.  The pattern is written repeatedly until the specified memory range is filled.</p>


## -syntax

````
HRESULT FillVirtual(
  [in]            ULONG64 Start,
  [in]            ULONG   Size,
  [in]            PVOID   Pattern,
  [in]            ULONG   PatternSize,
  [out, optional] PULONG  Filled
);
````


## -parameters
<dl>

### -param Start [in]

<dd>
<p>Specifies the location in the target's virtual address space at which to start writing the pattern.</p>
</dd>

### -param Size [in]

<dd>
<p>Specifies how many bytes to write to the target's memory.</p>
</dd>

### -param Pattern [in]

<dd>
<p>Specifies the memory location of the pattern.</p>
</dd>

### -param PatternSize [in]

<dd>
<p>Specifies the size in bytes of the pattern.</p>
</dd>

### -param Filled [out, optional]

<dd>
<p>Receives the number of bytes written.  If it is set to <b>NULL</b>, this information isn't returned.</p>
</dd>
</dl>

## -returns
<p>This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>This method writes the pattern to the target's memory as many times as will fit in <i>Size</i> bytes.</p>

<p>If the final copy of the pattern will not completely fit into the memory range, it will only be partially written.  This includes the case where the size of the pattern is larger than the value of <i>Size</i>, and the extra bytes in the pattern are ignored.</p>

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

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces2.md">IDebugDataSpaces2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>
</dt>
<dt>
<a href="debugger.writevirtual">WriteVirtual</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces2::FillVirtual method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>