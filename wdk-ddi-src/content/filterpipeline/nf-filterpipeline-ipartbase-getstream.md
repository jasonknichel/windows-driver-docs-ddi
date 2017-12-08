---
UID: NF.filterpipeline.IPartBase.GetStream
title: IPartBase::GetStream
author: windows-driver-content
description: The GetStream method gets the stream object that contains the part data. Each part has part-specific data that is associated with it (for example, a font, image, and page markup).
old-location: print\ipartbase_getstream.htm
old-project: print
ms.assetid: 83840bca-2e6e-4982-9ec1-e1e278908993
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IPartBase, GetStream, IPartBase::GetStream
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPartBase.GetStream
req.alt-loc: filterpipeline.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: IPartBase
---

# IPartBase::GetStream method



## -description
<p>The <b>GetStream</b> method gets the stream object that contains the part data. Each part has part-specific data that is associated with it (for example, a font, image, and page markup).</p>


## -syntax

````
HRESULT GetStream(
  [out] IPrintReadStream **ppStream
);
````


## -parameters
<dl>

### -param ppStream [out]

<dd>
<p>The stream object that contains the part data to be read.</p>
</dd>
</dl>

## -returns
<p><b>GetStream</b> returns an <b>HRESULT</b> value.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Filterpipeline.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IDL</p>
</th>
<td width="70%">
<dl>
<dt>Filterpipeline.idl</dt>
</dl>
</td>
</tr>
</table>