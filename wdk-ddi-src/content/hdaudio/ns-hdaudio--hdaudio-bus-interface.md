---
UID: NS.hdaudio._HDAUDIO_BUS_INTERFACE
title: HDAUDIO_BUS_INTERFACE
author: windows-driver-content
description: The HDAUDIO_BUS_INTERFACE structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE version of the HD Audio DDI. Another variant of this DDI is specified by the HDAUDIO_BUS_INTERFACE_BDL structure.
old-location: audio\hdaudio_bus_interface.htm
old-project: audio
ms.assetid: 6b3bc5ce-05d2-45e0-91d8-6bb34e58777f
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: HDAUDIO_BUS_INTERFACE, HDAUDIO_BUS_INTERFACE, *PHDAUDIO_BUS_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HDAUDIO_BUS_INTERFACE
req.alt-loc: hdaudio.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL.
req.iface: 
---

# HDAUDIO_BUS_INTERFACE structure



## -description
<p>The HDAUDIO_BUS_INTERFACE structure specifies the information that a client requires to call the routines in the HDAUDIO_BUS_INTERFACE version of the HD Audio DDI. Another variant of this DDI is specified by the <a href="..\hdaudio\ns-hdaudio--hdaudio-bus-interface-bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a> structure.</p>


## -syntax

````
typedef struct _HDAUDIO_BUS_INTERFACE {
  USHORT                       Size;
  USHORT                       Version;
  PVOID                        Context;
  PINTERFACE_REFERENCE         InterfaceReference;
  PINTERFACE_DEREFERENCE       InterfaceDereference;
  PTRANSFER_CODEC_VERBS        TransferCodecVerbs;
  PALLOCATE_CAPTURE_DMA_ENGINE AllocateCaptureDmaEngine;
  PALLOCATE_RENDER_DMA_ENGINE  AllocateRenderDmaEngine;
  PCHANGE_BANDWIDTH_ALLOCATION ChangeBandwidthAllocation;
  PALLOCATE_DMA_BUFFER         AllocateDmaBuffer;
  PFREE_DMA_BUFFER             FreeDmaBuffer;
  PFREE_DMA_ENGINE             FreeDmaEngine;
  PSET_DMA_ENGINE_STATE        SetDmaEngineState;
  PGET_WALL_CLOCK_REGISTER     GetWallClockRegister;
  PGET_LINK_POSITION_REGISTER  GetLinkPositionRegister;
  PREGISTER_EVENT_CALLBACK     RegisterEventCallback;
  PUNREGISTER_EVENT_CALLBACK   UnregisterEventCallback;
  PGET_DEVICE_INFORMATION      GetDeviceInformation;
  PGET_RESOURCE_INFORMATION    GetResourceInformation;
} HDAUDIO_BUS_INTERFACE, *PHDAUDIO_BUS_INTERFACE;
````


## -struct-fields
<dl>

### -field Size

<dd>
<p>Specifies the size in bytes of the HDAUDIO_BUS_INTERFACE structure.</p>
</dd>

### -field Version

<dd>
<p>Specifies the version of the baseline HD Audio DDI.</p>
</dd>

### -field Context

<dd>
<p>Pointer to interface-specific context information.</p>
</dd>

### -field InterfaceReference

<dd>
<p>Pointer to a driver-supplied routine that increments the interface's reference count.</p>
</dd>

### -field InterfaceDereference

<dd>
<p>Pointer to a driver-supplied routine that decrements the interface's reference count.</p>
</dd>

### -field TransferCodecVerbs

<dd>
<p>Function pointer to the <a href="..\hdaudio\nc-hdaudio-ptransfer-codec-verbs.md">TransferCodecVerbs</a> routine.</p>
</dd>

### -field AllocateCaptureDmaEngine

<dd>
<p>Function pointer to the <a href="..\hdaudio\nc-hdaudio-pallocate-capture-dma-engine.md">AllocateCaptureDmaEngine</a> routine.</p>
</dd>

### -field AllocateRenderDmaEngine

<dd>
<p>Function pointer to the <a href="..\hdaudio\nc-hdaudio-pallocate-render-dma-engine.md">AllocateRenderDmaEngine</a> routine.</p>
</dd>

### -field ChangeBandwidthAllocation

<dd>
<p>Function pointer to the <a href="..\hdaudio\nc-hdaudio-pchange-bandwidth-allocation.md">ChangeBandwidthAllocation</a> routine.</p>
</dd>

### -field AllocateDmaBuffer

<dd>
<p>Function pointer to the <a href="..\hdaudio\nc-hdaudio-pallocate-dma-buffer.md">AllocateDmaBuffer</a> routine.</p>
</dd>

### -field FreeDmaBuffer

<dd>
<p>Function pointer to the <a href="..\hdaudio\nc-hdaudio-pfree-dma-buffer.md">FreeDmaBuffer</a> routine.</p>
</dd>

### -field FreeDmaEngine

