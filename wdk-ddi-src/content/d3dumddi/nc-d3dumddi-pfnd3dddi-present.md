---
UID: NC.d3dumddi.PFND3DDDI_PRESENT
title: PFND3DDDI_PRESENT
author: windows-driver-content
description: The Present function notifies the user-mode display driver that an application finished rendering and requests that the driver display the source surface by either copying or flipping or that the driver perform a color-fill operation.
old-location: display\present.htm
old-project: display
ms.assetid: e90683b4-64b6-4018-96a5-b50118df3367
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: Present
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

# PFND3DDDI_PRESENT callback



## -description
<p>The <i>Present</i> function notifies the user-mode display driver that an application finished rendering and requests that the driver display the source surface by either copying or flipping or that the driver perform a color-fill operation. </p>


## -prototype

````
PFND3DDDI_PRESENT Present;

__checkReturn HRESULT APIENTRY Present(
  _In_       HANDLE            hDevice,
  _In_ const D3DDDIARG_PRESENT *pData
)
{ ... }
````


## -parameters
<dl>

### -param hDevice [in]

<dd>
<p> A handle to the display device (graphics context).</p>
</dd>

### -param pData [in]

<dd>
<p> A pointer to a <a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-present.md">D3DDDIARG_PRESENT</a> structure that describes the resource to display.</p>
</dd>
</dl>

## -returns
<p><i>Present</i> returns one of the following values:</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The resource is successfully displayed.</p><dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><p><i>Present</i> could not allocate the required memory for it to complete.</p>

<p> </p>

## -remarks
<p>The Microsoft Direct3D runtime calls the user-mode display driver's <i>Present</i> function to notify the user-mode display driver that an application finished rendering and to request that the driver display out the source surface or that the driver perform a color-fill operation. If the <b>hSrcResource</b> member of the <a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-present.md">D3DDDIARG_PRESENT</a> structure that the <i>pData</i> parameter points to is non-<b>NULL</b>, <i>Present</i> requests that the user-mode display driver display new content to the screen; if <b>hSrcResource</b> is <b>NULL</b>, <i>Present</i> requests that the user-mode display driver perform a color-fill operation to the screen. </p>

<p>If the <b>hDstResource</b> member of the <a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-present.md">D3DDDIARG_PRESENT</a> structure is <b>NULL</b>, the destination surface is unknown. In addition, the destination surface and a list of clipping rectangles are determined in kernel mode before sending the hardware command stream through DMA to the graphics processor. </p>

<p>As a result, the user-mode display driver cannot generate hardware instructions to perform the present operation. These hardware instructions must be generated by the display miniport driver. However, when the <b>hSrcResource</b> member of D3DDDIARG_PRESENT is non-<b>NULL</b>, the user-mode display driver must derive the allocation handle to the source surface and insert this handle in the <b>hSrcAllocation</b> member of the <a href="..\d3dumddi\ns-d3dumddi--d3dddicb-present.md">D3DDDICB_PRESENT</a> structure in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-presentcb.md">pfnPresentCb</a> function. The display miniport driver can then successfully generate the hardware instructions. The user-mode display driver typically derives the allocation handle from the resource information in the <a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-present.md">D3DDDIARG_PRESENT</a> structure.</p>

<p>If the <b>hDstResource</b> member of D3DDDIARG_PRESENT is non-<b>NULL</b>, the destination surface for the present is known and the user-mode display driver must fill in the <b>hDstAllocation</b> member of <a href="..\d3dumddi\ns-d3dumddi--d3dddicb-present.md">D3DDDICB_PRESENT</a> with the corresponding allocation handle.</p>

<p>If a user-mode display driver exposes a DDI version of less than 0x0000000C (the driver returns this value in the <b>DriverVersion</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg-openadapter.md">D3D10DDIARG_OPENADAPTER</a> structure in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-openadapter.md">OpenAdapter</a> function), the Direct3D runtime first calls the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-flush.md">Flush</a> function to submit any outstanding hardware commands in the command buffer before the runtime calls the user-mode display driver's <i>Present</i> function. In this way, the user-mode display driver's <i>Present</i> function is serialized with render operations (that is, calls to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-rendercb.md">pfnRenderCb</a> function). If a user-mode display driver exposes a DDI version of 0x0000000C or greater and the calling application runs in windowed mode, the runtime also calls <i>Flush</i> before it calls <i>Present</i>. If a user-mode display driver exposes a DDI version of 0x0000000C or greater and the calling application runs in full-screen mode, the runtime will not call <i>Flush</i> before it calls <i>Present</i>. This behavior allows drivers that implement their own threading to queue present calls. A driver that exposes a DDI version of 0x0000000C or greater must call <b>pfnRenderCb</b> to internally flush any outstanding command buffers before the driver calls the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-presentcb.md">pfnPresentCb</a> function.</p>

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
<a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-present.md">D3DDDIARG_PRESENT</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--d3dddi-devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="display.dxgkddipresent">DxgkDdiPresent</a>
</dt>
<dt>
<a href="display.dxgkddirender">DxgkDdiRender</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-flush.md">Flush</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-rendercb.md">pfnRenderCb</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_PRESENT callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>