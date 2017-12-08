---
UID: NS.KS.PKSDATARANGE~R1
title: PKSDATARANGE
author: windows-driver-content
description: The KSDATARANGE structure is a variable-length structure that describes a range of data formats.
old-location: stream\ksdatarange.htm
old-project: stream
ms.assetid: 76d8adf2-935d-4f78-aff2-c061414fe094
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSDATARANGE, *PKSDATARANGE, *PKSDATAFORMAT, KSDATAFORMAT, KSDATARANGE
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
req.alt-api: KSDATAFORMAT
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
---

# PKSDATARANGE structure



## -description
The KSDATARANGE structure is a variable-length structure that describes a range of data formats.


## -syntax

````
typedef union {
  struct {
    ULONG FormatSize;
    ULONG Flags;
    ULONG SampleSize;
    ULONG Reserved;
    GUID  MajorFormat;
    GUID  SubFormat;
    GUID  Specifier;
  };
  LONGLONG Alignment;
} KSDATAFORMAT, *PKSDATAFORMAT, KSDATARANGE, *PKSDATARANGE;
````


## -struct-fields

### -field FormatSize

Specifies the size, in bytes, of this structure. This must be at least <b>sizeof</b>(KSDATARANGE), but can be larger for specific settings of <b>MajorFormat</b>, <b>SubFormat</b>, and <b>Specifier</b>. See the descriptions for these members for more information. 

### -field Flags

Set Flags to KSDATARANGE_ATTRIBUTES (0x2) to indicate that the following KSDATARANGE is to be interpreted as an attribute list that uses the <a href="stream.ksattribute_list">KSATTRIBUTE_LIST</a> structure.

### -field SampleSize

This member is ignored.

### -field Reserved

Reserved. Drivers must set this member to zero.

### -field MajorFormat

Specifies either the specific major format of a data format that this data range matches, or KSDATAFORMAT_TYPE_WILDCARD if this data range matches all major formats. When <b>MajorFormat</b> has this value, both <b>SubFormat</b> and <b>Specifier</b> must also take on their wild card values. For more information about this member, see <b>Remarks</b>.

### -field SubFormat

Specifies either the specific subformat of a data format that this data range matches, or KSDATAFORMAT_SUBTYPE_WILDCARD if this data range matches all subformats. (In this instance, the specifier is not required to be its wild card value, unless <b>MajorFormat</b> is KSDATAFORMAT_TYPE_WILDCARD.) For more information about this member, see <b>Remarks</b>.

### -field Specifier

Specifies either the specifier of the data format that this data range matches, or KSDATAFORMAT_SPECIFIER_WILDCARD if this data range matches all specifier values. For more information about this member, see <b>Remarks</b>.

### -field Alignment

This member specifies the memory alignment in bytes for this buffer.

## -remarks
Drivers use data ranges to describe the ranges of data formats they support.

For a list of <b>MajorFormat</b>, <b>SubFormat</b>, and <b>Specifier</b> GUIDs, see <a href="https://msdn.microsoft.com/dc2af282-4976-42d8-b07b-13b2a6dfb7d5">Stream Categories</a> and its subtopics.

## -requirements
<table>
<tr>
<th width="30%">
Header
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
<a href="https://msdn.microsoft.com/dc2af282-4976-42d8-b07b-13b2a6dfb7d5">Stream Categories</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSDATARANGE union%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>