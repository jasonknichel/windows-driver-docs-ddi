---
UID: NS.NTDDK._FILE_VALID_DATA_LENGTH_INFORMATION
title: _FILE_VALID_DATA_LENGTH_INFORMATION
author: windows-driver-content
description: The FILE_VALID_DATA_LENGTH_INFORMATION structure is used as an argument to ZwSetInformationFile.
old-location: kernel\file_valid_data_length_information.htm
old-project: kernel
ms.assetid: 78badbac-9f77-4911-a42b-c0421be47f20
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _FILE_VALID_DATA_LENGTH_INFORMATION, *PFILE_VALID_DATA_LENGTH_INFORMATION, FILE_VALID_DATA_LENGTH_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows XP and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_VALID_DATA_LENGTH_INFORMATION
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
---

# _FILE_VALID_DATA_LENGTH_INFORMATION structure



## -description
The <b>FILE_VALID_DATA_LENGTH_INFORMATION</b> structure is used as an argument to <a href="kernel.zwsetinformationfile">ZwSetInformationFile</a>.


## -syntax

````
typedef struct _FILE_VALID_DATA_LENGTH_INFORMATION {
  LARGE_INTEGER ValidDataLength;
} FILE_VALID_DATA_LENGTH_INFORMATION, *PFILE_VALID_DATA_LENGTH_INFORMATION;
````


## -struct-fields

### -field ValidDataLength

Specifies the new valid data length for the file. This parameter must be a positive value that is greater than the current valid data length, but less than or equal to the current file size. 

## -remarks
The <b>FILE_VALID_DATA_LENGTH_INFORMATION</b> structure is used to set a new valid data length for a file on an NTFS volume. A file's <i>valid data length</i> is the length, in bytes, of the data that has been written to the file. This <i>valid data</i> extends from the beginning of the file to the last byte in the file that has not been zeroed or left uninitialized. 

Setting this information requires FILE_WRITE_DATA access to the file. In addition, nonadministrators and remote users must have <b>SeManageVolumePrivilege</b> (SE_MANAGE_VOLUME_PRIVILEGE) for the volume on which the file resides. 

File system filter drivers can find it useful to set a valid data length in the following scenarios: 

When writing raw clusters directly to disk through a hardware channel. This allows the filter driver to inform the file system that this range contains valid data that can be returned to the user. 

When creating large files where performance is an issue. This avoids the time it takes to fill the file with zeros when the file is created or extended. 

When remotely extending a file and writing to disk on a served-metadata cluster file system. 

The size of the <i>FileInformation</i> buffer passed to <b>ZwSetInformationFile</b> must be at least <b>sizeof</b>(<b>FILE_VALID_DATA_LENGTH_INFORMATION</b>). 

This structure must be aligned on a LONGLONG (8-byte) boundary. 

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available on Microsoft Windows XP and later versions of the Windows operating system.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.zwsetinformationfile">ZwSetInformationFile</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_VALID_DATA_LENGTH_INFORMATION structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>