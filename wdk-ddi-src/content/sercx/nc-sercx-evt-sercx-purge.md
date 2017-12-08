---
UID: NC.sercx.EVT_SERCX_PURGE
title: EVT_SERCX_PURGE
author: windows-driver-content
description: The EvtSerCxPurge event callback function is called by the serial framework extension (SerCx) to purge the serial controller's hardware buffers.
old-location: serports\evtsercxpurge.htm
old-project: serports
ms.assetid: 036D9AAC-C740-4108-B952-0A4F91585488
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: SENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EvtSerCxPurge
req.alt-loc: 1.0\Sercx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at IRQL <= DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# EVT_SERCX_PURGE callback



## -description
<p>The <i>EvtSerCxPurge</i> event callback function is called by the serial framework extension (SerCx) to purge the serial controller's hardware buffers.</p>


## -prototype

````
EVT_SERCX_PURGE EvtSerCxPurge;

NTSTATUS EvtSerCxPurge(
  _In_ WDFDEVICE Device,
  _In_ ULONG     PurgeMask
)
{ ... }
````


## -parameters
<dl>

### -param Device [in]

<dd>
<p>A WDFDEVICE handle to the framework device object that represents the serial controller.</p>
</dd>

### -param PurgeMask [in]

<dd>
<p>A set of flags that describe the hardware buffers that are to be purged.  Currently, no flags are defined for purge operations that are performed by the serial controller. For more information, see Remarks.</p>
</dd>
</dl>

## -returns
<p>The <i>EvtSerCxPurge</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.</p>

## -remarks
<p>The serial controller driver implements this callback function. SerCx calls this function when a client (application or peripheral driver) sends an <a href="..\ntddser\ni-ntddser-ioctl-serial-purge.md">IOCTL_SERIAL_PURGE</a> control request that requires hardware buffers managed by the serial controller to be purged.</p>

<p>SerCx performs the purge operations that are designated by the flags listed in the following table.</p>

<p>The <i>EvtSerCxPurge</i> function will never receive a purge request that contains any of the flags in this table. The SERIAL_PURGE_<i>XXX</i> flags are defined in the Ntddser.h header file.</p>

<p>Currently, no SERIAL_PURGE_<i>XXX</i> flags are defined to designate purge operations that are performed by the serial controller driver, and the serial controller driver should perform no purge operations in response to a <i>EvtSerCxPurge</i> call.</p>

<p>If the <b>IOCTL_SERIAL_PURGE</b> control request requires pending read or write requests to be canceled, SerCx cancels these requests before it calls the <i>EvtSerCxPurge</i> function.</p>

<p>To register an <i>EvtSerCxPurge</i> callback function, the controller driver calls the <a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a> method during the <a href="..\wdfdriver\nc-wdfdriver-evt-wdf-driver-device-add.md">EvtDriverDeviceAdd</a> callback.</p>

<p>The function type for this callback is declared in Sercx.h, as follows.</p>

<p>To define an <i>EvtSerCxPurge</i> callback function that is named <code>MyEvtSerCxPurge</code>, you must first provide a function declaration that <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.</p>

<p>Then, implement your callback function as follows.</p>

<p>For more information about SDV requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions Using Function Role Types for KMDF Drivers</a>.</p>

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
<p>Available starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>1.0\Sercx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Called at IRQL &lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt-wdf-driver-device-add.md">EvtDriverDeviceAdd</a>
</dt>
<dt>
<a href="..\ntddser\ni-ntddser-ioctl-serial-purge.md">IOCTL_SERIAL_PURGE</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX_PURGE callback function%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>