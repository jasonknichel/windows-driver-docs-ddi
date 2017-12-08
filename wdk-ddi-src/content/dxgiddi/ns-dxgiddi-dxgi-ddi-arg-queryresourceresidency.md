---
UID: NS.dxgiddi.DXGI_DDI_ARG_QUERYRESOURCERESIDENCY
title: DXGI_DDI_ARG_QUERYRESOURCERESIDENCY
author: windows-driver-content
description: The DXGI_DDI_ARG_QUERYRESOURCERESIDENCY structure describes the residency status of a list of resources.
old-location: display\dxgi_ddi_arg_queryresourceresidency.htm
old-project: display
ms.assetid: 140a92a8-4b82-47d0-855c-6bc1f9a3d167
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGI_DDI_ARG_QUERYRESOURCERESIDENCY, DXGI_DDI_ARG_QUERYRESOURCERESIDENCY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGI_DDI_ARG_QUERYRESOURCERESIDENCY
req.alt-loc: dxgiddi.h
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

# DXGI_DDI_ARG_QUERYRESOURCERESIDENCY structure



## -description
<p>The DXGI_DDI_ARG_QUERYRESOURCERESIDENCY structure describes the residency status of a list of resources. </p>


## -syntax

````
typedef struct DXGI_DDI_ARG_QUERYRESOURCERESIDENCY {
  DXGI_DDI_HDEVICE         hDevice;
  const DXGI_DDI_HRESOURCE *pResources;
  DXGI_DDI_RESIDENCY       *pStatus;
  SIZE_T                   Resources;
} DXGI_DDI_ARG_QUERYRESOURCERESIDENCY;
````


## -struct-fields
<dl>

### -field hDevice

<dd>
<p>[in] A handle to the display device (graphics context) on which the driver determines resource residency status. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg-createdevice.md">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createdevice.md">CreateDevice(D3D10)</a> function to create the display device. </p>
</dd>

### -field pResources

<dd>
<p>[in] An array of handles to the resources to query for residency on. </p>
</dd>

### -field pStatus

<dd>
<p>[out] A pointer to an array of DXGI_DDI_RESIDENCY values. The number of elements in the array is specified by the <b>Resources</b> member, and each element receives one of the following values to indicate the residency status of the corresponding resource in the array that <b>pResources</b> specifies. </p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>DXGI_DDI_RESIDENCY_FULLY_RESIDENT (1)</p>
</td>
<td>
<p>The resources reside in GPU memory, which is the highest residency status.</p>
</td>
</tr>
<tr>
<td>
<p>DXGI_DDI_RESIDENCY_RESIDENT_IN_SHARED_MEMORY (2)</p>
</td>
<td>
<p>The resources reside in shared memory.</p>
</td>
</tr>
<tr>
<td>
<p>DXGI_DDI_RESIDENCY_EVICTED_TO_DISK (3)</p>
</td>
<td>
<p>The resources are nonresident, which is the lowest residency status.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field Resources

<dd>
<p>[in] The number of elements in the <i>pResources</i> and <i>pStatus</i> arrays. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dxgiddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.queryresourceresidencydxgi">QueryResourceResidencyDXGI</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_ARG_QUERYRESOURCERESIDENCY structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>