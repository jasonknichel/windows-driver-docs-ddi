---
UID: NS.ntdddisk._DRIVE_LAYOUT_INFORMATION_EX
title: DRIVE_LAYOUT_INFORMATION_EX
author: windows-driver-content
description: The DRIVE_LAYOUT_INFORMATION_EX structure is used to report information about the driver layout.
old-location: storage\drive_layout_information_ex.htm
old-project: storage
ms.assetid: e077f9a6-1d94-4d17-9166-b23756df6cc8
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: DRIVE_LAYOUT_INFORMATION_EX, DRIVE_LAYOUT_INFORMATION_EX, *PDRIVE_LAYOUT_INFORMATION_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DRIVE_LAYOUT_INFORMATION_EX
req.alt-loc: ntdddisk.h
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

# DRIVE_LAYOUT_INFORMATION_EX structure



## -description
<p>The DRIVE_LAYOUT_INFORMATION_EX structure is used to report information about the driver layout. </p>


## -syntax

````
typedef struct _DRIVE_LAYOUT_INFORMATION_EX {
  ULONG                    PartitionStyle;
  ULONG                    PartitionCount;
  union {
    DRIVE_LAYOUT_INFORMATION_MBR Mbr;
    DRIVE_LAYOUT_INFORMATION_GPT Gpt;
  };
  PARTITION_INFORMATION_EX PartitionEntry[1];
} DRIVE_LAYOUT_INFORMATION_EX, *PDRIVE_LAYOUT_INFORMATION_EX;
````


## -struct-fields
<dl>

### -field PartitionStyle

<dd>
<p>Takes a <a href="storage.partition_style">PARTITION_STYLE</a> enumerated value that specifies the type of partition table the disk contains.</p>
</dd>

### -field PartitionCount

<dd>
<p>Indicates the number of partitions detected on the disk.</p>
</dd>

### -field Mbr

<dd>
<p>Indicates the drive layout information for a disk with a Master Boot Record. This member is valid when <b>PartitionStyle</b> is PARTITION_STYLE_MBR.  See the definition of <a href="..\ntdddisk\ns-ntdddisk--drive-layout-information-mbr.md">DRIVE_LAYOUT_INFORMATION_MBR</a> for more information.</p>
</dd>

### -field Gpt

<dd>
<p>Indicates the drive layout information for a disk with a GUID Partition Table. This member is valid when <b>PartitionStyle</b> is PARTITION_STYLE_GPT. See definition of <a href="..\ntdddisk\ns-ntdddisk--drive-layout-information-gpt.md">DRIVE_LAYOUT_INFORMATION_GPT</a> for more information. </p>
</dd>

### -field PartitionEntry

<dd>
<p>Contains a variable-length array of <a href="..\ntdddisk\ns-ntdddisk--partition-information-ex.md">PARTITION_INFORMATION_EX</a> structures, one for each partition on the drive. </p>
</dd>
</dl>

## -remarks
<p>This structure is used for both reading and writing disk partition information. It is used with <a href="..\ntddk\nf-ntddk-ioreadpartitiontableex.md">IoReadPartitionTableEx</a> and <a href="..\ntddk\nf-ntddk-iowritepartitiontableex.md">IoWritePartitionTableEx</a> and replaces the obsolete structure DRIVE_LAYOUT_INFORMATION that was used with <b>IoReadPartitionTable</b> and <b>IoWritePartitionTable</b>. The principal difference is that the new structures and routines support both Master Boot Record (MBR) partitions and GUID Partition Table (GPT) partitions, whereas the older routines and structures are only used with MBR partitions. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntdddisk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-ioreadpartitiontableex.md">IoReadPartitionTableEx</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-iowritepartitiontableex.md">IoWritePartitionTableEx</a>
</dt>
<dt>
<a href="..\ntdddisk\ns-ntdddisk--drive-layout-information-mbr.md">DRIVE_LAYOUT_INFORMATION_MBR</a>
</dt>
<dt>
<a href="..\ntdddisk\ns-ntdddisk--drive-layout-information-gpt.md">DRIVE_LAYOUT_INFORMATION_GPT</a>
</dt>
<dt>
<a href="storage.partition_style">PARTITION_STYLE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DRIVE_LAYOUT_INFORMATION_EX structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>