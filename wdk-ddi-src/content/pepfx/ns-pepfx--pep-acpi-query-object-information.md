---
UID: NS.pepfx._PEP_ACPI_QUERY_OBJECT_INFORMATION
title: PEP_ACPI_QUERY_OBJECT_INFORMATION
author: windows-driver-content
description: The PEP_ACPI_QUERY_OBJECT_INFORMATION structure contains information about an ACPI object.
old-location: kernel\pep_acpi_query_object_information.htm
old-project: kernel
ms.assetid: 71E43364-CBD6-4628-B51C-B41315E0E800
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PEP_ACPI_QUERY_OBJECT_INFORMATION, PEP_ACPI_QUERY_OBJECT_INFORMATION, *PPEP_ACPI_QUERY_OBJECT_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_ACPI_QUERY_OBJECT_INFORMATION
req.alt-loc: pepfx.h
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

# PEP_ACPI_QUERY_OBJECT_INFORMATION structure



## -description
<p>The <b>PEP_ACPI_QUERY_OBJECT_INFORMATION</b> structure contains information about an ACPI object.</p>


## -syntax

````
typedef struct _PEP_ACPI_QUERY_OBJECT_INFORMATION {
  PEPHANDLE            DeviceHandle;
  PEP_ACPI_OBJECT_NAME Name;
  PEP_ACPI_OBJECT_TYPE Type;
  ULONG                ObjectFlags;
  union {
    struct {
      ULONG InputArgumentCount;
      ULONG OutputArgumentCount;
    } MethodObject;
  } DUMMYUNIONNAME;
} PEP_ACPI_QUERY_OBJECT_INFORMATION, *PPEP_ACPI_QUERY_OBJECT_INFORMATION;
````


## -struct-fields
<dl>

### -field DeviceHandle

<dd>
<p>[in] A PEPHANDLE value that identifies the device's registration for ACPI services. The platform extension plug-in (PEP) supplied this handle in response to a previous <a href="kernel.pep_notify_acpi_register_device">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a> notification.</p>
</dd>

### -field Name

<dd>
<p>[in] A <a href="..\pepfx\ns-pepfx--pep-acpi-object-name.md">PEP_ACPI_OBJECT_NAME</a> union that specifies the path-relative, four-character name of the object.</p>
</dd>

### -field Type

<dd>
<p>[in] A <a href="..\pepfx\ne-pepfx--pep-acpi-object-type.md">PEP_ACPI_OBJECT_TYPE</a> enumeration value that specifies the object type. Currently, a control method is the only object type that is defined for this member (<b>Type</b> = <b>PepAcpiObjectTypeMethod</b>).</p>
</dd>

### -field ObjectFlags

<dd>
<p>[in] A set of input flags. No flags are currently defined for this member, which is always set to PEP_ACPI_OBJECT_FLAG_NONE (0x0).</p>
</dd>

### -field DUMMYUNIONNAME

<dd>
<p>The query result. If the specified object is a control method, the platform extension plug-in (PEP) writes the query result to the <b>MethodObject</b> member of this union.</p>
<dl>

### -field MethodObject

<dd>
<p>[out] Information about a control method object.</p>
<dl>

### -field InputArgumentCount

<dd>
<p>The number of input arguments expected by the control method.</p>
</dd>

### -field OutputArgumentCount

<dd>
<p>The number of output arguments produced by the control method.</p>
</dd>
</dl>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p>This structure is used by the <a href="kernel.pep_notify_acpi_query_object_information">PEP_NOTIFY_ACPI_QUERY_OBJECT_INFORMATION</a> notification. The <b>Name</b>, <b>Type</b>, and <b>Flags</b> members of the structure contain input values that the Windows <a href="kernel.power_management_framework__pofx__routines">power management framework</a> (PoFx) supplies when this notification is sent. The <b>MethodObject</b> member contains an output value that the PEP writes to the structure in response to the notification.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 10.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Pepfx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.pep_notify_acpi_register_device">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a>
</dt>
<dt>
<a href="..\pepfx\ns-pepfx--pep-acpi-object-name.md">PEP_ACPI_OBJECT_NAME</a>
</dt>
<dt>
<a href="..\pepfx\ne-pepfx--pep-acpi-object-type.md">PEP_ACPI_OBJECT_TYPE</a>
</dt>
<dt>
<a href="kernel.pep_notify_acpi_query_object_information">PEP_NOTIFY_ACPI_QUERY_OBJECT_INFORMATION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_QUERY_OBJECT_INFORMATION structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>