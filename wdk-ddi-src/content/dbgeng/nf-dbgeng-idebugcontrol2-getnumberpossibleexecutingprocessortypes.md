---
UID: NF.dbgeng.IDebugControl2.GetNumberPossibleExecutingProcessorTypes
title: IDebugControl2::GetNumberPossibleExecutingProcessorTypes
author: windows-driver-content
description: The GetNumberPossibleExecutingProcessorTypes method returns the number of processor types that are supported by the computer running the current target.
old-location: debugger\getnumberpossibleexecutingprocessortypes.htm
old-project: debugger
ms.assetid: 9e4ca8a6-f33f-4403-a52f-f242ce40aac8
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugControl2, GetNumberPossibleExecutingProcessorTypes, IDebugControl2::GetNumberPossibleExecutingProcessorTypes
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
req.alt-api: IDebugControl.GetNumberPossibleExecutingProcessorTypes,IDebugControl2.GetNumberPossibleExecutingProcessorTypes,IDebugControl3.GetNumberPossibleExecutingProcessorTypes
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
req.iface: IDebugControl2
---

# IDebugControl2::GetNumberPossibleExecutingProcessorTypes method



## -description
<p>The <b>GetNumberPossibleExecutingProcessorTypes</b> method returns the number of processor types that are supported by the computer running the current target.</p>


## -syntax

````
HRESULT GetNumberPossibleExecutingProcessorTypes(
  [out] PULONG Number
);
````


## -parameters
<dl>

### -param Number [out]

<dd>
<p>Receives the number of processor types.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.</p>

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
<a href="..\dbgeng\nn-dbgeng-idebugcontrol.md">IDebugControl</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>
</dt>
<dt>
<a href="debugger.getpossibleexecutingprocessortypes">GetPossibleExecutingProcessorTypes</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl::GetNumberPossibleExecutingProcessorTypes method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>