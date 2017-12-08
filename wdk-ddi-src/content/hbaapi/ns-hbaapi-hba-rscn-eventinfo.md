---
UID: NS.hbaapi.HBA_RSCN_EventInfo
title: HBA_RSCN_EventInfo
author: windows-driver-content
description: The HBA_Link_EventInfo structure contains information about a WMI RSCN event associated with the fibre channel HBA API.
old-location: storage\hba_rscn_eventinfo.htm
old-project: storage
ms.assetid: d726d974-a877-464d-9721-6caf8a8402bf
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: HBA_RSCN_EventInfo, HBA_RSCN_EVENTINFO, *PHBA_RSCN_EVENTINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBA_RSCN_EVENTINFO
req.alt-loc: hbaapi.h
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

# HBA_RSCN_EventInfo structure



## -description
<p>The HBA_Link_EventInfo structure contains information about a WMI RSCN event associated with the fibre channel HBA API. </p>


## -syntax

````
typedef struct HBA_RSCN_EventInfo {
  HBA_UINT32 PortFcId;
  HBA_UINT32 NPortPage;
  HBA_UINT32 Reserved[2];
} HBA_RSCN_EVENTINFO, *PHBA_RSCN_EVENTINFO;
````


## -struct-fields
<dl>

### -field PortFcId

<dd>
<p>Indicates the port of type Nx_Port through which the event occurred. For a definition of Nx_Port, see the T11 committee's <i>Fibre Channel HBA API</i>.specification.</p>
</dd>

### -field NPortPage

<dd>
<p>Contains port page information. For information about what values this member can have, see section entitled "Affected N-Port Pages" in the <i>FC-FS </i>specification for RSCN ELS. </p>
</dd>

### -field Reserved

<dd>
<p>Reserved. </p>
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
<dt>Hbaapi.h (include Hbaapi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hbaapi\ns-hbaapi-hba-eventinfo.md">HBA_EventInfo</a>
</dt>
<dt>
<a href="..\hbaapi\ns-hbaapi-hba-link-eventinfo.md">HBA_Link_EventInfo</a>
</dt>
<dt>
<a href="..\hbaapi\ns-hbaapi-hba-pty-eventinfo.md">HBA_Pty_EventInfo</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_RSCN_EventInfo structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>