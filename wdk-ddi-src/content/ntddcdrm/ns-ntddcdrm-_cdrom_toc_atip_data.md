---
UID: NS.NTDDCDRM._CDROM_TOC_ATIP_DATA
title: _CDROM_TOC_ATIP_DATA
author: windows-driver-content
description: Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_ATIP return their output data in this header structure followed by a series of descriptors of type CDROM_TOC_ATIP_DATA_BLOCK.
old-location: storage\cdrom_toc_atip_data.htm
old-project: storage
ms.assetid: 4caf59d4-262a-49e3-8b66-9cf29ed5cee5
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _CDROM_TOC_ATIP_DATA, *PCDROM_TOC_ATIP_DATA, CDROM_TOC_ATIP_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CDROM_TOC_ATIP_DATA
req.alt-loc: ntddcdrm.h
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
---

# _CDROM_TOC_ATIP_DATA structure



## -description
Device control IRPs with a control code of <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md">IOCTL_CDROM_READ_TOC_EX</a> and a format of CDROM_READ_TOC_EX_FORMAT_ATIP return their output data in this header structure followed by a series of descriptors of type <a href="storage.cdrom_toc_atip_data_block">CDROM_TOC_ATIP_DATA_BLOCK</a>.


## -syntax

````
typedef struct _CDROM_TOC_ATIP_DATA {
  UCHAR                     Length[2];
  UCHAR                     Reserved1;
  UCHAR                     Reserved2;
  CDROM_TOC_ATIP_DATA_BLOCK Descriptors[];
} CDROM_TOC_ATIP_DATA, *PCDROM_TOC_ATIP_DATA;
````


## -struct-fields

### -field Length

Indicates the number of bytes to be transferred in response to the command. This length value does not include the length of the <b>Length </b>member itself. 

### -field Reserved1

Reserved. 

### -field Reserved2

Reserved. 

### -field Descriptors

Contains zero or more ATIP data block descriptors of type <a href="storage.cdrom_toc_atip_data_block">CDROM_TOC_ATIP_DATA_BLOCK</a>. 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddcdrm.h (include Ntddcdrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md">IOCTL_CDROM_READ_TOC_EX</a>
</dt>
<dt>
<a href="storage.cdrom_read_toc_ex">CDROM_READ_TOC_EX</a>
</dt>
<dt>
<a href="storage.cdrom_toc_atip_data_block">CDROM_TOC_ATIP_DATA_BLOCK</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_TOC_ATIP_DATA structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>