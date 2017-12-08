---
UID: NF.dbgeng.IDebugSymbols.GetNumberModules
title: IDebugSymbols::GetNumberModules
author: windows-driver-content
description: The GetNumberModules method returns the number of modules in the current process's module list.
old-location: debugger\getnumbermodules.htm
old-project: debugger
ms.assetid: e74a4e51-0e3b-4d16-b39c-379dfb3905ad
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugSymbols, GetNumberModules, IDebugSymbols::GetNumberModules
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
req.alt-api: IDebugSymbols.GetNumberModules,IDebugSymbols2.GetNumberModules,IDebugSymbols3.GetNumberModules
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
req.iface: IDebugSymbols
---

# IDebugSymbols::GetNumberModules method



## -description
<p>The <b>GetNumberModules</b> method returns the number of <a href="debugger.modules#modules#modules">modules</a> in the current process's module list.</p>


## -syntax

````
HRESULT GetNumberModules(
  [out] PULONG Loaded,
  [out] PULONG Unloaded
);
````


## -parameters
<dl>

### -param Loaded [out]

<dd>
<p>Receives the number of loaded modules in the current process's module list.</p>
</dd>

### -param Unloaded [out]

<dd>
<p>Receives the number of unloaded modules in the current process's module list. This number will be zero if the version of Microsoft Windows running on the target computer does not track unloaded modules.</p>
</dd>
</dl>

## -returns
<p>This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>The list of loaded and unloaded modules is maintained by Windows.  The engine caches a copy of this list, but it may become out of date.  <a href="debugger.reload">Reload</a> can be used to synchronize the engine's copy of the list with the list maintained by Windows.</p>

<p>The unloaded modules are not tracked in all versions of Windows.  Unloaded modules are tracked for user-mode targets in Microsoft Windows Server 2003 and later; for kernel-mode targets, the unloaded modules are tracked in earlier Windows versions as well.  When they are tracked they are indexed after the loaded modules.  Unloaded modules can be used to analyze failures caused by an attempt to call unloaded code.</p>

<p>For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.</p>

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
<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="debugger.getmodulebyindex">GetModuleByIndex</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::GetNumberModules method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>