---
UID: NF.hidsdi.HidD_GetFeature
title: HidD_GetFeature
author: windows-driver-content
description: The HidD_GetFeature routine returns a feature report from a specified top-level collection.
old-location: hid\hidd_getfeature.htm
old-project: hid
ms.assetid: e6a01367-981a-4b44-97a8-4cb37f9753fc
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: HidD_GetFeature
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hidsdi.h
req.include-header: Hidsdi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HidD_GetFeature
req.alt-loc: Hid.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hid.lib
req.dll: Hid.dll
req.irql: 
req.iface: 
---

# HidD_GetFeature function



## -description
<p>The <b>HidD_GetFeature</b> routine returns a feature report from a specified <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.</p>


## -syntax

````
BOOLEAN __stdcall HidD_GetFeature(
  _In_  HANDLE HidDeviceObject,
  _Out_ PVOID  ReportBuffer,
  _In_  ULONG  ReportBufferLength
);
````


## -parameters
<dl>

### -param HidDeviceObject [in]

<dd>
<p>Specifies an open handle to a top-level collection.</p>
</dd>

### -param ReportBuffer [out]

<dd>
<p>Pointer to a caller-allocated HID report buffer that the caller uses to specify a report ID. <b>HidD_GetFeature</b> uses <i>ReportBuffer</i> to return the specified feature report. </p>
<p>For more information about this parameter, see the Remarks section.</p>
</dd>

### -param ReportBufferLength [in]

<dd>
<p>Specifies the size, in bytes, of the report buffer. The report buffer must be large enough to hold the feature report -- excluding its report ID, if report IDs are used -- plus one additional byte that specifies a nonzero report ID or zero.</p>
</dd>
</dl>

## -returns
<p>If <b>HidD_GetFeature</b> succeeds, it returns <b>TRUE</b>; otherwise, it returns <b>FALSE</b>.</p>

## -remarks
<p>Before it calls the <b>HidD_GetFeature</b> routine, the caller must do the following:</p>

<p>If the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> includes report IDs, the caller must set the first byte of the <i>ReportBuffer</i> parameter to a nonzero report ID.</p>

<p>If the <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> does not include report IDs, the caller must set the first byte of the <i>ReportBuffer</i> parameter to zero.

</p>

<p>The feature report is returned in the <i>ReportBuffer</i>  parameter. Depending on the report ID, the caller parses the report by calling one of the following functions:</p>

<p>For an example of how to parse a HID report, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=256119">HClient</a> sample application. This sample is located in the MSDN Code Gallery.</p>

<p>Only user-mode applications can call <b>HidD_GetFeature</b>. Kernel-mode drivers can use an <a href="..\hidclass\ni-hidclass-ioctl-hid-get-feature.md">IOCTL_HID_GET_FEATURE</a> request.</p>

<p>For more information, see the following topics:</p>

<p>
<a href="https://msdn.microsoft.com/b6312dce-39af-4fff-b17d-4a50b9ab823b">Obtaining HID Reports</a>
</p>

<p>
<a href="https://msdn.microsoft.com/10f8c3a1-ad60-4c99-a425-fa8c9a3be0e1">Interpreting HID Reports</a>
</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 2000 and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hidsdi.h (include Hidsdi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Hid.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Hid.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hidsdi\nf-hidsdi-hidd-setfeature.md">HidD_SetFeature</a>
</dt>
<dt>
<a href="..\hidsdi\nf-hidsdi-hidd-getinputreport.md">HidD_GetInputReport</a>
</dt>
<dt>
<a href="..\hidsdi\nf-hidsdi-hidd-setoutputreport.md">HidD_SetOutputReport</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl-hid-get-feature.md">IOCTL_HID_GET_FEATURE</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl-hid-get-input-report.md">IOCTL_HID_GET_INPUT_REPORT</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl-hid-set-feature.md">IOCTL_HID_SET_FEATURE</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl-hid-set-output-report.md">IOCTL_HID_SET_OUTPUT_REPORT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidD_GetFeature routine%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>