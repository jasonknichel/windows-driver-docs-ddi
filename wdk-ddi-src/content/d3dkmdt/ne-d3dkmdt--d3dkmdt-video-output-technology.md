---
UID: NE.d3dkmdt._D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY
title: D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY
author: windows-driver-content
description: The D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY enumerated type indicates the type of connector a video output device (on the display adapter) uses to connect to an external display device.
old-location: display\d3dkmdt_video_output_technology.htm
old-project: display
ms.assetid: 5a0876a0-5c27-47aa-9215-1b2bd8612306
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO, DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY
req.alt-loc: d3dkmdt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY enumeration



## -description
<p>The D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY enumerated type indicates the type of connector a video output device (on the display adapter) uses to connect to an external display device.</p>


## -syntax

````
typedef enum _D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY { 
  D3DKMDT_VOT_UNINITIALIZED         = -2,
  D3DKMDT_VOT_OTHER                 = -1,
  D3DKMDT_VOT_HD15                  = 0,
  D3DKMDT_VOT_SVIDEO                = 1,
  D3DKMDT_VOT_COMPOSITE_VIDEO       = 2,
  D3DKMDT_VOT_COMPONENT_VIDEO       = 3,
  D3DKMDT_VOT_DVI                   = 4,
  D3DKMDT_VOT_HDMI                  = 5,
  D3DKMDT_VOT_LVDS                  = 6,
  D3DKMDT_VOT_D_JPN                 = 8,
  D3DKMDT_VOT_SDI                   = 9,
  D3DKMDT_VOT_DISPLAYPORT_EXTERNAL  = 10,
  D3DKMDT_VOT_DISPLAYPORT_EMBEDDED  = 11,
  D3DKMDT_VOT_UDI_EXTERNAL          = 12,
  D3DKMDT_VOT_UDI_EMBEDDED          = 13,
  D3DKMDT_VOT_SDTVDONGLE            = 14,
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3_M1)
  D3DKMDT_VOT_MIRACAST              = 15,
#endif 
  D3DKMDT_VOT_INTERNAL              = 0x80000000,
  D3DKMDT_VOT_SVIDEO_4PIN           = D3DKMDT_VOT_SVIDEO,
  D3DKMDT_VOT_SVIDEO_7PIN           = D3DKMDT_VOT_SVIDEO,
  D3DKMDT_VOT_RF                    = D3DKMDT_VOT_COMPOSITE_VIDEO,
  D3DKMDT_VOT_RCA_3COMPONENT        = D3DKMDT_VOT_COMPONENT_VIDEO,
  D3DKMDT_VOT_BNC                   = D3DKMDT_VOT_COMPONENT_VIDEO
} D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY;
````


## -enum-fields
<dl>

### -field D3DKMDT_VOT_UNINITIALIZED

<dd>
<p>Indicates that a variable of type D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY has not yet been assigned a meaningful value.</p>
</dd>

### -field D3DKMDT_VOT_OTHER

<dd>
<p>Indicates that the video output device connects to an external display device through a connector that is not one of the types that is indicated by the following values in this enumeration.</p>
</dd>

### -field D3DKMDT_VOT_HD15

<dd>
<p>Indicates that the video output device connects to an external display device through an HD15 (VGA) connector.</p>
</dd>

### -field D3DKMDT_VOT_SVIDEO

<dd>
<p>Indicates that the video output device connects to an external display device through an S-video connector.</p>
</dd>

### -field D3DKMDT_VOT_COMPOSITE_VIDEO

<dd>
<p>Indicates that the video output device connects to an external display device through composite video connectors.</p>
</dd>

### -field D3DKMDT_VOT_COMPONENT_VIDEO

<dd>
<p>Indicates that the video output device connects to an external display device through component video connectors.</p>
</dd>

### -field D3DKMDT_VOT_DVI

<dd>
<p>Indicates that the video output device connects to an external display device through a Digital Video Interface (DVI) connector.</p>
</dd>

### -field D3DKMDT_VOT_HDMI

<dd>
<p>Indicates that the video output device connects to an external display device through an High-Definition Multimedia Interface (HDMI) connector.</p>
</dd>

