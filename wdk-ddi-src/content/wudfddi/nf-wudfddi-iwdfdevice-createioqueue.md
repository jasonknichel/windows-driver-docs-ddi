---
UID: NF.wudfddi.IWDFDevice.CreateIoQueue
title: IWDFDevice::CreateIoQueue
author: windows-driver-content
description: The CreateIoQueue method configures the default I/O queue that is associated with a device or creates a secondary I/O queue for the device.
old-location: wdf\iwdfdevice_createioqueue.htm
old-project: wdf
ms.assetid: 54c19d8c-59eb-44b2-b406-8fe33cdfcd63
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IWDFDevice, CreateIoQueue, IWDFDevice::CreateIoQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFDevice.CreateIoQueue
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
req.irql: <= DISPATCH_LEVEL
req.iface: IWDFDevice
req.product: Windows 10 or later.
---

# IWDFDevice::CreateIoQueue method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>The <b>CreateIoQueue</b> method configures the default I/O queue that is associated with a device or creates a secondary I/O queue for the device.</p>


## -syntax

````
HRESULT CreateIoQueue(
  [in, optional] IUnknown                   *pCallbackInterface,
  [in]           BOOL                       bDefaultQueue,
  [in]           WDF_IO_QUEUE_DISPATCH_TYPE DispatchType,
  [in]           BOOL                       bPowerManaged,
  [in]           BOOL                       bAllowZeroLengthRequests,
  [out]          IWDFIoQueue                **ppIoQueue
);
````


## -parameters
<dl>

### -param pCallbackInterface [in, optional]

<dd>
<p>A pointer to the <b>IUnknown</b> interface that the framework uses to determine the event callback functions that the driver subscribes to on the queue. These are the functions that the framework calls when the relevant events occur.</p>
<p> For UMDF versions 1.9 and later, this parameter is required for I/O queues that use the sequential or parallel <a href="wdf.configuring_dispatch_mode_for_an_i_o_queue">dispatching method</a><u>,</u> and it is optional (can be <b>NULL</b>) for I/O queues that use the manual dispatching method. For UMDF versions earlier than 1.9, this parameter is required for all dispatching methods.</p>
</dd>

### -param bDefaultQueue [in]

<dd>
<p>A BOOL value that specifies whether to configure the default I/O queue or create a secondary I/O queue for the device. <b>TRUE</b> indicates to configure the default I/O queue; <b>FALSE</b> indicates to create a secondary I/O queue.</p>
</dd>

### -param DispatchType [in]

<dd>
<p>A <a href="..\wudfddi_types\ne-wudfddi-types--wdf-io-queue-dispatch-type.md">WDF_IO_QUEUE_DISPATCH_TYPE</a>-typed value that identifies how the driver must receive requests from the I/O queue.</p>
</dd>

### -param bPowerManaged [in]

<dd>
<p>A BOOL value that specifies whether the I/O queue is power managed. <b>TRUE</b> indicates the framework automatically coordinates dispatching for the I/O queue with Plug and Play (PnP) and the power state of the device; <b>FALSE</b> indicates no automatically coordinated dispatching.</p>
</dd>

### -param bAllowZeroLengthRequests [in]

<dd>
<p>A BOOL value that specifies whether the framework puts zero-length I/O requests directly in the I/O queue for the driver to handle. <b>TRUE</b> indicates that the driver should receive read and write requests that have zero-length buffers--that is, the framework automatically puts these request types directly in the I/O queue for the driver. <b>FALSE</b> indicates that the framework completes zero-length I/O requests instead of putting them in the I/O queue.</p>
</dd>

### -param ppIoQueue [out]

<dd>
<p>A pointer to a variable that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a> interface for the newly created I/O queue object or the default I/O queue object.</p>
</dd>
</dl>

## -returns
<p><b>CreateIoQueue</b> returns one of the following values:</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The I/O queue was successfully created.</p><dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_BAD_CONFIGURATION)</b></dt>
</dl><p>The I/O queue is configured in one of the following ways:</p>

<p>The <i>DispatchType</i> parameter specifies a nonmanual queue and none of the I/O queue callback interfaces that are specified in the Remarks section are supported through the <i>pCallbackInterface</i> parameter.</p>

<p>The <i>DispatchType</i> parameter specifies a manual queue and one or more of the I/O queue callback interfaces that are specified in the Remarks section are supported through the <i>pCallbackInterface</i> parameter.</p>

