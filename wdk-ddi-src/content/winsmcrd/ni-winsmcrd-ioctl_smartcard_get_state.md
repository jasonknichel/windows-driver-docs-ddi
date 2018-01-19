---
UID : NI:winsmcrd.IOCTL_SMARTCARD_GET_STATE
title : IOCTL_SMARTCARD_GET_STATE
author : windows-driver-content
description : The IOCTL_SMARTCARD_GET_STATE control code gets the current status of the smart card.
old-location : nfpdrivers\ioctl_smartcard_get_state.htm
old-project : nfpdrivers
ms.assetid : 18666E48-9505-448E-ABA1-536D365FC49D
ms.author : windowsdriverdev
ms.date : 12/18/2017
ms.keywords : GdiStartPageEMF
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : winsmcrd.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_SMARTCARD_GET_STATE
req.alt-loc : winsmcrd.h
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
req.typenames : DOT11_WPS_DEVICE_NAME, *PDOT11_WPS_DEVICE_NAME
req.product : Windows 10 or later.
---

# IOCTL_SMARTCARD_GET_STATE IOCTL
The <b>IOCTL_SMARTCARD_GET_STATE</b> 
   control code  gets the current status of the smart card.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
<text></text>

### Output Buffer
(DWORD) one of the following states:

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | winsmcrd.h |
| **IRQL** |  |

    ## See Also

        <dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a></dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/design-guide-smart-card">Smart card design guide</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20IOCTL_SMARTCARD_GET_STATE control code%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>