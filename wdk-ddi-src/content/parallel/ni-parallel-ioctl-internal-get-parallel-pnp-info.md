---
UID: NI.parallel.IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO
title: IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO
author: windows-driver-content
description: The IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO request returns Plug and Play information about a parallel port.
old-location: parports\ioctl_internal_get_parallel_pnp_info.htm
old-project: parports
ms.assetid: 9a93d91a-e9b8-41f5-8d15-f693336bee07
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RegisterOpRegionHandler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: parallel.h
req.include-header: Parallel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO
req.alt-loc: parallel.h
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

# IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO IOCTL



## -description
<p>The <b>IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO</b> request returns Plug and Play information about a parallel port. </p>
<p>For more information, see <a href="https://msdn.microsoft.com/d8ae2296-05b6-419a-93cc-00fcb12d41fe">Obtaining Information About a ParallelPort</a>. </p>


## -ioctlparameters

### -input-buffer
<p>A <a href="..\parallel\ns-parallel--parallel-pnp-information.md">PARALLEL_PNP_INFORMATION</a> structure. </p>

### -input-buffer-length
<p>The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <a href="..\parallel\ns-parallel--parallel-pnp-information.md">PARALLEL_PNP_INFORMATION</a> structure. </p>

<p>The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <a href="..\parallel\ns-parallel--parallel-pnp-information.md">PARALLEL_PNP_INFORMATION</a> structure. </p>

### -output-buffer
<p>The <b>AssociatedIrp.SystemBuffer</b> member points to a PARALLEL_PNP_INFORMATION structure that the client allocates to output Plug and Play information.</p>

<p>The <b>AssociatedIrp.SystemBuffer</b> member points to a PARALLEL_PNP_INFORMATION structure that the client allocates to output Plug and Play information.</p>

<p>The <b>AssociatedIrp.SystemBuffer</b> member points to a PARALLEL_PNP_INFORMATION structure that the client allocates to output Plug and Play information.</p>

### -output-buffer-length
<p>The size of a PARALLEL_PNP_INFORMATION structure.</p>

<p>The size of a PARALLEL_PNP_INFORMATION structure.</p>

<p>The size of a PARALLEL_PNP_INFORMATION structure.</p>

<p>The size of a PARALLEL_PNP_INFORMATION structure.</p>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p>The <b>Information</b> member is set to zero. </p>

<p>The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to the following value:</p>

<p></p>

<p>The value of <b>Parameters.DeviceIoControl.OutputBufferLength</b> is less than the size, in bytes, of a PARALLEL_PNP_INFORMATION structure.</p>

<p>The <b>Information</b> member is set to zero. </p>

<p>The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to the following value:</p>

<p></p>

<p>The value of <b>Parameters.DeviceIoControl.OutputBufferLength</b> is less than the size, in bytes, of a PARALLEL_PNP_INFORMATION structure.</p>

<p>The <b>Information</b> member is set to zero. </p>

<p>The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to the following value:</p>

<p></p>

<p>The value of <b>Parameters.DeviceIoControl.OutputBufferLength</b> is less than the size, in bytes, of a PARALLEL_PNP_INFORMATION structure.</p>

<p>The <b>Information</b> member is set to zero. </p>

<p>The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to the following value:</p>

<p></p>

<p>The value of <b>Parameters.DeviceIoControl.OutputBufferLength</b> is less than the size, in bytes, of a PARALLEL_PNP_INFORMATION structure.</p>

<p>The <b>Information</b> member is set to zero. </p>

<p>The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports or to the following value:</p>

<p></p>

<p>The value of <b>Parameters.DeviceIoControl.OutputBufferLength</b> is less than the size, in bytes, of a PARALLEL_PNP_INFORMATION structure.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Parallel.h (include Parallel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\parallel\ni-parallel-ioctl-internal-get-more-parallel-port-info.md">IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO</a>
</dt>
<dt>
<a href="..\parallel\ni-parallel-ioctl-internal-get-parallel-port-info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a>
</dt>
<dt>
<a href="..\parallel\ns-parallel--parallel-pnp-information.md">PARALLEL_PNP_INFORMATION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO control code%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>