---
UID: NS.ntifs._FILE_ZERO_DATA_INFORMATION_EX
title: FILE_ZERO_DATA_INFORMATION_EX
author: windows-driver-content
description: Contains a range of a file to set to zeros.
old-location: ifsk\file_zero_data_information_ex.htm
old-project: ifsk
ms.assetid: 429C644C-C784-4C0E-96C3-EC82698F6624
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FILE_ZERO_DATA_INFORMATION_EX, FILE_ZERO_DATA_INFORMATION_EX, *PFILE_ZERO_DATA_INFORMATION_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_ZERO_DATA_INFORMATION_EX
req.alt-loc: ntifs.h
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

# FILE_ZERO_DATA_INFORMATION_EX structure



## -description
<p>Contains a range of a file to set to zeros. This structure is used by the 
<a href="ifsk.fsctl_set_zero_data">FSCTL_SET_ZERO_DATA</a> control code. It's similar to <a href="..\ntifs\ns-ntifs--file-zero-data-information.md">FILE_ZERO_DATA_INFORMATION</a>, but contains an additional <b>Flags</b> member. </p>


## -syntax

````
typedef struct _FILE_ZERO_DATA_INFORMATION_EX {
  LARGE_INTEGER FileOffset;
  LARGE_INTEGER BeyondFinalZero;
  ULONG         Flags;
} FILE_ZERO_DATA_INFORMATION_EX, *PFILE_ZERO_DATA_INFORMATION_EX;
````


## -struct-fields
<dl>

### -field FileOffset

<dd>
<p>The file offset of the start of the range to set to zeros, in bytes.</p>
</dd>

### -field BeyondFinalZero

<dd>
<p>The byte offset of the first byte beyond the last zeroed byte.</p>
</dd>

### -field Flags

<dd>
<p>The following flags are supported:</p>
<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td><b>FILE_ZERO_DATA_INFORMATION_FLAG_PRESERVE_CACHED_DATA</b></td>
<td>Indicates not to purge the contents of the cache corresponding to this range of the file. Only drivers can set this flag.</td>
</tr>
</table>
<p> </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltfscontrolfile.md">FltFsControlFile</a>
</dt>
<dt>
<a href="ifsk.fsctl_set_zero_data">FSCTL_SET_ZERO_DATA</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs--file-zero-data-information.md">FILE_ZERO_DATA_INFORMATION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_ZERO_DATA_INFORMATION_EX structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>