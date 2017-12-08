---
UID: NC.dispmprt.DXGKCB_MIRACAST_SEND_MESSAGE
title: DXGKCB_MIRACAST_SEND_MESSAGE
author: windows-driver-content
description: Sends an asynchronous message to the user-mode display driver.
old-location: display\dxgkcbmiracastsendmessage.htm
old-project: display
ms.assetid: E8C3B9E3-854C-488D-809B-0F0893591352
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SYMBOL_INFO_EX, SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkCbMiracastSendMessage
req.alt-loc: Dispmprt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: IDebugSystemObjects4
---

# DXGKCB_MIRACAST_SEND_MESSAGE callback



## -description
<p>Sends an asynchronous message to the user-mode display driver.</p>


## -prototype

````
DXGKCB_MIRACAST_SEND_MESSAGE DxgkCbMiracastSendMessage;

NTSTATUS* DxgkCbMiracastSendMessage(
  _In_     HANDLE                                MiracastHandle,
  _In_     ULONG                                 InputBufferSize,
  _In_     VOID                                  *pInputBuffer,
  _In_     ULONG                                 OutBufferSize,
  _Out_    VOID                                  *pOutputBuffer,
  _In_opt_ DXGKCB_MIRACAST_SEND_MESSAGE_CALLBACK pCallback,
  _In_opt_ PVOID                                 pCallbackContext
)
{ ... }
````


## -parameters
<dl>

### -param MiracastHandle [in]

<dd>
<p>A driver-supplied handle to the Miracast display device. This handle was originally passed in the <b>MiracastHandle</b> member of the <a href="..\dispmprt\ns-dispmprt--dxgk-miracast-display-callbacks.md">DXGK_MIRACAST_DISPLAY_CALLBACKS</a> structure in a call to the <a href="..\dispmprt\nc-dispmprt-dxgkddi-miracast-create-context.md">DxgkDdiMiracastCreateContext</a> function.</p>
</dd>

### -param InputBufferSize [in]

<dd>
<p>The size, in bytes, of the input buffer pointed to by <i>pInputBuffer</i>.</p>
</dd>

### -param pInputBuffer [in]

<dd>
<p>A pointer to the input buffer. <i>InputBufferSize</i> specifies the size of the buffer.</p>
<p>See Remarks for more info about the input buffer.</p>
</dd>

### -param OutBufferSize [in]

<dd>
<p>The size, in bytes, of the output buffer pointed to by <i>pOutputBuffer</i>.</p>
</dd>

### -param pOutputBuffer [out]

<dd>
<p>A pointer to the output buffer. <i>OutBufferSize</i> specifies the size of the buffer.</p>
<p>See Remarks for more info about the output buffer.</p>
</dd>

### -param pCallback [in, optional]

<dd>
<p>An optional pointer, supplied by the display miniport driver, to the <a href="..\dispmprt\nc-dispmprt-dxgkcb-miracast-send-message-callback.md">DxgkCbMiracastSendMessageCallback</a> callback function.</p>
<p>If the display miniport driver supplies the pointer to <a href="..\dispmprt\nc-dispmprt-dxgkcb-miracast-send-message-callback.md">DxgkCbMiracastSendMessageCallback</a>, then after the user-mode driver handles the message, the operating system sends a message to the user-mode driver asynchronously by calling <b>DxgkCbMiracastSendMessageCallback</b>.</p>
<p>See Return value and Remarks sections for more about calls to <a href="..\dispmprt\nc-dispmprt-dxgkcb-miracast-send-message-callback.md">DxgkCbMiracastSendMessageCallback</a>.</p>
</dd>

### -param pCallbackContext [in, optional]

<dd>
<p>An optional driver-supplied pointer to the driver-supplied callback context. The operating system passes this context to the driver-supplied callback routine after the operation has completed.</p>
</dd>
</dl>

## -returns
<p>Returns <b>STATUS_PENDING</b> if it successfully delivers the message. Otherwise, it returns one of the error codes that are defined in Ntstatus.h.</p>

<p>If the display miniport driver needs to know the status of message handling in user mode, it should supply the <a href="..\dispmprt\nc-dispmprt-dxgkcb-miracast-send-message-callback.md">DxgkCbMiracastSendMessageCallback</a> function in the <i>pCallback</i> parameter and check the return status in that function's <i>pIoStatusBlock</i> parameter.</p>

## -remarks
<p>If the display miniport driver supplies the <i>pInputBuffer</i> and <i>pOutputBuffer</i> buffers, it is the driver’s responsibility to hold these two buffers until the <a href="..\dispmprt\nc-dispmprt-dxgkcb-miracast-send-message-callback.md">DxgkCbMiracastSendMessageCallback</a> function is called. Otherwise, a random memory corruption issue can be created.</p>

<p>If the driver supplies the <a href="..\dispmprt\nc-dispmprt-dxgkcb-miracast-send-message-callback.md">DxgkCbMiracastSendMessageCallback</a> in the <i>pCallback</i> parameter, it's possible that <b>DxgkCbMiracastSendMessageCallback</b> will return before <b>DxgkCbMiracastSendMessage</b> returns.</p>

<p>Here's example code that shows how to use this function:</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
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
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dispmprt\ns-dispmprt--dxgk-miracast-display-callbacks.md">DXGK_MIRACAST_DISPLAY_CALLBACKS</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkcb-miracast-send-message-callback.md">DxgkCbMiracastSendMessageCallback</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi-miracast-create-context.md">DxgkDdiMiracastCreateContext</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_MIRACAST_SEND_MESSAGE callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>