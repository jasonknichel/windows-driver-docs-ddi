---
UID: NF.sercx.SerCx2CustomReceiveTransactionReportProgress
title: SerCx2CustomReceiveTransactionReportProgress function
author: windows-driver-content
description: The SerCx2CustomReceiveTransactionReportProgress method reports whether progress is being made toward completing the current custom-receive transaction.
old-location: serports\sercx2customreceivetransactionreportprogress.htm
old-project: serports
ms.assetid: FBC776FE-1056-4D3B-BECB-124FC41DD68F
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: SerCx2CustomReceiveTransactionReportProgress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SerCx2CustomReceiveTransactionReportProgress
req.alt-loc: 2.0\Sercx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# SerCx2CustomReceiveTransactionReportProgress function



## -description
The <b>SerCx2CustomReceiveTransactionReportProgress</b> method reports whether progress is being made toward completing the current custom-receive transaction.


## -syntax

````
VOID SerCx2CustomReceiveTransactionReportProgress(
  [in] SERCX2CUSTOMRECEIVETRANSACTION             CustomReceive,
  [in] SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS Progress
);
````


## -parameters

### -param CustomReceive [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a> handle to a custom-receive object. The serial controller driver previously called the <a href="serports.sercx2customreceivetransactioncreate">SerCx2CustomReceiveTransactionCreate</a> method to create this object.

### -param Progress [in]

Whether progress is being made toward completing the custom-receive transaction. Set this parameter to one of the following enumeration constants:
<ul>
<li>SERCX2_CUSTOM_RECEIVE_NO_PROGRESS</li>
<li>SERCX2_CUSTOM_RECEIVE_BYTES_TRANSFERRED</li>
</ul>
For more information about these enumeration constants, see <a href="serports.sercx2_custom_receive_transaction_progress">SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS</a>.

## -returns
None.

## -remarks
To determine whether the serial controller is making progress toward completing the current custom-receive transaction, SerCx2 periodically calls the <a href="serports.evtsercx2customreceivetransactionqueryprogress">EvtSerCx2CustomReceiveTransactionQueryProgress</a> event callback function. In response to this call, the serial controller driver calls <b>SerCx2CustomReceiveTransactionReportProgress</b> to provide a progress report.

Each <b>SerCx2CustomReceiveTransactionReportProgress</b> call reports whether any data bytes have been transferred in the current custom-receive transaction since either the previous call to this method or the start of the transaction, whichever is more recent. If one or more bytes have been transferred, the call reports that the serial controller is making progress. If no bytes have been transferred, the call reports that there is no progress.

The serial controller driver must call this method only in response to a call from SerCx2 to the <i>EvtSerCx2CustomReceiveTransactionQueryProgress</i> function.

For more information, see <a href="https://msdn.microsoft.com/29849A8C-6656-444C-BE91-405A4BA2D5B0">SerCx2 Custom-Receive Transactions</a>.

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
Version
</th>
<td width="70%">
Available starting with Windows 8.1.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>2.0\Sercx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="serports.evtsercx2customreceivetransactionqueryprogress">EvtSerCx2CustomReceiveTransactionQueryProgress</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a>
</dt>
<dt>
<a href="serports.sercx2customreceivetransactioncreate">SerCx2CustomReceiveTransactionCreate</a>
</dt>
<dt>
<a href="serports.sercx2_custom_receive_transaction_progress">SERCX2_CUSTOM_RECEIVE_TRANSACTION_PROGRESS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2CustomReceiveTransactionReportProgress method%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>