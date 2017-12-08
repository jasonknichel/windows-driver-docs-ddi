---
UID: NS.ntddk._IMAGE_INFO_EX
title: IMAGE_INFO_EX
author: windows-driver-content
description: Extended version of the image information structure (see IMAGE_INFO).
old-location: kernel\image_info_ex.htm
old-project: kernel
ms.assetid: 97F3D9BE-9069-4A4A-B114-FC9331510512
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IMAGE_INFO_EX, IMAGE_INFO_EX, *PIMAGE_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IMAGE_INFO_EX
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

# IMAGE_INFO_EX structure



## -description
<p>Extended version of the image information structure (see <a href="..\ntddk\ns-ntddk--image-info.md">IMAGE_INFO</a>).</p>


## -syntax

````
typedef struct _IMAGE_INFO_EX {
  SIZE_T              Size;
  IMAGE_INFO          ImageInfo;
  struct _FILE_OBJECT  *FileObject;
} IMAGE_INFO_EX, *PIMAGE_INFO_EX;
````


## -struct-fields
<dl>

### -field Size

<dd>
<p>Specifies the size, in bytes, of the <b>IMAGE_INFO_EX</b> structure. </p>
</dd>

### -field ImageInfo

<dd>
<p>An <a href="..\ntddk\ns-ntddk--image-info.md">IMAGE_INFO</a> structure that specifies image information.</p>
</dd>

### -field FileObject

<dd>
<p>Contains a pointer to the file object of the backing file for the image. The driver can take a reference to this object or use it for other operations.</p>
</dd>
</dl>

## -remarks
<p>If the <b>ExtendedInfoPresent</b> flag is set, the <b>IMAGE_INFO</b> structure is part of a larger, extended version of the image information structure. In this case, the load-image notify routine can use the <b>CONTAINING_RECORD</b> macro in the Winnt.h header file to obtain the base address of the <b>IMAGE_INFO_EX</b> structure. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\ntddk\nc-ntddk-pload-image-notify-routine.md">PLOAD_IMAGE_NOTIFY_ROUTINE</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-pssetloadimagenotifyroutine.md">PsSetLoadImageNotifyRoutine</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--image-info.md">IMAGE_INFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IMAGE_INFO_EX structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>