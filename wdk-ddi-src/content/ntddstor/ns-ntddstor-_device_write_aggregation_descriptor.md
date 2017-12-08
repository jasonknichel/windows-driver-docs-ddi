---
UID: NS.NTDDSTOR._DEVICE_WRITE_AGGREGATION_DESCRIPTOR
title: _DEVICE_WRITE_AGGREGATION_DESCRIPTOR
author: windows-driver-content
description: Reserved for system use.
old-location: storage\device_write_aggregation_descriptor.htm
old-project: storage
ms.assetid: 7AACFA1A-4B56-4B51-91B6-5FA30918E516
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _DEVICE_WRITE_AGGREGATION_DESCRIPTOR, *PDEVICE_WRITE_AGGREGATION_DESCRIPTOR, DEVICE_WRITE_AGGREGATION_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Windows 7
req.target-min-winversvr: Windows Server 2008 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEVICE_WRITE_AGGREGATION_DESCRIPTOR
req.alt-loc: ntddstor.h
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

# _DEVICE_WRITE_AGGREGATION_DESCRIPTOR structure



## -description
Reserved for system use.


## -syntax

````
typedef struct _DEVICE_WRITE_AGGREGATION_DESCRIPTOR {
  ULONG   Version;
  ULONG   Size;
  BOOLEAN BenefitsFromWriteAggregation;
} DEVICE_WRITE_AGGREGATION_DESCRIPTOR, *PDEVICE_WRITE_AGGREGATION_DESCRIPTOR;
````


## -struct-fields

### -field Version

Contains the size, in bytes, of this structure. The value of this member will change as members are added 
      to the structure.

### -field Size

Specifies the total size of the descriptor, in bytes.

### -field BenefitsFromWriteAggregation

<b>TRUE</b> if the device benefits from write aggregation.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 7
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2008 R2
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddstor.h (include Ntddstor.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DEVICE_WRITE_AGGREGATION_DESCRIPTOR structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>