<p>For more information about these configurations, see the Remarks section. </p>

<p> </p>

<p><b>CreateIoQueue</b> might also return other HRESULT values.

</p>

## -remarks
<p>The <b>IUnknown</b> interface that the driver supplies for the <i>pCallbackInterface</i> parameter can support several queue callback functions. The framework calls the <b>QueryInterface</b> method on the supplied <b>IUnknown</b> interface multiple times to retrieve the interface methods that the driver supports. When applications perform actions that are related to the methods of the supported interfaces (such as, an I/O read request), the framework calls the methods (such as, the <a href="wdf.iqueuecallbackread_onread">IQueueCallbackRead::OnRead</a> method) to notify the driver. The framework calls <b>QueryInterface</b> for the following interfaces:</p>

<p>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackcreate.md">IQueueCallbackCreate</a>
</p>

<p>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackdefaultiohandler.md">IQueueCallbackDefaultIoHandler</a>
</p>

<p>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackdeviceiocontrol.md">IQueueCallbackDeviceIoControl</a>
</p>

<p>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackread.md">IQueueCallbackRead</a>
</p>

<p>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackwrite.md">IQueueCallbackWrite</a>
</p>

<p>When the driver passes either <b>WdfIoQueueDispatchSequential</b> or <b>WdfIoQueueDispatchParallel</b> for the <i>DispatchType</i> parameter of <b>CreateIoQueue</b> to create a nonmanual queue, <b>CreateIoQueue</b> can return S_OK only if the driver's queue callback object implements at least one of the preceding interfaces and indicates support of such interfaces through the <b>IUnknown</b> interface that <i>pCallbackInterface</i> points to. </p>

<p>When the driver passes <b>WdfIoQueueDispatchManual</b> for <i>DispatchType</i> to create a manual queue, <b>CreateIoQueue</b> can return S_OK only if the driver's queue callback object does not implement or indicate support of any of the preceding callback interfaces. For more information about the driver's callback objects, see <a href="wdf.creating_callback_objects">Creating Callback Objects</a>.</p>

<p>For more information about configuring dispatch mode, see <a href="wdf.configuring_dispatch_mode_for_an_i_o_queue">Configuring Dispatch Mode for an I/O Queue</a>.</p>

<p>The framework also calls <b>QueryInterface</b> on the supplied <b>IUnknown</b> interface to determine if the driver supports any of the following interfaces:</p>

<p>
<a href="..\wudfddi\nn-wudfddi-iobjectcleanup.md">IObjectCleanup</a>
</p>

<p>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackioresume.md">IQueueCallbackIoResume</a>
</p>

<p>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackiostop.md">IQueueCallbackIoStop</a>
</p>

<p>The framework also calls <b>QueryInterface</b> on the supplied <b>IUnknown</b> interface to determine if the driver supports the <a href="..\wudfddi\nn-wudfddi-iqueuecallbackstatechange.md">IQueueCallbackStateChange</a> interface. The driver's queue callback object can optionally implement and indicate support of <b>IQueueCallbackStateChange</b> only for a manual queue. The driver's queue callback object must not implement and indicate support of <b>IQueueCallbackStateChange</b> for a sequential or parallel queue. </p>

<p>For a code example of how to use the <b>CreateIoQueue</b> method, see <a href="wdf.iwdfdriver_createdevice">IWDFDriver::CreateDevice</a>.</p>

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
<dt>Wudfddi.h (include Wudfddi.h)</dt>
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
<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iobjectcleanup.md">IObjectCleanup</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackcreate.md">IQueueCallbackCreate</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackdefaultiohandler.md">IQueueCallbackDefaultIoHandler</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackdeviceiocontrol.md">IQueueCallbackDeviceIoControl</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackioresume.md">IQueueCallbackIoResume</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackiostop.md">IQueueCallbackIoStop</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackread.md">IQueueCallbackRead</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackstatechange.md">IQueueCallbackStateChange</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iqueuecallbackwrite.md">IQueueCallbackWrite</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>
</dt>
<dt>
<a href="..\wudfddi_types\ne-wudfddi-types--wdf-io-queue-dispatch-type.md">WDF_IO_QUEUE_DISPATCH_TYPE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice::CreateIoQueue method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>