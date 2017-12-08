---
UID: NS.ks.PKSMETHOD_SET
title: PKSMETHOD_SET
author: windows-driver-content
description: The KSMETHOD_SET structure describes the methods that comprise a kernel streaming method set.
old-location: stream\ksmethod_set.htm
old-project: stream
ms.assetid: e06bbf6f-f636-4fb1-8195-b74512d4cd13
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSMETHOD_SET, KSMETHOD_SET, *PKSMETHOD_SET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSMETHOD_SET
req.alt-loc: ks.h
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

# PKSMETHOD_SET structure



## -description
<p>The KSMETHOD_SET structure describes the methods that comprise a kernel streaming method set.</p>


## -syntax

````
typedef struct {
  const GUID              *Set;
  ULONG                   MethodsCount;
  const KSMETHOD_ITEM     *MethodItem;
  ULONG                   FastIoCount;
  const KSFASTMETHOD_ITEM *FastIoTable;
} KSMETHOD_SET, *PKSMETHOD_SET;
````


## -struct-fields
<dl>

### -field Set

<dd>
<p>Specifies a GUID the identifies the kernel streaming method set. For more information about method set GUIDs, see <b>Remarks</b>.</p>
</dd>

### -field MethodsCount

<dd>
<p>Specifies the number of methods in this method set.</p>
</dd>

### -field MethodItem

<dd>
<p>Points to an array of <a href="stream.ksmethod_item">KSMETHOD_ITEM</a> structures. Each structure describes one method of the method set.</p>
</dd>

### -field FastIoCount

<dd>
<p>Reserved for system use. Do not use.</p>
</dd>

### -field FastIoTable

<dd>
<p>Reserved for system use. Do not use.</p>
</dd>
</dl>

## -remarks
<p>Microsoft provides several system-defined kernel streaming method set GUIDs. Minidrivers specify one of these GUIDs in the <b>Set</b> member. Kernel streaming method sets typically begin with a <i>KSMETHODSETID</i> prefix. Method set GUIDs are defined in <i>ks.h</i>, <i>ksmedia.h</i>, <i>bdamedia.h</i>, and possibly other header files.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksmethod_item">KSMETHOD_ITEM</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSMETHOD_SET structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>