---
UID: NS.hbapiwmi._MSFC_LinkEvent
title: MSFC_LinkEvent
author: windows-driver-content
description: A WMI provider uses the MSFC_LinkEvent structure to report link events for the indicated adapter.
old-location: storage\msfc_linkevent.htm
old-project: storage
ms.assetid: 35fb3397-2e45-4d32-8cb1-1050199b2209
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: MSFC_LinkEvent, MSFC_LinkEvent, *PMSFC_LinkEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MSFC_LinkEvent
req.alt-loc: hbapiwmi.h
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

# MSFC_LinkEvent structure



## -description
<p>A WMI provider uses the MSFC_LinkEvent structure to report link events for the indicated adapter.</p>


## -syntax

````
typedef struct _MSFC_LinkEvent {
  ULONG EventType;
  UCHAR AdapterWWN[8];
  ULONG RLIRBufferSize;
  UCHAR RLIRBuffer[1];
} MSFC_LinkEvent, *PMSFC_LinkEvent;
````


## -struct-fields
<dl>

### -field EventType

<dd>
<p>Indicates the type of the event. The values that can be assigned to this member are defined by the <a href="storage.event_types_qualifiers">EVENT_TYPE_QUALIFIERS</a> WMI class qualifier.</p>
</dd>

### -field AdapterWWN

<dd>
<p>Contains a worldwide name that indicates the adapter for which the event occurred. </p>
</dd>

### -field RLIRBufferSize

<dd>
<p>Indicates the size of the buffer at <b>RLIRBuffer</b>. </p>
</dd>

### -field RLIRBuffer

<dd>
<p>Contains the data associated with a register link incident request (RLIR).</p>
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
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.event_types_qualifiers">EVENT_TYPE_QUALIFIERS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSFC_LinkEvent structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>