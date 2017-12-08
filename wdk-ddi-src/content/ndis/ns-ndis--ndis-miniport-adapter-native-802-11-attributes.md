---
UID: NS.ndis._NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES
title: NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\ndis_miniport_adapter_native_802_11_attributes.htm
old-project: netvista
ms.assetid: f841c7f9-9ad3-4b53-b2d9-0d66d6e64b8b
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
req.iface: 
---

# NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure



## -description

## -syntax

````
typedef struct {
  NDIS_OBJECT_HEADER       Header;
  ULONG                    OpModeCapability;
  ULONG                    NumOfTXBuffers;
  ULONG                    NumOfRXBuffers;
  BOOLEAN                  MultiDomainCapabilityImplemented;
  ULONG                    NumSupportedPhys;
  PDOT11_PHY_ATTRIBUTES    SupportedPhyAttributes;
  PDOT11_EXTSTA_ATTRIBUTES ExtSTAAttributes;
#if (NDIS_SUPPORT_NDIS620)
  PDOT11_VWIFI_ATTRIBUTES  VWiFiAttributes;
  PDOT11_EXTAP_ATTRIBUTES  ExtAPAttributes;
#endif 
#if (NDIS_SUPPORT_NDIS630)
  PDOT11_WFD_ATTRIBUTES    WFDAttributes;
#endif 
} NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES;
````


## -struct-fields
<dl>

### -field Header

<dd>
<p>The type, revision, and size of the NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure. This
     member is formatted as an 
     <a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a> structure.
     </p>
<p>The miniport driver must set the members of 
     <b>Header</b> to the following values:</p>
<p></p>
<dl>

### -field Type

<dd>
<p>This member must be set to NDIS_OBJECT_TYPE_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES.</p>
</dd>

### -field Revision

<dd>
<p>For the Windows Vista or Windows Server 2008 operating systems, this member must be set to
        NDIS_MINIPORT_ADAPTER_802_11_ATTRIBUTES_REVISION_1.</p>
<p>For later versions of the Windows operating systems, this member must be set to
        NDIS_MINIPORT_ADAPTER_802_11_ATTRIBUTES_REVISION_2.</p>
</dd>

### -field Size

<dd>
<p>For the Windows Vista or Windows Server 2008 operating systems, this member must be set to
        NDIS_SIZEOF_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES_REVISION_1.</p>
<p>For later versions of the Windows operating systems, this member must be set to
        NDIS_SIZEOF_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES_REVISION_2.</p>
</dd>
</dl>
<p>For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a>.</p>
</dd>

### -field OpModeCapability

<dd>
<p>A bitmask of the miniport driver's supported operation modes. This bitmask is defined through the
     following:
     </p>
<p></p>
<dl>

### -field DOT11_OPERATION_MODE_EXTENSIBLE_AP

<dd>
<p>Specifies that the miniport driver supports the Extensible Access Point (ExtAP) operation mode.
       </p>
<p>This value is available beginning with Windows 7.</p>
</dd>

### -field DOT11_OPERATION_MODE_EXTENSIBLE_STATION

<dd>
<p>Specifies that the miniport driver supports the Extensible Station (ExtSTA) operation
       mode.</p>
</dd>

### -field DOT11_OPERATION_MODE_NETWORK_MONITOR

<dd>
<p>Specifies that the miniport driver supports the Network Monitor (NetMon) operation mode.</p>
</dd>
</dl>
<p>For more information about operation modes, see 
     <a href="netvista.native_802_11_operation_modes">Native 802.11 Operation
     Modes</a>.</p>
</dd>

### -field NumOfTXBuffers

<dd>
<p>The maximum number of media access control (MAC) service data unit (MSDU) packets that the 802.11
     station can hold in its transmit queue. The miniport driver must support a minimum transmit queue depth
     of 64.
     </p>
<p>The value of this member must not include the number of transmit buffers that the 802.11 station uses
     to send packets on its own, such as Beacon packets or 802.11 control packets.</p>
</dd>

### -field NumOfRXBuffers

<dd>
<p>The maximum number of MSDU packets that the 802.11 station can buffer in its receive queue. The
     miniport driver must support a minimum receive queue depth of 64.</p>
</dd>

### -field MultiDomainCapabilityImplemented

<dd>
<p>A Boolean value that, if <b>TRUE</b>, specifies that the 802.11 station can operate in multiple
     regulatory domains. For more information about 802.11 regulatory domains, refer to the IEEE 802.11d-2001
     standard.</p>
</dd>

### -field NumSupportedPhys

