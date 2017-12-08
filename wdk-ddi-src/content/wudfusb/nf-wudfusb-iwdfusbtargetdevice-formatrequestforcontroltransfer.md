---
UID: NF.wudfusb.IWDFUsbTargetDevice.FormatRequestForControlTransfer
title: IWDFUsbTargetDevice::FormatRequestForControlTransfer
author: windows-driver-content
description: The FormatRequestForControlTransfer method formats an I/O request object for a USB control transfer.
old-location: wdf\iwdfusbtargetdevice_formatrequestforcontroltransfer.htm
old-project: wdf
ms.assetid: 7f75fbaa-06e8-4c4d-b1ee-c89a55889295
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IWDFUsbTargetDevice, FormatRequestForControlTransfer, IWDFUsbTargetDevice::FormatRequestForControlTransfer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfusb.h
req.include-header: Wudfusb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFUsbTargetDevice.FormatRequestForControlTransfer
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
req.iface: IWDFUsbTargetDevice
req.product: Windows 10 or later.
---

# IWDFUsbTargetDevice::FormatRequestForControlTransfer method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>The <b>FormatRequestForControlTransfer</b> method formats an I/O request object for a USB control transfer.</p>


## -syntax

````
HRESULT FormatRequestForControlTransfer(
  [in]           IWDFIoRequest        *pRequest,
  [in]           PWINUSB_SETUP_PACKET SetupPacket,
  [in, optional] IWDFMemory           *pMemory,
  [in, optional] PWDFMEMORY_OFFSET    TransferOffset
);
````


## -parameters
<dl>

### -param pRequest [in]

<dd>
<p>A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface for the request object to format. </p>
</dd>

### -param SetupPacket [in]

<dd>
<p>A pointer to a <a href="buses.winusb_setup_packet">WINUSB_SETUP_PACKET</a> for the control transfer.</p>
</dd>

### -param pMemory [in, optional]

<dd>
<p>A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface that is used to access the buffer that is used for the control transfer. This parameter is optional.</p>
</dd>

### -param TransferOffset [in, optional]

<dd>
<p>A pointer to a <a href="..\wudfddi_types\ns-wudfddi-types--wdfmemory-offset.md">WDFMEMORY_OFFSET</a> structure that describes the memory offset that is used for the control transfer. This parameter is optional.</p>
</dd>
</dl>

## -returns
<p><b>FormatRequestForControlTransfer</b> returns one of the following values: </p><dl>
<dt><b>S_OK </b></dt>
</dl><p>
<a href="wdf.iwdfusbtargetdevice_formatrequestforcontroltransfer">FormatRequestForControlTransfer</a> successfully formatted an I/O request object. </p><dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl><p>
<a href="wdf.iwdfusbtargetdevice_formatrequestforcontroltransfer">FormatRequestForControlTransfer</a> encountered an allocation failure.</p><dl>
<dt><b>E_INVALIDARG </b></dt>
</dl><p>The memory offset that the <i>TransferOffset</i> parameter specified was invalid.</p>

<p> </p>

## -remarks
<p>After a UMDF driver calls <b>FormatRequestForControlTransfer</b> to format an I/O request for a control transfer operation, the framework can subsequently send the request to the I/O target.</p>

<p>The following code example is taken from the <a href="http://go.microsoft.com/fwlink/p/?LinkID=256209">wdf_osrfx2_lab</a> sample in the WDK.</p>

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
<p>End of support</p>
</th>
<td width="70%">
<p>Unavailable in UMDF 2.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>1.5</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wudfusb.h (include Wudfusb.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetdevice.md">IWDFUsbTargetDevice</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>
</dt>
<dt>
<a href="..\wudfddi_types\ns-wudfddi-types--wdfmemory-offset.md">WDFMEMORY_OFFSET</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetDevice::FormatRequestForControlTransfer method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>