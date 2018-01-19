---
UID : NF:wiamindr_lh.IWiaMiniDrvTransferCallback.SendMessage
title : IWiaMiniDrvTransferCallback::SendMessage method
author : windows-driver-content
description : Periodically called by the WIA mini-driver during a data transfer, to update the WIA application client about the progress and status of the transfer.
old-location : image\iwiaminidrvtransfercallback_sendmessage.htm
old-project : image
ms.assetid : 9C4800E6-0F5F-4895-AD19-635C7F784462
ms.author : windowsdriverdev
ms.date : 1/17/2018
ms.keywords : IWiaMiniDrvTransferCallback, IWiaMiniDrvTransferCallback::SendMessage, SendMessage
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wiamindr_lh.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IWiaMiniDrvTransferCallback.SendMessage
req.alt-loc : Wiamindr_lh.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PSCANWINDOW, SCANWINDOW"
req.product : Windows 10 or later.
---


# SendMessage method
Periodically called by the WIA mini-driver during a data transfer, to update the WIA application client about the progress and status of the transfer.

For more information about the progress data that is transferred, see <a href="http://msdn.microsoft.com/library/windows/desktop/ms629867(v=vs.85).aspx">WiaTransferParams</a>.

## Syntax

````
HRESULT SendMessage(
  [in] LONG              lFlags,
  [in] WiaTransferParams *pWiaTransferParams
);
````

## Parameters

`lFlags`

Represents flag bits. This parameter is unused and should always be set to zero (0) by the caller.

`pWiaTransferParams`

Pointer to a <b>WiaTransferParams</b> object.


## Return Value

This method returns S_OK when the call is successful. Otherwise it returns an appropriate HRESULT error code.

## Remarks

When the current transfer sequence is cancelled, the <b>SendMessage</b> method returns S_FALSE.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wiamindr_lh.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiaminidrvtransfercallback.md">IWiaMiniDrvTransferCallback</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/0cdc02bf-23fe-4122-8d5f-f42c3c07da8b">Cancellation of Data Transfers in Windows Vista</a>
</dt>
<dt><a href="http://msdn.microsoft.com/library/windows/desktop/ms629867(v=vs.85).aspx">WiaTransferParams</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaMiniDrvTransferCallback::SendMessage method%20 RELEASE:%20(1/17/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>