<dd>
<p>The number of PHYs on the 802.11 station.</p>
</dd>

### -field SupportedPhyAttributes

<dd>
<p>A pointer to an array of 
     <a href="..\windot11\ns-windot11-dot11-phy-attributes.md">DOT11_PHY_ATTRIBUTES</a> structures. This
     array must have 
     <b>NumSupportedPhys</b> entries and must be sorted in the same order as the list of PHY types returned
     through a query of 
     <a href="netvista.oid_dot11_supported_phy_types">
     OID_DOT11_SUPPORTED_PHY_TYPES</a>.</p>
</dd>

### -field ExtSTAAttributes

<dd>
<p>A pointer to a 
     <a href="..\windot11\ns-windot11-dot11-extsta-attributes.md">DOT11_EXTSTA_ATTRIBUTES</a> structure
     that specifies the attributes of the miniport driver and 802.11 station when operating in Extensible
     Station (ExtSTA) mode. For more information about this operation mode, see 
     <a href="netvista.extensible_station_operation_mode">Extensible Station Operation
     Mode</a>.</p>
</dd>

### -field VWiFiAttributes

<dd>
<p>A pointer to a 
      <a href="..\windot11\ns-windot11-dot11-vwifi-attributes.md">DOT11_VWIFI_ATTRIBUTES</a> structure
      that specifies the attributes of the miniport driver and 802.11 station when it operates in Virtual
      WiFi mode.</p>
<p>This member is available beginning with Windows 7.</p>
</dd>

### -field ExtAPAttributes

<dd>
<p>A pointer to a 
      <a href="..\windot11\ns-windot11--dot11-extap-attributes.md">DOT11_EXTAP_ATTRIBUTES</a> structure
      that specifies the attributes of the miniport driver and 802.11 station when it operates in Extensible
      Access Point (ExtAP) mode.</p>
<p>This member is available beginning with Windows 7.</p>
</dd>

### -field WFDAttributes

<dd>
<p>A pointer to a 
      <a href="..\windot11\ns-windot11--dot11-wfd-attributes.md">DOT11_WFD_ATTRIBUTES</a> structure
      that specifies the attributes of the miniport driver and 802.11 station when it operates in Wi-Fi Direct (WFD) mode.</p>
<p>This member is available beginning with Windows 8.</p>
</dd>
</dl>

## -remarks
<p>When its 
    <a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a> function is
    called, the miniport driver must call the 
    <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
    NdisMSetMiniportAttributes</a> function to define the Native 802.11 attributes of the driver and 802.11
    station. The miniport driver must follow these guidelines when it makes the call to 
    <b>NdisMSetMiniportAttributes</b>:</p>

<p>The 
      <i>MiniportAttributes</i> parameter must be set to the address of a driver-allocated block of memory
      that contains an NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure along with the ExtSTA
      attributes and an array of PHY attributes.</p>

<p>The 
      <b>SupportedPhyAttributes</b> member must be the address of the array of 
      <a href="..\windot11\ns-windot11-dot11-phy-attributes.md">DOT11_PHY_ATTRIBUTES</a> structures. This
      array must be within the driver-allocated memory block referenced by the 
      <i>MiniportAttributes</i> parameter.</p>

<p>The 
      <b>ExtSTAAttributes</b> member must be the address of a 
      <a href="..\windot11\ns-windot11-dot11-extsta-attributes.md">DOT11_EXTSTA_ATTRIBUTES</a> structure.
      This structure must be within the driver-allocated memory block referenced by the 
      <i>MiniportAttributes</i> parameter.</p>

<p>For more information about the initialization requirements for a Native 802.11 miniport driver, see 
    <a href="netvista.native_802_11_miniport_driver_initialization">Native 802.11 Miniport
    Driver Initialization</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating
   systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\windot11\ns-windot11--dot11-extap-attributes.md">DOT11_EXTAP_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11-dot11-extsta-attributes.md">DOT11_EXTSTA_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11-dot11-phy-attributes.md">DOT11_PHY_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11-dot11-vwifi-attributes.md">DOT11_VWIFI_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11--dot11-wfd-attributes.md">DOT11_WFD_ATTRIBUTES</a>
</dt>
<dt>
<a href="netvista.extensible_station_operation_mode">Extensible Station Operation
   Mode</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569426">OID_DOT11_SUPPORTED_PHY_TYPES</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="netvista.native_802_11_miniport_driver_initialization">Native 802.11 Miniport
   Driver Initialization</a>
</dt>
<dt>
<a href="netvista.native_802_11_operation_modes">Native 802.11 Operation Modes</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>