---
UID: NE.d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT
title: D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT
author: windows-driver-content
description: Specifies the layout in memory of a stereo 3-D video frame.
old-location: display\d3d11_1ddi_video_processor_stereo_format.htm
old-project: display
ms.assetid: 348d17f3-a688-4f63-87aa-a8588f069c5c
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT
req.alt-loc: D3d10umddi.h
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

# D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT enumeration



## -description
<p>Specifies the layout in memory of a stereo 3-D video frame.</p>


## -syntax

````
typedef enum D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT { 
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO                = 0,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_HORIZONTAL          = 1,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_VERTICAL            = 2,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_SEPARATE            = 3,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET         = 4,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_ROW_INTERLEAVED     = 5,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_COLUMN_INTERLEAVED  = 6,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_CHECKERBOARD        = 7
} D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT;
````


## -enum-fields
<dl>

### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO

<dd>
<p>The sample does not contain stereo data. If the stereo format is not specified, this value is the default.</p>
</dd>

### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_HORIZONTAL

<dd>
<p>Frame 0 and frame 1 are packed side-by-side, as shown in the following diagram.</p>
<p><img alt="Side-by-side packing" src="images/dxgistereo3d02.png"/></p>
<p>All drivers that support stereo video must support this format.</p>
</dd>

### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_VERTICAL

<dd>
<p>Frame 0 and frame 1 are packed top-to-bottom, as shown in the following diagram.</p>
<p><img alt="Top-to-bottom packing" src="images/dxgistereo3d01.png"/></p>
<p>All drivers that support stereo video must support this format.</p>
</dd>

### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_SEPARATE

<dd>
<p>Frame 0 and frame 1 are placed in separate resources or in separate texture array elements within the same resource.</p>
<p>All drivers that support stereo video must support this format.</p>
</dd>

### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET

<dd>
<p>The sample contains non-stereo data. However, the driver should create a left/right output of this sample using a specified offset.  The offset is specified in the <i>MonoOffset</i> parameter of the <a href="display.videoprocessorsetstreamstereoformat">VideoProcessorSetStreamStereoFormat</a> function. </p>
<p>This format is primarily intended for subtitles and other subpicture data, where the entire sample is presented on the same plane.</p>
<p>Support for this stereo format is optional.</p>
</dd>

### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_ROW_INTERLEAVED

<dd>
<p>Frame 0 and frame 1 are packed into interleaved rows, as shown in the following diagram.</p>
<p><img alt="Interleaved rows" src="images/dxgistereo3d03.png"/></p>
<p>Support for this stereo format is optional.</p>
</dd>

### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_COLUMN_INTERLEAVED

<dd>
<p>Frame 0 and frame 1 are packed into interleaved columns, as shown in the following diagram.</p>
<p><img alt="Interleaved columns" src="images/dxgistereo3d04.png"/></p>
<p>Support for this stereo format is optional.</p>
</dd>

### -field D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_CHECKERBOARD

<dd>
<p>Frame 0 and frame 1 are packed in a checkerboard format, as shown in the following diagram.</p>
<p><img alt="Checkerboard packing" src="images/dxgistereo3d05.png"/></p>
<p>Support for this stereo format is optional.</p>
</dd>
</dl>

## -remarks
<p>This enumeration designates the two stereo views as "frame 0" and "frame 1". The <i>LeftViewFrame0</i> parameter of the <a href="display.videoprocessorsetstreamstereoformat">VideoProcessorSetStreamStereoFormat</a> method specifies which view is the left view, and which is the right view.</p>

<p>For packed formats, if the source rectangle clips part of the surface, the driver interprets the rectangle in logical coordinates relative to the stereo view,  rather than absolute pixel coordinates. The result is that frame 0 and frame 1 are clipped proportionately.</p>

<p>To query whether the device supports stereo 3-D video, call <a href="display.getvideoprocessorcaps">GetVideoProcessorCaps</a> and check for the <b>D3D11_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO</b> flag in the <b>FeatureCaps</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11-1ddi-video-processor-caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure. If this capability flag is present, it means that the driver supports all of the stereo formats that are not  listed as optional. To find out which optional formats are supported, call <b>GetVideoProcessorCaps</b> and check the <b>StereoCaps</b> member of the structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11-1ddi-video-processor-caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>
</dt>
<dt>
<a href="display.getvideoprocessorcaps">GetVideoProcessorCaps</a>
</dt>
<dt>
<a href="display.videoprocessorsetstreamstereoformat">VideoProcessorSetStreamStereoFormat</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>