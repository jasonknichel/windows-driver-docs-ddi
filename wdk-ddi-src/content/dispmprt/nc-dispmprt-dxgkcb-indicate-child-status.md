---
UID: NC.dispmprt.DXGKCB_INDICATE_CHILD_STATUS
title: DXGKCB_INDICATE_CHILD_STATUS
author: windows-driver-content
description: The DxgkCbIndicateChildStatus function records the current status of a specified child device of a display adapter.
old-location: display\dxgkcbindicatechildstatus.htm
old-project: display
ms.assetid: 780a8867-bba1-4b1b-a941-b55bfe087b7b
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SYMBOL_INFO_EX, SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkCbIndicateChildStatus
req.alt-loc: dispmprt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.iface: IDebugSystemObjects4
---

# DXGKCB_INDICATE_CHILD_STATUS callback



## -description
<p>The <b>DxgkCbIndicateChildStatus</b> function records the current status of a specified child device of a display adapter.</p>


## -prototype

````
DXGKCB_INDICATE_CHILD_STATUS DxgkCbIndicateChildStatus;

NTSTATUS DxgkCbIndicateChildStatus(
  _In_ HANDLE             DeviceHandle,
  _In_ PDXGK_CHILD_STATUS ChildStatus
)
{ ... }
````


## -parameters
<dl>

### -param DeviceHandle [in]

<dd>
<p>A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="display.dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure that was passed to <a href="display.dxgkddistartdevice">DxgkDdiStartDevice</a>.</p>
</dd>

### -param ChildStatus [in]

<dd>
<p>A pointer to a <a href="..\dispmprt\ns-dispmprt--dxgk-child-status.md">DXGK_CHILD_STATUS</a> structure that identifies the child device and describes the current status of the child device.</p>
</dd>
</dl>

## -returns
<p><b>DxgkCbIndicateChildStatus</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.</p>

## -remarks
<p>The display miniport driver's DPC for ISR calls <b>DxgkCbIndicateChildStatus</b> when the display adapter generates an interrupt for any of the following reasons:</p>

<p>An external device (typically a monitor) has been connected to one of the display adapter's child devices that has an HPD awareness value of <b>HpdAwarenessInterruptible</b>. In this case, the display miniport driver sets<i> ChildStatus</i>-&gt;<b>Type</b> to <b>StatusConnection</b> and sets<i> ChildStatus</i>.<b>HotPlug</b>.<b>Connected</b> to <b>TRUE</b>.</p>

<p>An external device (typically a monitor) has been disconnected from one of the display adapter's child devices that has an HPD awareness value of <b>HpdAwarenessInterruptible</b>. In this case, the display miniport driver sets<i> ChildStatus</i>-&gt;<b>Type</b> to <b>StatusConnection</b> and sets<i> ChildStatus</i>.<b>HotPlug</b>.<b>Connected</b> to <b>FALSE</b>.</p>

<p>The display device connected to one of its on-board child devices (that has a monitor orientation awareness value of <b>D3DKMDT_MOA_INTERRUPTIBLE</b>) has been rotated. In this case, the display miniport driver sets<i> ChildStatus</i>-&gt;<b>Type</b> to <b>StatusRotation</b> and sets<i> ChildStatus</i>.<b>Rotation</b>.<b>Angle</b> to the angle of rotation.</p>

<p>The display miniport driver's <a href="display.dxgkddinotifyacpievent">DxgkDdiNotifyAcpiEvent</a> function calls <b>DxgkCbIndicateChildStatus</b> in the following situations:</p>

<p>The lid on a portable computer gets opened. In this case, the display miniport driver sets<i> ChildStatus</i>-&gt;<b>Type</b> to <b>StatusConnection</b> and sets<i> ChildStatus</i>.<b>HotPlug</b>.<b>Connected</b> to <b>TRUE</b>.</p>

<p>The lid on a portable computer gets closed. In this case, the display miniport driver sets<i> ChildStatus</i>-&gt;<b>Type</b> to <b>StatusConnection</b> and sets<i> ChildStatus</i>.<b>HotPlug</b>.<b>Connected</b> to <b>FALSE</b>.</p>

<p>The following code example shows how to record the current status of a child device.</p>

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
<dt>Dispmprt.h (include Dispmprt.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgkddiquerychildrelations">DxgkDdiQueryChildRelations</a>
</dt>
<dt>
<a href="display.dxgkddiquerychildstatus">DxgkDdiQueryChildStatus</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_INDICATE_CHILD_STATUS callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>