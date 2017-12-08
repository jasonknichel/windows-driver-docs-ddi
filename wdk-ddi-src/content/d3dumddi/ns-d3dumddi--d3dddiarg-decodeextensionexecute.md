---
UID: NS.d3dumddi._D3DDDIARG_DECODEEXTENSIONEXECUTE
title: D3DDDIARG_DECODEEXTENSIONEXECUTE
author: windows-driver-content
description: The D3DDDIARG_DECODEEXTENSIONEXECUTE structure describes a nonstandard Microsoft DirectX Video Acceleration (VA) decode operation to perform.
old-location: display\d3dddiarg_decodeextensionexecute.htm
old-project: display
ms.assetid: 10c69928-a12f-4583-a3cc-7c4a81da4b03
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DDDIARG_DECODEEXTENSIONEXECUTE, D3DDDIARG_DECODEEXTENSIONEXECUTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_DECODEEXTENSIONEXECUTE
req.alt-loc: d3dumddi.h
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

# D3DDDIARG_DECODEEXTENSIONEXECUTE structure



## -description
<p>The D3DDDIARG_DECODEEXTENSIONEXECUTE structure describes a nonstandard Microsoft DirectX Video Acceleration (VA) decode operation to perform.</p>


## -syntax

````
typedef struct _D3DDDIARG_DECODEEXTENSIONEXECUTE {
  HANDLE                hDecode;
  UINT                  Function;
  DXVADDI_PRIVATEDATA   *pPrivateInput;
  DXVADDI_PRIVATEDATA   *pPrivateOutput;
  UINT                  NumBuffers;
  DXVADDI_PRIVATEBUFFER *pBuffers;
} D3DDDIARG_DECODEEXTENSIONEXECUTE;
````


## -struct-fields
<dl>

### -field hDecode

<dd>
<p>[in] A handle to the DirectX VA decode device. The user-mode display driver returns this handle in a call to its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createdecodedevice.md">CreateDecodeDevice</a> function.</p>
</dd>

### -field Function

<dd>
<p>[in] A specific decode operation to perform. The possible values for this member are defined by the nonstandard decode device.</p>
</dd>

### -field pPrivateInput

<dd>
<p>[in] A pointer to a <a href="..\d3dumddi\ns-d3dumddi--dxvaddi-privatedata.md">DXVADDI_PRIVATEDATA</a> structure that contains data that the driver requires to perform the decode operation.</p>
</dd>

### -field pPrivateOutput

<dd>
<p>[out] A pointer to a DXVADDI_PRIVATEDATA structure that contains data about the decode operation that the driver returns.</p>
</dd>

### -field NumBuffers

<dd>
<p>[in] The number of buffers in the list that is pointed to by <b>pBuffers</b>.</p>
</dd>

### -field pBuffers

<dd>
<p>
      [in] A pointer to a list of <a href="..\d3dumddi\ns-d3dumddi--dxvaddi-privatebuffer.md">DXVADDI_PRIVATEBUFFER</a> structures that describe private buffers that a nonstandard decoder uses to perform a decode operation.
     </p>
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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createdecodedevice.md">CreateDecodeDevice</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-decodeextensionexecute.md">DecodeExtensionExecute</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--dxvaddi-privatebuffer.md">DXVADDI_PRIVATEBUFFER</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--dxvaddi-privatedata.md">DXVADDI_PRIVATEDATA</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DECODEEXTENSIONEXECUTE structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>