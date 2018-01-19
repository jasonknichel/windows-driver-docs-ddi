---
UID : NS:ntddndis._NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS
title : _NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS
author : windows-driver-content
description : The NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS structure specifies the parameters for the custom status information of a Hyper-V extensible switch port.
old-location : netvista\ndis_switch_port_feature_status_parameters.htm
old-project : netvista
ms.assetid : 117ba27f-812a-406d-8120-99ba89551164
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS, NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS, *PNDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.30 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS
req.alt-loc : Ntddndis.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS, *PNDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS
---

# _NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS structure
The <b>NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</b> structure specifies the parameters for the custom status information of a Hyper-V extensible switch port. This information is known as <i>feature status</i> information. The format of this information is defined by the independent software vendor (ISV). 

The status information is specified through an <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_feature_status_custom.md">NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</a> structure and is returned through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598274">OID_SWITCH_PORT_FEATURE_STATUS_QUERY</a>.



The <b>NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</b> structure specifies the parameters for the custom status information of a Hyper-V extensible switch port. This information is known as <i>feature status</i> information. The format of this information is defined by the independent software vendor (ISV). 

The status information is specified through an <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_feature_status_custom.md">NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</a> structure and is returned through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598274">OID_SWITCH_PORT_FEATURE_STATUS_QUERY</a>.

## Syntax
````
typedef struct _NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS {
  NDIS_OBJECT_HEADER                       Header;
  ULONG                                    Flags;
  NDIS_SWITCH_PORT_ID                      PortId;
  NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE     FeatureStatusType;
  NDIS_SWITCH_OBJECT_ID                    FeatureStatusId;
  NDIS_SWITCH_OBJECT_VERSION               FeatureStatusVersion;
  NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION SerializationVersion;
  NDIS_SWITCH_OBJECT_INSTANCE_ID           FeatureStatusInstanceId;
  ULONG                                    FeatureStatusBufferLength;
  ULONG                                    FeatureStatusBufferOffset;
  ULONG                                    Reserved;
} NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS, *PNDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS;
````

## Members

        
            `FeatureStatusBufferLength`

            A ULONG value that specifies the size, in bytes, of the feature status buffer.
        
            `FeatureStatusBufferOffset`

            A ULONG value that specifies the offset, in bytes, to the feature status buffer that follows the <b>NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</b> structure. The feature status buffer contains an <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_feature_status_custom.md">NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</a> structure. 

The offset is measured from the start of the <b>NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</b> structure up to the beginning of the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_feature_status_custom.md">NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</a> structure.
        
            `FeatureStatusId`

            An NDIS_SWITCH_OBJECT_ID value that identifies the profile property for the extensible switch port.
        
            `FeatureStatusInstanceId`

            An NDIS_SWITCH_OBJECT_INSTANCE_ID value that identifies the instance of the  feature status information for the extensible switch port.
        
            `FeatureStatusType`

            An <a href="..\ntddndis\ne-ntddndis-_ndis_switch_port_feature_status_type.md">NDIS_SWITCH_PORT_FEATURE_STATUS_TYPE</a> enumeration value that specifies the type of the status information for a custom extensible switch port profile property.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, this member must be set to <b>NdisSwitchPortPropertyTypeCustom</b>.</div>
<div> </div>
        
            `FeatureStatusVersion`

            An NDIS_SWITCH_OBJECT_VERSION value that identifies the version of the profile property for the extensible switch port.
        
            `Flags`

            A ULONG value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.
        
            `Header`

            The type, revision, and size of the <b>NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:
        
            `PortId`

            An NDIS_SWITCH_PORT_ID value that specifies the numeric identifier for an extensible switch port. This value uniquely identifies the port on the extensible switch for which feature status information is to be returned.
        
            `Reserved`

            Reserved for future use.
        
            `SerializationVersion`

            An NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION value that identifies the format version of the serialized port property data. This data is serialized for access by the extension from the Managed Object Format (MOF) file that defined the property.

<div class="alert"><b>Note</b>  For Windows Server 2012, the <b>SerializationVersion</b> member must be set to NDIS_SWITCH_OBJECT_SERIALIZATION_VERSION_1.</div>
<div> </div>

    ## Remarks
        The <b>NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</b> structure is used in OID method requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598274">OID_SWITCH_PORT_FEATURE_STATUS_QUERY</a>. This OID request returns the following structures in the information buffer that is associated with the OID request: 

An <b>NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS</b>  structure that specifies the parameters for a custom property of an extensible switch port  for which status information is to be returned.  The switch extension populates the <b>FeatureStatusVersion</b> member of the structure to reflect the version of the custom status being returned in the NDIS_SWITCH_FEATURE_STATUS_CUSTOM buffer. The Hyper-v Extensible switch populates all other members when issuing the query OID.

An <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_feature_status_custom.md">NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</a> structure that contains the status information for the extensible switch port property.  The switch extension populates the <b>FeatureStatusCustomBufferLength</b> member of the structure to reflect the size of the custom status being returned. The Hyper-v Extensible switch populates all other members when issuing the query OID.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddndis.h (include Ndis.h) |

    ## See Also

        <dl>
<dt><b></b></dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_feature_status_custom.md">NDIS_SWITCH_PORT_FEATURE_STATUS_CUSTOM</a>
</dt>
<dt>
<a href="..\ntddndis\ne-ntddndis-_ndis_switch_port_property_type.md">NDIS_SWITCH_PORT_PROPERTY_TYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598274">OID_SWITCH_PORT_FEATURE_STATUS_QUERY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_FEATURE_STATUS_PARAMETERS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>