---
UID: NF.ndis.NdisRawWritePortUshort
title: NdisRawWritePortUshort
author: windows-driver-content
description: NdisRawWritePortUshort writes a USHORT value to an I/O port on the NIC.
old-location: netvista\ndisrawwriteportushort.htm
old-project: netvista
ms.assetid: f8ad7d35-5832-4258-8666-2c0f1f893f10
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NdisRawWritePortUshort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawWritePortUshort (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawWritePortUshort (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisRawWritePortUshort
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.iface: 
---

# NdisRawWritePortUshort function



## -description
<p><b>NdisRawWritePortUshort</b> writes a USHORT value to an I/O port on the NIC.</p>


## -syntax

````
VOID NdisRawWritePortUshort(
  _In_ ULONG_PTR Port,
  _In_ USHORT    Data
);
````


## -parameters
<dl>

### -param Port [in]

<dd>
<p>Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">
     NdisMRegisterIoPortRange</a>.</p>
</dd>

### -param Data [in]

<dd>
<p>Specifies the USHORT to be written.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p><b>NdisRawWritePortUshort</b> runs fast because it need not map a bus-relative I/O port address onto a
    host-dependent logical port address at every call.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/19ff32ab-b132-4a3a-b2d0-49e11613c30d">NdisRawWritePortUshort (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisRawWritePortUshort (NDIS
   5.1)</b>) in Windows XP.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisrawreadportushort.md">NdisRawReadPortUshort</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisrawwriteportbufferushort.md">NdisRawWritePortBufferUshort</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisrawwriteportuchar.md">NdisRawWritePortUchar</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisrawwriteportulong.md">NdisRawWritePortUlong</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisRawWritePortUshort function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>