<dd>
<p>Function pointer to the <a href="..\hdaudio\nc-hdaudio-pfree-dma-engine.md">FreeDmaEngine</a> routine.</p>
</dd>

### -field SetDmaEngineState

<dd>
<p>Function pointer to the <a href="..\hdaudio\nc-hdaudio-pset-dma-engine-state.md">SetDmaEngineState</a> routine.</p>
</dd>

### -field GetWallClockRegister

<dd>
<p>Function pointer to the <a href="..\hdaudio\nc-hdaudio-pget-wall-clock-register.md">GetWallClockRegister</a> routine.</p>
</dd>

### -field GetLinkPositionRegister

<dd>
<p>Function pointer to the <a href="..\hdaudio\nc-hdaudio-pget-link-position-register.md">GetLinkPositionRegister</a> routine.</p>
</dd>

### -field RegisterEventCallback

<dd>
<p>Function pointer to the <a href="..\hdaudio\nc-hdaudio-pregister-event-callback.md">RegisterEventCallback</a> routine.</p>
</dd>

### -field UnregisterEventCallback

<dd>
<p>Function pointer to the <a href="..\hdaudio\nc-hdaudio-punregister-event-callback.md">UnregisterEventCallback</a> routine.</p>
</dd>

### -field GetDeviceInformation

<dd>
<p>Function pointer to the <a href="..\hdaudio\nc-hdaudio-pget-device-information.md">GetDeviceInformation</a> routine.</p>
</dd>

### -field GetResourceInformation

<dd>
<p>Function pointer to the <a href="..\hdaudio\nc-hdaudio-pget-resource-information.md">GetResourceInformation</a> routine.</p>
</dd>
</dl>

## -remarks
<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> IOCTL uses this structure to provide interface information to a client that is querying the HD Audio bus driver for the HD Audio DDI. Another variant of this DDI is specified by the HDAUDIO_BUS_INTERFACE_BDL structure.</p>

<p>The HDAUDIO_BUS_INTERFACE and HDAUDIO_BUS_INTERFACE_BDL structures are similar but have the following differences:</p>

<p>HDAUDIO_BUS_INTERFACE has two members, <b>AllocateDmaBuffer</b> and <b>FreeDmaBuffer</b>, that are not present in HDAUDIO_BUS_INTERFACE_BDL.</p>

<p>HDAUDIO_BUS_INTERFACE_BDL has three members, <a href="..\hdaudio\nc-hdaudio-pallocate-contiguous-dma-buffer.md">AllocateContiguousDmaBuffer</a>, <a href="..\hdaudio\nc-hdaudio-pfree-contiguous-dma-buffer.md">FreeContiguousDmaBuffer</a>, and <a href="..\hdaudio\nc-hdaudio-psetup-dma-engine-with-bdl.md">SetupDmaEngineWithBdl</a>, that are not present in HDAUDIO_BUS_INTERFACE.</p>

<p>For more information, see <a href="https://msdn.microsoft.com/e24071d3-9021-40c0-907a-91ada8a1306b">Differences Between the HD Audio DDI Versions</a>.</p>

<p>The names and definitions of the first five members (<b>Size</b>, <b>Version</b>, <b>Context</b>, <b>InterfaceReference</b>, and <b>InterfaceDereference</b>) are the same as in the <a href="..\wdm\ns-wdm--interface.md">INTERFACE</a> structure. The remaining members are specific to the baseline HD Audio DDI and specify function pointers to the routines in the DDI. For more information, see <a href="https://msdn.microsoft.com/78667254-62a6-41fe-af36-43dbdea63aa8">Obtaining an HDAUDIO_BUS_INTERFACE DDI Object</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hdaudio.h (include Hdaudio.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hdaudio\nc-hdaudio-ptransfer-codec-verbs.md">TransferCodecVerbs</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate-capture-dma-engine.md">AllocateCaptureDmaEngine</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate-render-dma-engine.md">AllocateRenderDmaEngine</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pchange-bandwidth-allocation.md">ChangeBandwidthAllocation</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pallocate-dma-buffer.md">AllocateDmaBuffer</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pfree-dma-buffer.md">FreeDmaBuffer</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pfree-dma-engine.md">FreeDmaEngine</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pset-dma-engine-state.md">SetDmaEngineState</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pget-wall-clock-register.md">GetWallClockRegister</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pget-link-position-register.md">GetLinkPositionRegister</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pregister-event-callback.md">RegisterEventCallback</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-punregister-event-callback.md">UnregisterEventCallback</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pget-device-information.md">GetDeviceInformation</a>
</dt>
<dt>
<a href="..\hdaudio\nc-hdaudio-pget-resource-information.md">GetResourceInformation</a>
</dt>
<dt>
<a href="..\hdaudio\ns-hdaudio--hdaudio-bus-interface-bdl.md">HDAUDIO_BUS_INTERFACE_BDL</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20HDAUDIO_BUS_INTERFACE structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>