---
UID: NS.windot11.DOT11_CIPHER_ALGORITHM_LIST
title: DOT11_CIPHER_ALGORITHM_LIST
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_cipher_algorithm_list.htm
old-project: netvista
ms.assetid: b6d96a82-f744-4663-8373-886f4245c106
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: DOT11_CIPHER_ALGORITHM_LIST, DOT11_CIPHER_ALGORITHM_LIST, *PDOT11_CIPHER_ALGORITHM_LIST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_CIPHER_ALGORITHM_LIST
req.alt-loc: windot11.h
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
req.product: Windows 10 or later.
---

# DOT11_CIPHER_ALGORITHM_LIST structure



## -description

## -syntax

````
typedef struct DOT11_CIPHER_ALGORITHM_LIST {
  NDIS_OBJECT_HEADER     Header;
  ULONG                  uNumOfEntries;
  ULONG                  uTotalNumOfEntries;
  DOT11_CIPHER_ALGORITHM AlgorithmIds[1];
} DOT11_CIPHER_ALGORITHM_LIST, *PDOT11_CIPHER_ALGORITHM_LIST;
````


## -struct-fields
<dl>

### -field Header

<dd>
<p>The type, revision, and size of the DOT11_CIPHER_ALGORITHM_LIST structure. This member is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a> structure.
     </p>
<p>The miniport driver must set the members of 
     <b>Header</b> to the following values:</p>
<p></p>
<dl>

### -field Type

<dd>
<p>This member must be set to NDIS_OBJECT_TYPE_DEFAULT.</p>
</dd>

### -field Revision

<dd>
<p>This member must be set to DOT11_CIPHER_ALGORITHM_LIST_REVISION_1.</p>
</dd>

### -field Size

<dd>
<p>This member must be set to 
       sizeof(DOT11_CIPHER_ALGORITHM_LIST).</p>
</dd>
</dl>
<p>For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a>.</p>
</dd>

### -field uNumOfEntries

<dd>
<p>The number of entries in the 
     <b>AlgorithmIds</b> array.</p>
</dd>

### -field uTotalNumOfEntries

<dd>
<p>The maximum number of entries that the 
     <b>AlgorithmIds</b> array can contain.</p>
</dd>

### -field AlgorithmIds

<dd>
<p>The cipher algorithm, which is defined by a 
     <a href="..\wlantypes\ne-wlantypes--dot11-cipher-algorithm.md">DOT11_CIPHER_ALGORITHM</a> enumerator
     value.
     </p>
<p>The list of cipher algorithms is sorted by preference. 
     <b>AlgorithmIds</b> [0] defines the cipher algorithm with the highest preference.</p>
</dd>
</dl>

## -remarks
<p>A miniport driver returns the DOT11_CIPHER_ALGORITHM_LIST structure when it is queried by either 
    <a href="netvista.oid_dot11_supported_unicast_algorithm_pair">
    OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a> or 
    <a href="netvista.oid_dot11_supported_multicast_algorithm_pair">
    OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>.</p>

<p>When these OIDs are queried, the miniport driver must verify that the 
    <b>InformationBuffer</b> member of the 
    <a href="..\ndis\nc-ndis-miniport-oid-request.md">MiniportOidRequest</a> function's
    <i>OidRequest</i> parameter is large enough to return the entire DOT11_CIPHER_ALGORITHM_LIST structure,
    including all entries in the 
    <b>AlgorithmIds</b> array. The value of the 
    <b>InformationBufferLength</b> member of the 
    <i>OidRequest</i> parameter determines what the miniport driver must do, as the following list shows:</p>

<p>If the value of the 
      <b>InformationBufferLength</b> member is less than the length, in bytes, of the entire
      DOT11_CIPHER_ALGORITHM_LIST structure, the miniport driver must do the following:</p>

<p>For the 
        <i>OidRequest</i> parameter, set the 
        <b>BytesWritten</b> member to zero and the 
        <b>BytesNeeded</b> member to the length, in bytes, of the entire DOT11_CIPHER_ALGORITHM_LIST
        structure.</p>

<p>Fail the query request by returning NDIS_STATUS_BUFFER_OVERFLOW from its 
        <a href="..\ndis\nc-ndis-miniport-oid-request.md">MiniportOidRequest</a> function.</p>

<p>If the value of the 
      <b>InformationBufferLength</b> member is greater than or equal to the length, in bytes, of the entire
      DOT11_CIPHER_ALGORITHM_LIST structure, the miniport driver must do the following to complete a
      successful query request:</p>

<p>For the DOT11_CIPHER_ALGORITHM_LIST structure, set the 
        <b>uNumOfEntries</b> and 
        <b>uTotalNumOfEntries</b> members to the total number of entries in the 
        <b>AlgorithmIds</b> array.</p>

<p>For the 
        <i>OidRequest</i> parameter, set the 
        <b>BytesNeeded</b> member to zero and the 
        <b>BytesWritten</b> member to the length, in bytes, of the entire DOT11_CIPHER_ALGORITHM_LIST
        structure. The miniport driver must also copy the entire DOT11_CIPHER_ALGORITHM_LIST structure to the
        
        <b>InformationBuffer</b> member.</p>

<p>Return NDIS_STATUS_SUCCESS from its 
        <a href="..\ndis\nc-ndis-miniport-oid-request.md">MiniportOidRequest</a> function.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows Vista.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Windot11.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\wlantypes\ne-wlantypes--dot11-cipher-algorithm.md">DOT11_CIPHER_ALGORITHM</a>
</dt>
<dt>
<a href="netvista.oid_dot11_supported_multicast_algorithm_pair">
   OID_DOT11_SUPPORTED_MULTICAST_ALGORITHM_PAIR</a>
</dt>
<dt>
<a href="netvista.oid_dot11_supported_unicast_algorithm_pair">
   OID_DOT11_SUPPORTED_UNICAST_ALGORITHM_PAIR</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_CIPHER_ALGORITHM_LIST structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>