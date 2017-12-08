---
UID: NS.ntddser._SERIAL_LINE_CONTROL
title: SERIAL_LINE_CONTROL
author: windows-driver-content
description: The SERIAL_LINE_CONTROL structure describes the control settings for the serial line.
old-location: serports\serial_line_control.htm
old-project: serports
ms.assetid: 2D11187E-B21B-4211-BAC0-248B93BAB6D5
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: SERIAL_LINE_CONTROL, SERIAL_LINE_CONTROL, *PSERIAL_LINE_CONTROL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddser.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SERIAL_LINE_CONTROL
req.alt-loc: Ntddser.h
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

# SERIAL_LINE_CONTROL structure



## -description
<p>The <b>SERIAL_LINE_CONTROL</b> structure describes the control settings for the serial line.</p>


## -syntax

````
typedef struct _SERIAL_LINE_CONTROL {
  UCHAR StopBits;
  UCHAR Parity;
  UCHAR WordLength;
} SERIAL_LINE_CONTROL, *PSERIAL_LINE_CONTROL;
````


## -struct-fields
<dl>

### -field StopBits

<dd>
<p>The number of stop bits used at the end of each character that is transmitted or received. This member is set to one of the following values.</p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>STOP_BIT_1</td>
<td>One stop bit.</td>
</tr>
<tr>
<td>STOP_BITS_1_5</td>
<td>One and a half stop bits.</td>
</tr>
<tr>
<td>STOP_BITS_2</td>
<td>Two stop bits. Not valid if <b>WordLength</b> = 5.</td>
</tr>
</table>
<p> </p>
</dd>

### -field Parity

<dd>
<p>The type of parity checking used for each character that is transmitted or received. This member is set to one of the following values.</p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>NO_PARITY</td>
<td>No parity bit is used.</td>
</tr>
<tr>
<td>ODD_PARITY</td>
<td>Odd parity is used. The parity bit is 0 if the number of 1s in the character value is odd. Otherwise, the parity bit is 1.</td>
</tr>
<tr>
<td>EVEN_PARITY</td>
<td>Even parity is used. The parity bit is 0 if the number of 1s in the character value is even. Otherwise, the parity bit is 1.</td>
</tr>
<tr>
<td>MARK_PARITY</td>
<td>The parity bit is always set to 1.</td>
</tr>
<tr>
<td>SPACE_PARITY</td>
<td>The parity bit is always set to 0.</td>
</tr>
</table>
<p> </p>
</dd>

### -field WordLength

<dd>
<p>Data bits per character. This member indicates the number of data bits in each character value that is transmitted or received, and does not include parity bits or stop bits. <b>WordLength</b> values in the range 5 to 8 are typically supported.</p>
</dd>
</dl>

## -remarks
<p>This structure is used by the <a href="..\ntddser\ni-ntddser-ioctl-serial-get-line-control.md">IOCTL_SERIAL_GET_LINE_CONTROL</a> and <a href="..\ntddser\ni-ntddser-ioctl-serial-set-line-control.md">IOCTL_SERIAL_SET_LINE_CONTROL</a> requests.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddser.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddser\ni-ntddser-ioctl-serial-get-line-control.md">IOCTL_SERIAL_GET_LINE_CONTROL</a>
</dt>
<dt>
<a href="..\ntddser\ni-ntddser-ioctl-serial-set-line-control.md">IOCTL_SERIAL_SET_LINE_CONTROL</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERIAL_LINE_CONTROL structure%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>