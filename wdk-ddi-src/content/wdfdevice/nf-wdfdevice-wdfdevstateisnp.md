---
UID: NF.wdfdevice.WdfDevStateIsNP
title: WdfDevStateIsNP function
author: windows-driver-content
description: The WdfDevStateIsNP method returns a Boolean value that indicates whether a specified power state or power policy state is a nonpageable state.
old-location: wdf\wdfdevstateisnp.htm
old-project: wdf
ms.assetid: 49584600-e470-4be8-9111-3e890a9fedfd
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfDevStateIsNP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfDevStateIsNP
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level
req.product: Windows 10 or later.
---

# WdfDevStateIsNP function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WdfDevStateIsNP</b> method returns a Boolean value that indicates whether a specified power state or power policy state is a <a href="wdf.creating_pageable_code_in_a_kmdf_driver">nonpageable</a> state. 


## -syntax

````
BOOLEAN WdfDevStateIsNP(
  _In_ ULONG State
);
````


## -parameters

### -param State [in]

A <a href="wdf.wdf_device_power_state">WDF_DEVICE_POWER_STATE</a>-typed enumerator or a <a href="wdf.wdf_device_power_policy_state">WDF_DEVICE_POWER_POLICY_STATE</a>-typed enumerator.

## -returns
If the calling driver is currently nonpageable, the <b>WdfDevStateIsNP</b> method returns <b>TRUE</b>. Otherwise, the method returns <b>FALSE</b>.

## -remarks
To obtain the current state of the framework's power state machine, a driver can call <a href="wdf.wdfdevicegetdevicepowerstate">WdfDeviceGetDevicePowerState</a> from within a PnP or power callback function. To obtain the current state of the framework's power policy state machine, a driver can call <a href="wdf.wdfdevicegetdevicepowerpolicystate">WdfDeviceGetDevicePowerPolicyState</a> from within a power policy callback function. After the driver has called <b>WdfDeviceGetDevicePowerState</b> or <b>WdfDeviceGetDevicePowerPolicyState</b>, it can call <b>WdfDevStateIsNP</b> to determine if the returned state represents a pageable or nonpageable state. If the framework's state machine is in a nonpageable state, the driver is not pageable and must not perform any operations that might cause the operating system to access the paging file. Such operations include accessing files, the registry, or paged pool. 

The following code example sets the <b>nonpageable</b> value to <b>TRUE</b> if the framework's power state machine is currently in a nonpageable state.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
Any level
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfdeviceinitsetpowerpageable">WdfDeviceInitSetPowerPageable</a>
</dt>
<dt>
<a href="wdf.wdfdeviceinitsetpowernotpageable">WdfDeviceInitSetPowerNotPageable</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDevStateIsNP method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>