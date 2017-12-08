---
UID: NE.ntddk._WHEA_ERROR_SOURCE_TYPE
title: WHEA_ERROR_SOURCE_TYPE
author: windows-driver-content
description: The WHEA_ERROR_SOURCE_TYPE enumeration defines the different types of error sources that can report hardware errors.
old-location: whea\whea_error_source_type.htm
old-project: whea
ms.assetid: d2615320-6c8a-4813-afb5-c5b510e5fde9
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: FILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WHEA_ERROR_SOURCE_TYPE
req.alt-loc: ntddk.h
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

# WHEA_ERROR_SOURCE_TYPE enumeration



## -description
<p>The WHEA_ERROR_SOURCE_TYPE enumeration defines the different types of error sources that can report hardware errors.</p>


## -syntax

````
typedef enum _WHEA_ERROR_SOURCE_TYPE { 
  WheaErrSrcTypeMCE         = 0x00,
  WheaErrSrcTypeCMC         = 0x01,
  WheaErrSrcTypeCPE         = 0x02,
  WheaErrSrcTypeNMI         = 0x03,
  WheaErrSrcTypePCIe        = 0x04,
  WheaErrSrcTypeGeneric     = 0x05,
  WheaErrSrcTypeINIT        = 0x06,
  WheaErrSrcTypeBOOT        = 0x07,
  WheaErrSrcTypeSCIGeneric  = 0x08,
  WheaErrSrcTypeIPFMCA      = 0x09,
  WheaErrSrcTypeIPFCMC      = 0x0a,
  WheaErrSrcTypeIPFCPE      = 0x0b,
  WheaErrSrcTypeMax
} WHEA_ERROR_SOURCE_TYPE, *PWHEA_ERROR_SOURCE_TYPE;
````


## -enum-fields
<dl>

### -field WheaErrSrcTypeMCE

<dd>
<p>A machine check exception (MCE).</p>
</dd>

### -field WheaErrSrcTypeCMC

<dd>
<p>A corrected machine check (CMC).</p>
</dd>

### -field WheaErrSrcTypeCPE

<dd>
<p>A corrected platform error (CPE).</p>
</dd>

### -field WheaErrSrcTypeNMI

<dd>
<p>A nonmaskable interrupt (NMI).</p>
</dd>

### -field WheaErrSrcTypePCIe

<dd>
<p>A PCI Express (PCIe) error.</p>
</dd>

### -field WheaErrSrcTypeGeneric

<dd>
<p>A type of error source that does not conform to any of the other WHEA_ERROR_SOURCE_TYPE enumeration values.</p>
</dd>

### -field WheaErrSrcTypeINIT

<dd>
<p>An Itanium processor INIT error.</p>
</dd>

### -field WheaErrSrcTypeBOOT

<dd>
<p>A boot error source.</p>
</dd>

### -field WheaErrSrcTypeSCIGeneric

<dd>
<p>A service control interrupt (SCI).</p>
</dd>

### -field WheaErrSrcTypeIPFMCA

<dd>
<p>An Itanium processor machine check abort (MCA).</p>
</dd>

### -field WheaErrSrcTypeIPFCMC

<dd>
<p>An Itanium processor corrected machine check (CMC).</p>
</dd>

### -field WheaErrSrcTypeIPFCPE

<dd>
<p>An Itanium processor corrected platform error (CPE).</p>
</dd>

### -field WheaErrSrcTypeMax

<dd>
<p>The maximum number of error source types that can report hardware errors.</p>
</dd>
</dl>

## -remarks
<p>The <a href="..\ntddk\ns-ntddk--whea-error-source-descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure contains a member of type WHEA_ERROR_SOURCE_TYPE that specifies the type of error source that is described by the structure.</p>

<p>The <a href="whea.whea_error_packet">WHEA_ERROR_PACKET</a> structure contains a member of type WHEA_ERROR_SOURCE_TYPE that specifies the type of error source that caused the error condition described by the structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
</p>
</td>
</tr>
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
<a href="whea.whea_error_packet">WHEA_ERROR_PACKET</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-error-source-descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_SOURCE_TYPE enumeration%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>