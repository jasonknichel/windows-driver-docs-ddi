---
UID: NF.dbgeng.IDebugClient3.WriteDumpFile
title: IDebugClient3::WriteDumpFile
author: windows-driver-content
description: The WriteDumpFile method creates a user-mode or kernel-modecrash dump file.
old-location: debugger\writedumpfile.htm
old-project: debugger
ms.assetid: 5f410561-b848-471e-8230-f12aa512a897
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugClient3, WriteDumpFile, IDebugClient3::WriteDumpFile
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
req.alt-api: IDebugClient.WriteDumpFile,IDebugClient2.WriteDumpFile,IDebugClient3.WriteDumpFile,IDebugClient4.WriteDumpFile,IDebugClient5.WriteDumpFile
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
req.iface: IDebugClient3
---

# IDebugClient3::WriteDumpFile method



## -description
<p>The <b>WriteDumpFile</b> method creates a user-mode or kernel-modecrash dump file.</p>


## -syntax

````
HRESULT WriteDumpFile(
  [in] PCSTR DumpFile,
  [in] ULONG Qualifier
);
````


## -parameters
<dl>

### -param DumpFile [in]

<dd>
<p>Specifies the name of the dump file to create.  <i>DumpFile</i> must include the file name extension.  <i>DumpFile</i> can include a relative or absolute path; relative paths are relative to the directory in which the debugger was started.</p>
</dd>

### -param Qualifier [in]

<dd>
<p>Specifies the type of dump file to create.  For possible values, see Remarks.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>The DEBUG_DUMP_<i>XXX</i> constants are used by the methods <b>WriteDumpFile</b>, <a href="debugger.writedumpfile2">WriteDumpFile2</a>, and <a href="debugger.writedumpfilewide">WriteDumpFileWide</a> to specify the type of crash dump file to create.</p>

<p>The possible values include the following.</p>

<p><b>DEBUG_DUMP_SMALL</b></p>

<p>Creates a Small Memory Dump (kernel-mode) or Minidump (user-mode).</p>

<p><b>DEBUG_DUMP_DEFAULT</b></p>

<p>Creates a Full User-Mode Dump (user-mode) or Kernel Summary Dump (kernel-mode).</p>

<p><b>DEBUG_DUMP_FULL</b></p>

<p>
         Creates a Complete Memory Dump (kernel-mode only).</p>

<p>To specify the formatting of the file and--for user-mode minidumps--the information to include in the file, use <a href="debugger.writedumpfile2">WriteDumpFile2</a> or <a href="debugger.writedumpfilewide">WriteDumpFileWide</a>.</p>

<p>For more information about crash dump files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542783">Dump-File Targets</a>.</p>

<p>Moreover, the following aliases are available for kernel-mode debugging.</p>

<p>DEBUG_DUMP_SMALL</p>

<p>DEBUG_DUMP_DEFAULT</p>

<p>DEBUG_DUMP_FULL</p>

<p>Additionally, the following aliases are available for user-mode debugging.</p>

<p>For a description of kernel-mode dump files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560246">Varieties of Kernel-Mode Dump Files</a>.  For a description of user-mode dump files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560251">Varieties of User-Mode Dump Files</a>.</p>

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
<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>
</dt>
<dt>
<a href="debugger.writedumpfile2">WriteDumpFile2</a>
</dt>
<dt>
<a href="debugger.writedumpfilewide">WriteDumpFileWide</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562428">.dump (Create Dump File)</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::WriteDumpFile method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>