### -field D3DKMDT_VOT_LVDS

<dd>
<p>Indicates that the video output device connects to an external display device through an Low Voltage Differential Swing (LVDS) or Mobile Industry Processor Interface (MIPI) Digital Serial Interface (DSI) connector.</p>
</dd>

### -field D3DKMDT_VOT_D_JPN

<dd>
<p>Indicates that the video output device connects to an external display device through a D-Jpn connector. </p>
</dd>

### -field D3DKMDT_VOT_SDI

<dd>
<p>Indicates that the video output device connects to an external display device through an SDI connector. </p>
</dd>

### -field D3DKMDT_VOT_DISPLAYPORT_EXTERNAL

<dd>
<p>Indicates that the connector type is an external display port. </p>
</dd>

### -field D3DKMDT_VOT_DISPLAYPORT_EMBEDDED

<dd>
<p>Indicates that the connector type is an embedded display port. </p>
</dd>

### -field D3DKMDT_VOT_UDI_EXTERNAL

<dd>
<p>Indicates that the connector type is an external Unified Display Interface (UDI). </p>
</dd>

### -field D3DKMDT_VOT_UDI_EMBEDDED

<dd>
<p>Indicates that the connector type is an embedded UDI. </p>
</dd>

### -field D3DKMDT_VOT_SDTVDONGLE

<dd>
<p>Indicates that the video output device connects to an external display device through a dongle cable that supports SDTV. </p>
</dd>

### -field D3DKMDT_VOT_MIRACAST

<dd>
<p>Indicates that the video output device connects to an external display device wirelessly through a Miracast connected session. For more info, see <a href="https://msdn.microsoft.com/1645E14A-EC4A-4EB8-9AFA-6DF0466D2B1A">Wireless displays (Miracast)</a>.</p>
<p>Supported starting with Windows 8.1.</p>
</dd>

### -field D3DKMDT_VOT_INTERNAL

<dd>
<p>Indicates that the video output device connects internally to a display device (for example, the internal connection in a laptop computer).</p>
<p>This constant value is not a bit-field value. Instead, it's a standalone video output type.</p>
</dd>

### -field D3DKMDT_VOT_SVIDEO_4PIN

<dd>
<p>Indicates that the video output device connects to an external display device through a 4-pin S-video connector.</p>
</dd>

### -field D3DKMDT_VOT_SVIDEO_7PIN

<dd>
<p>Indicates that the video output device connects to an external display device through a 7-pin S-video connector.</p>
</dd>

### -field D3DKMDT_VOT_RF

<dd>
<p>Indicates that the video output device connects to an external display device through an RF connector.</p>
</dd>

### -field D3DKMDT_VOT_RCA_3COMPONENT

<dd>
<p>Indicates that the video output device connects to an external display device through a set of three RCA connectors.</p>
</dd>

### -field D3DKMDT_VOT_BNC

<dd>
<p>Indicates that the video output device connects to an external display device through a BNC connector.</p>
</dd>
</dl>

## -remarks
<p>The <b>ChildCapabilities</b> member of a <a href="..\dispmprt\ns-dispmprt--dxgk-child-descriptor.md">DXGK_CHILD_DESCRIPTOR</a> structure is a <a href="..\dispmprt\ns-dispmprt--dxgk-child-capabilities.md">DXGK_CHILD_CAPABILITIES</a> structure. The <b>Type.VideoOutput</b> member of a DXGK_CHILD_CAPABILITIES structure is a <a href="..\dispmprt\ns-dispmprt--dxgk-video-output-capabilities.md">DXGK_VIDEO_OUTPUT_CAPABILITIES</a> structure. The <b>InterfaceTechnology</b> member of a DXGK_VIDEO_OUTPUT_CAPABILITIES structure is a D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY value.</p>

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
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgkddiquerychildrelations">DxgkDdiQueryChildRelations</a>
</dt>
<dt>
<a href="..\dispmprt\ns-dispmprt--dxgk-video-output-capabilities.md">DXGK_VIDEO_OUTPUT_CAPABILITIES</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_VIDEO_OUTPUT_TECHNOLOGY enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>