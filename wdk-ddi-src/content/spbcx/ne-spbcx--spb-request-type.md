---
UID: NE.spbcx._SPB_REQUEST_TYPE
title: SPB_REQUEST_TYPE
author: windows-driver-content
description: The SPB_REQUEST_TYPE enumeration specifies the type of SPB operation that a client is requesting.
old-location: spb\spb_request_type.htm
old-project: SPB
ms.assetid: B3C2505E-A2B6-4D79-B8B7-9D1B53AA5B56
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: SPB_TRANSFER_LIST,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: spbcx.h
req.include-header: Spb.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SPB_REQUEST_TYPE
req.alt-loc: spbcx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at PASSIVE_LEVEL.
req.iface: 
req.product: Windows 10 or later.
---

# SPB_REQUEST_TYPE enumeration



## -description
<p>The <b>SPB_REQUEST_TYPE</b> enumeration specifies the type of SPB operation that a client is requesting.</p>


## -syntax

````
typedef enum  { 
  SpbRequestTypeUndefined         = 0,
  SpbRequestTypeRead,
  SpbRequestTypeWrite,
  SpbRequestTypeSequence,
  SpbRequestTypeLockController,
  SpbRequestTypeUnlockController,
  SpbRequestTypeLockConnection,
  SpbRequestTypeUnlockConnection,
  SpbRequestTypeOther,
  SpbRequestTypeMax
} SPB_REQUEST_TYPE;
````


## -enum-fields
<dl>

### -field SpbRequestTypeUndefined

<dd>
<p>For internal use only.</p>
</dd>

### -field SpbRequestTypeRead

<dd>
<p> A read operation. The transfer direction for read data is from the target device to the client (peripheral driver).  Your SPB controller driver will  see requests of this type only  if it registers an <a href="https://msdn.microsoft.com/2BC0E6E7-7EE1-487A-9276-AE8EBB3FFD43">EvtSpbControllerIoRead</a> callback function.</p>
</dd>

### -field SpbRequestTypeWrite

<dd>
<p>A write operation. The transfer direction for write data is from the client to the target device.  Your SPB controller driver receives requests of this type only if it registers an <a href="https://msdn.microsoft.com/D97C3A17-309E-4364-8DFB-9073901D332E">EvtSpbControllerIoWrite</a> callback function.</p>
</dd>

### -field SpbRequestTypeSequence

<dd>
<p>A sequence of transfer (read and write) operations combined into a single request. Your SPB controller driver receives requests of this type only if it registers an <a href="https://msdn.microsoft.com/C56F1528-5FDA-4BC9-AB32-7882FB0F7713">EvtSpbControllerIoSequence</a> callback function.  Otherwise, the SPB framework extension (SpbCx) will convert an I/O transfer sequence into a series of I/O requests of type <b>SpbRequestTypeRead</b> and <b>SpbRequestTypeWrite</b>, and send these requests to the SPB controller driver's <i>EvtSpbControllerIoRead</i> and <i>EvtSpbControllerIoWrite</i> callback functions.</p>
</dd>

### -field SpbRequestTypeLockController

<dd>
<p>A request to lock the controller exclusively for bus transfers to or from the specified target device.  Your SPB controller driver receives requests of this type only if it registers an <a href="https://msdn.microsoft.com/E08674F1-CE63-464B-9C70-96F93C574753">EvtSpbControllerLock</a> callback function.</p>
</dd>

### -field SpbRequestTypeUnlockController

<dd>
<p>A request to unlock the controller for the specified target device.  Your SPB controller driver receives requests of this type through its <a href="https://msdn.microsoft.com/4EB36115-2783-4FD5-9CEE-1F7C971C334D">EvtSpbControllerUnlock</a> callback function.</p>
</dd>

### -field SpbRequestTypeLockConnection

<dd>
<p>A request to lock the specified target device for exclusive use by a client.  This request is handled entirely by SpbCx. Your SPB controller driver performs no processing for requests of this type. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj819324">IOCTL_SPB_LOCK_CONNECTION</a>.</p>
</dd>

### -field SpbRequestTypeUnlockConnection

<dd>
<p>A request to unlock the specified target device.  This request is handled entirely by SpbCx. Your SPB controller driver performs no processing for requests of this type. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj819325">IOCTL_SPB_UNLOCK_CONNECTION</a>.</p>
</dd>

### -field SpbRequestTypeOther

<dd>
<p>An unknown I/O control (IOCTL) request sent by a client (peripheral driver) to a target device on the bus.  Call the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a> method to retrieve the parameters for this request; for this call, use the SPBREQUEST handle for the <i>Request</i> parameter. Your SPB controller driver receives requests of this type only if it registers an <a href="https://msdn.microsoft.com/5A4BC061-4703-4C46-BD5D-A891F3DA8842">EvtSpbControllerIoOther</a> callback function.  Otherwise, SpbCx rejects unknown IOCTL requests.</p>
</dd>

### -field SpbRequestTypeMax

<dd>
<p>For internal use only.</p>
</dd>
</dl>

## -remarks
<p>The <a href="https://msdn.microsoft.com/91A5C504-7072-4B64-86F1-2BDE616CCA31">SPB_REQUEST_PARAMETERS</a> structure contains an <b>SPB_REQUEST_TYPE</b> enumeration value.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Spbcx.h (include Spb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/E08674F1-CE63-464B-9C70-96F93C574753">EvtSpbControllerLock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/5A4BC061-4703-4C46-BD5D-A891F3DA8842">EvtSpbControllerIoOther</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/2BC0E6E7-7EE1-487A-9276-AE8EBB3FFD43">EvtSpbControllerIoRead</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/C56F1528-5FDA-4BC9-AB32-7882FB0F7713">EvtSpbControllerIoSequence</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/D97C3A17-309E-4364-8DFB-9073901D332E">EvtSpbControllerIoWrite</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/4EB36115-2783-4FD5-9CEE-1F7C971C334D">EvtSpbControllerUnlock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj819324">IOCTL_SPB_LOCK_CONNECTION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj819325">IOCTL_SPB_UNLOCK_CONNECTION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/91A5C504-7072-4B64-86F1-2BDE616CCA31">SPB_REQUEST_PARAMETERS</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SPB_REQUEST_TYPE enumeration%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>