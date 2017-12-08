---
UID: NS.ntddtape._TAPE_ERASE
title: TAPE_ERASE
author: windows-driver-content
description: The TAPE_ERASE structure is used in conjunction with the IOCTL_TAPE_ERASE request to erase the current tape partition.
old-location: storage\tape_erase.htm
old-project: storage
ms.assetid: dc17efe6-9183-4908-8ca5-69c6ae38db6d
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: TAPE_ERASE, TAPE_ERASE, *PTAPE_ERASE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddtape.h
req.include-header: Ntddtape.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TAPE_ERASE
req.alt-loc: ntddtape.h
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

# TAPE_ERASE structure



## -description
<p>The TAPE_ERASE structure is used in conjunction with the <a href="..\ntddtape\ni-ntddtape-ioctl-tape-erase.md">IOCTL_TAPE_ERASE</a> request to erase the current tape partition.</p>


## -syntax

````
typedef struct _TAPE_ERASE {
  ULONG   Type;
  BOOLEAN Immediate;
} TAPE_ERASE, *PTAPE_ERASE;
````


## -struct-fields
<dl>

### -field Type

<dd>
<p>Indicates the type of erasure to perform. When this member is set to TAPE_ERASE_LONG, the tape partition is overwritten with a filler pattern. When it is set to TAPE_ERASE_SHORT, an end-of-recorded-data mark is written to the current position. </p>
</dd>

### -field Immediate

<dd>
<p>Indicates that the target device should return status immediately, when set to <b>TRUE</b>. When this member is set to <b>FALSE</b>, the device should return status after the operation is complete. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddtape.h (include Ntddtape.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddtape\ni-ntddtape-ioctl-tape-erase.md">IOCTL_TAPE_ERASE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TAPE_ERASE structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>