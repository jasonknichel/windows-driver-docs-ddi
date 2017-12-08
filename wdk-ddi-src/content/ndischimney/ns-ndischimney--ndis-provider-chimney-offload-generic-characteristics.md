---
UID: NS.ndischimney._NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
title: NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
author: windows-driver-content
description: The NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies the generic chimney offload miniport entry points of an offload target or intermediate driver.
old-location: netvista\ndis_provider_chimney_offload_generic_characteristics.htm
old-project: netvista
ms.assetid: e80a9999-2e4e-4da0-8aae-54ee71d9249d
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, *PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
req.alt-loc: ndischimney.h
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

# NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]</p>
<p>The NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies the generic chimney
  offload miniport entry points of an offload target or intermediate driver. Generic chimney offload entry
  points pertain to all chimney offload types. Currently, TCP chimney offload is the only defined chimney
  offload type.</p>


## -syntax

````
typedef struct _NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS {
  NDIS_OBJECT_HEADER           Header;
  ULONG                        Flags;
  W_INITIATE_OFFLOAD_HANDLER   InitiateOffloadHandler;
  W_TERMINATE_OFFLOAD_HANDLER  TerminateOffloadHandler;
  W_UPDATE_OFFLOAD_HANDLER     UpdateOffloadHandler;
  W_INVALIDATE_OFFLOAD_HANDLER InvalidateOffloadHandler;
  W_QUERY_OFFLOAD_HANDLER      QueryOffloadHandler;
} NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, *PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS;
````


## -struct-fields
<dl>

### -field Header

<dd>
<p>The header of the NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure. The header is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a> structure. The
     NDIS_OBJECT_HEADER structure contains the revision number of the
     NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure and the size of the
     NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure, including the header, in bytes. The 
     <b>Type</b> member of the header is not significant.</p>
</dd>

### -field Flags

<dd>
<p>Reserved for system use.</p>
</dd>

### -field InitiateOffloadHandler

<dd>
<p>The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w-initiate-offload-handler.md">
     MiniportInitiateOffload</a> function.</p>
</dd>

### -field TerminateOffloadHandler

<dd>
<p>The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w-terminate-offload-handler.md">
     MiniportTerminateOffload</a> function.</p>
</dd>

### -field UpdateOffloadHandler

<dd>
<p>The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w-update-offload-handler.md">
     MiniportUpdateOffload</a> function.</p>
</dd>

### -field InvalidateOffloadHandler

<dd>
<p>The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w-invalidate-offload-handler.md">
     MiniportInvalidateOffload</a> function.</p>
</dd>

### -field QueryOffloadHandler

<dd>
<p>The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w-query-offload-handler.md">
     MiniportQueryOffload</a> function.</p>
</dd>
</dl>

## -remarks
<p>To register its generic chimney offload entry points, an offload target or intermediate driver calls
    the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> function
    in the context of the 
    <a href="netvista.miniportsetoptions">MiniportSetOptions</a> function. To the 
    <b>NdisSetOptionalHandlers</b> function, the offload target or intermediate driver passes a pointer to the
    NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndischimney.h (include Ndischimney.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndischimney\nc-ndischimney-w-initiate-offload-handler.md">MiniportInitiateOffload</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-w-invalidate-offload-handler.md">MiniportInvalidateOffload</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-w-query-offload-handler.md">MiniportQueryOffload</a>
</dt>
<dt>
<a href="netvista.miniportsetoptions">MiniportSetOptions</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-w-terminate-offload-handler.md">MiniportTerminateOffload</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-w-update-offload-handler.md">MiniportUpdateOffload</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>