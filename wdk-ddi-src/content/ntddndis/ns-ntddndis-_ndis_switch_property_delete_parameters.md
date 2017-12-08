---
UID: NS.NTDDNDIS._NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS
title: _NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS
author: windows-driver-content
description: The NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS structure specifies the parameters for a Hyper-V extensible switch profile property that will be deleted.
old-location: netvista\ndis_switch_property_delete_parameters.htm
old-project: netvista
ms.assetid: dcedbdd0-178b-4e44-aaaa-25a5b219324a
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS, *PNDIS_SWITCH_PROPERTY_DELETE_PARAMETERS, NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS
req.alt-loc: Ntddndis.h
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
---

# _NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS structure



## -description
The <b>NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS</b> structure specifies the parameters for a Hyper-V extensible switch profile property that will be deleted. 


## -syntax

````
typedef struct _NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS {
  NDIS_OBJECT_HEADER             Header;
  ULONG                          Flags;
  NDIS_SWITCH_PROPERTY_TYPE      PropertyType;
  NDIS_SWITCH_OBJECT_ID          PropertyId;
  NDIS_SWITCH_OBJECT_INSTANCE_ID PropertyInstanceId;
} NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS, *PNDIS_SWITCH_PROPERTY_DELETE_PARAMETERS;
````


## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS</b> structure. This member is formatted as an <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure.
The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:


### -field NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.
Set the <b>Size</b> member to NDIS_SIZEOF_NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS_REVISION_1.
</dd>
</dl>

### -field Flags

A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.

### -field PropertyType

 An <a href="netvista.ndis_switch_property_type">NDIS_SWITCH_PROPERTY_TYPE</a> enumeration value that specifies the type of extensible switch property that will be deleted.

### -field PropertyId

A GUID value that identifies the property for the extensible switch.



### -field PropertyInstanceId

An NDIS_SWITCH_OBJECT_INSTANCE_ID value that specifies the instance identifier of the  extensible switch property.



## -remarks
The <b>NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS</b> structure is used in OID set requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598281">OID_SWITCH_PROPERTY_DELETE</a>.

For more information about extensible switch policies, see <a href="netvista.hyper_v_extensible_switch_policies">Hyper-V Extensible Switch Policies</a>.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported in NDIS 6.30 and later.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndis_switch_property_type">NDIS_SWITCH_PROPERTY_TYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598281">OID_SWITCH_PROPERTY_DELETE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PROPERTY_DELETE_PARAMETERS structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>