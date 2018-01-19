---
UID : NS:ntdddisk._DISK_PARTITION_INFO
title : _DISK_PARTITION_INFO
author : windows-driver-content
description : The DISK_PARTITION_INFO structure is used to report information about the disk's partition table.
old-location : storage\disk_partition_info.htm
old-project : storage
ms.assetid : 14df0604-39cd-4743-a051-894d63f4417c
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _DISK_PARTITION_INFO, DISK_PARTITION_INFO, *PDISK_PARTITION_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntdddisk.h
req.include-header : Ntdddisk.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DISK_PARTITION_INFO
req.alt-loc : ntdddisk.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : DISK_PARTITION_INFO, *PDISK_PARTITION_INFO
---

# _DISK_PARTITION_INFO structure
The <b>DISK_PARTITION_INFO</b> structure is used to report information about the disk's partition table.

## Syntax
````
typedef struct _DISK_PARTITION_INFO {
  ULONG           SizeOfPartitionInfo;
  PARTITION_STYLE PartitionStyle;
  union {
    struct {
      ULONG Signature;
      ULONG CheckSum;
    } Mbr;
    struct {
      GUID DiskId;
    } Gpt;
  };
} DISK_PARTITION_INFO, *PDISK_PARTITION_INFO;
````

## Members

        
            `PartitionStyle`

            Takes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563773">PARTITION_STYLE</a> enumerated value that specifies the type of partition table the disk contains.
        
            `SizeOfPartitionInfo`

            Size of this structure in bytes. Set to <b>sizeof</b>(DISK_PARTITION_INFO).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntdddisk.h (include Ntdddisk.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ntdddisk\ns-ntdddisk-_disk_geometry_ex.md">DISK_GEOMETRY_EX</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563773">PARTITION_STYLE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DISK_PARTITION_INFO structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>