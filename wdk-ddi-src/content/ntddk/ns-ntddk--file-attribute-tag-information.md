---
UID: NS.ntddk._FILE_ATTRIBUTE_TAG_INFORMATION
title: FILE_ATTRIBUTE_TAG_INFORMATION
author: windows-driver-content
description: The FILE_ATTRIBUTE_TAG_INFORMATION structure is used as an argument to ZwQueryInformationFile.
old-location: kernel\file_attribute_tag_information.htm
old-project: kernel
ms.assetid: e330bd79-cd44-412e-b9aa-ca5b791750d4
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: FILE_ATTRIBUTE_TAG_INFORMATION, FILE_ATTRIBUTE_TAG_INFORMATION, *PFILE_ATTRIBUTE_TAG_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_ATTRIBUTE_TAG_INFORMATION
req.alt-loc: Ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# FILE_ATTRIBUTE_TAG_INFORMATION structure



## -description
<p>The <b>FILE_ATTRIBUTE_TAG_INFORMATION</b> structure is used as an argument to <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>. </p>


## -syntax

````
typedef struct _FILE_ATTRIBUTE_TAG_INFORMATION {
  ULONG FileAttributes;
  ULONG ReparseTag;
} FILE_ATTRIBUTE_TAG_INFORMATION, *PFILE_ATTRIBUTE_TAG_INFORMATION;
````


## -struct-fields
<dl>

### -field FileAttributes

<dd>
<p>Specifies one or more FILE_ATTRIBUTE_<i>XXX</i> flags. For descriptions of these flags, see the documentation of the <b>GetFileAttributes</b> function in the Microsoft Windows SDK.</p>
</dd>

### -field ReparseTag

<dd>
<p>Specifies the reparse point tag. If the <b>FileAttributes</b> member includes the FILE_ATTRIBUTE_REPARSE_POINT attribute flag, this member specifies the reparse tag. Otherwise, this member is unused.</p>
</dd>
</dl>

## -remarks
<p>FILE_READ_ATTRIBUTES access to the file is required to query this information.</p>

<p>For more information about reparse points and reparse point tags, see the Windows SDK.</p>

<p>This structure must be aligned on a LONG (4-byte) boundary.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_ATTRIBUTE_TAG_INFORMATION structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>