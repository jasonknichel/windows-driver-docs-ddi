---
UID: NF.dbgeng.IDebugSystemObjects4.GetCurrentSystemServerNameWide
title: IDebugSystemObjects4::GetCurrentSystemServerNameWide
author: windows-driver-content
description: Gets the server name for the current process.
old-location: debugger\idebugsystemobjects4_getcurrentsystemservernamewide.htm
old-project: debugger
ms.assetid: 44BAB9BF-76E6-42C2-B8DD-EB1A960C429C
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugSystemObjects4, GetCurrentSystemServerNameWide, IDebugSystemObjects4::GetCurrentSystemServerNameWide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugSystemObjects4.GetCurrentSystemServerNameWide
req.alt-loc: Dbgeng.h
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
req.iface: IDebugSystemObjects4
---

# IDebugSystemObjects4::GetCurrentSystemServerNameWide method



## -description
<p>Gets the server name for the current process.</p>


## -syntax

````
HRESULT GetCurrentSystemServerNameWide(
  [out]           _writes_opt_(BufferSize) PWSTR Buffer,
  [in]            ULONG                          BufferSize,
  [out, optional] PULONG                         NameSize
);
````


## -parameters
<dl>

### -param Buffer [out]

<dd>
<p>A pointer to an output buffer as a Unicode character string. </p>
</dd>

### -param BufferSize [in]

<dd>
<p>The buffer size. </p>
</dd>

### -param NameSize [out, optional]

<dd>
<p>A pointer to the name size. </p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks


## -requirements
<table>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects4.md">IDebugSystemObjects4</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSystemObjects4::GetCurrentSystemServerNameWide method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>