---
UID: NC.d3d12umddi.PFND3D12DDI_CREATECRYPTOSESSIONPOLICY_0030
title: PFND3D12DDI_CREATECRYPTOSESSIONPOLICY_0030
author: windows-driver-content
description: Used to create a crypto session policy.
old-location: display\pfnd3d12ddi_createcryptosessionpolicy_0030.htm
old-project: display
ms.assetid: BB3B2C57-CE5A-4E15-ABCB-4817C0234B62
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DWDDM2_2DDI_SWIZZLE_PATTERN_DESC, D3DWDDM2_2DDI_SWIZZLE_PATTERN_DESC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFND3D12DDI_CREATECRYPTOSESSIONPOLICY_0030
req.alt-loc: d3d12umddi.h
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

# PFND3D12DDI_CREATECRYPTOSESSIONPOLICY_0030 callback



## -description
<p>Used to create a crypto session policy.</p>


## -prototype

````
HRESULT APIENTRY* PFND3D12DDI_CREATECRYPTOSESSIONPOLICY_0030(
             D3D12DDI_HDEVICE                              hDrvDevice,
  _In_ const D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030 *pArgs,
             D3D12DDI_HCRYPTOSESSION_0030                  hDrvCryptoSession,
             D3D12DDI_HCRYPTOSESSIONPOLICY_0030            hDrvCryptoSessionPolicy,
             D3D12DDI_HRTPROTECTEDSESSION_0030             hRtProtectedSession
);
````


## -parameters
<dl>

### -param hDrvDevice 

<dd>
<p>The hardware device being processed.</p>
</dd>

### -param pArgs [in]

<dd>
<p>The arguments used to create a crypto session policy.</p>
</dd>

### -param hDrvCryptoSession 

<dd>
<p>Used to create a crypto session.</p>
</dd>

### -param hDrvCryptoSessionPolicy 

<dd>
<p>Used to create a crypto session policy.</p>
</dd>

### -param hRtProtectedSession 

<dd>
<p>Used to create a protected session.</p>
</dd>
</dl>

## -returns
<p>Returns STATUS_SUCCESS if completed successfully.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h</dt>
</dl>
</td>
</tr>
</table>