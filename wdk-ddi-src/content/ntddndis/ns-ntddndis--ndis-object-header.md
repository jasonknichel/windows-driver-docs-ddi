---
UID: NS.ntddndis._NDIS_OBJECT_HEADER
title: NDIS_OBJECT_HEADER
author: windows-driver-content
description: The NDIS_OBJECT_HEADER structure packages the object type, version, and size information that is required in many NDIS 6.0 structures.
old-location: netvista\ndis_object_header.htm
old-project: netvista
ms.assetid: 59d1a9b0-a4d0-4a24-aa2f-2167b0f53caa
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NDIS_OBJECT_HEADER, NDIS_OBJECT_HEADER, *PNDIS_OBJECT_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_OBJECT_HEADER
req.alt-loc: ntddndis.h
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

# NDIS_OBJECT_HEADER structure



## -description
<p>The NDIS_OBJECT_HEADER structure packages the object type, version, and size information that is
  required in many NDIS 6.0 structures.</p>


## -syntax

````
typedef struct _NDIS_OBJECT_HEADER {
  UCHAR  Type;
  UCHAR  Revision;
  USHORT Size;
} NDIS_OBJECT_HEADER, *PNDIS_OBJECT_HEADER;
````


## -struct-fields
<dl>

### -field Type

<dd>
<p>The type of NDIS object that a structure describes. Use this member to identify the type of
     structure in a memory dump.</p>
</dd>

### -field Revision

<dd>
<p>The revision number of the structure. Every NDIS structure that has an NDIS_OBJECT_HEADER member
     has a revision number that applies to the NDIS structure exclusively. This allows NDIS drivers to
     support multiple versions of the same structure. For example, a driver can check the 
     <b>Revision</b> member value at run time and use the appropriate version of the structure.</p>
</dd>

### -field Size

<dd>
<p>The total size, in bytes, of the NDIS object structure that includes the NDIS_OBJECT_HEADER
     member. This size includes the size of the NDIS_OBJECT_HEADER member and the other members of the
     structure.</p>
</dd>
</dl>

## -remarks
<p>The reference page for every structure, that has an NDIS_OBJECT_HEADER structure as a member, defines
    values for the 
    <b>Type</b>, 
    <b>Revision</b>, and 
    <b>Size</b> members for that structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>