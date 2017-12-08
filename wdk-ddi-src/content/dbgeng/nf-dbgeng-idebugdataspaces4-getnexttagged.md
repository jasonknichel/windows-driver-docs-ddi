---
UID: NF.dbgeng.IDebugDataSpaces4.GetNextTagged
title: IDebugDataSpaces4::GetNextTagged
author: windows-driver-content
description: The GetNextTagged method returns the GUID for the next block of tagged data in the enumeration.
old-location: debugger\getnexttagged.htm
old-project: debugger
ms.assetid: 529ef33a-adad-4242-96a8-01cdd273cc35
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugDataSpaces4, GetNextTagged, IDebugDataSpaces4::GetNextTagged
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
req.alt-api: IDebugDataSpaces3.GetNextTagged,IDebugDataSpaces4.GetNextTagged
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

# IDebugDataSpaces4::GetNextTagged method



## -description
<p>The <b>GetNextTagged</b> method returns the GUID for the next block of tagged data in the enumeration.</p>


## -syntax

````
HRESULT GetNextTagged(
  [in]  ULONG64 Handle,
  [out] LPGUID  Tag,
  [out] PULONG  Size
);
````


## -parameters
<dl>

### -param Handle [in]

<dd>
<p>Specifies the handle identifying the enumeration.  This is the handle returned by <a href="debugger.startenumtagged">StartEnumTagged</a>.</p>
</dd>

### -param Tag [out]

<dd>
<p>Receives the GUID identifying the tagged data.  The data may be retrieved by passing this GUID to <a href="debugger.readtagged">ReadTagged</a>.</p>
</dd>

### -param Size [out]

<dd>
<p>Receives the size of the data identified by the GUID <i>Tag</i>.</p>
</dd>
</dl>

## -returns
<p>This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p><dl>
<dt><b>S_FALSE</b></dt>
</dl><p>There are no more blocks of tagged data available in this enumeration.</p>

<p> </p>

## -remarks


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
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>
</dt>
<dt>
<a href="debugger.startenumtagged">StartEnumTagged</a>
</dt>
<dt>
<a href="debugger.readtagged">ReadTagged</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces3::GetNextTagged method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>