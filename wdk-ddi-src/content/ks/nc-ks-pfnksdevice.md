---
UID : NC:ks.PFNKSDEVICE
title : PFNKSDEVICE
author : windows-driver-content
description : An AVStream minidriver's AVStrMiniDevicePostStart routine is called when AVStream performs post-PnP-start processing. Use it to load drivers at start time, for example. Such events then will occur in the context of a worker thread after PnP start.
old-location : stream\avstrminidevicepoststart.htm
old-project : stream
ms.assetid : 5a08cdb2-f4e5-4c32-b98e-e854412954e9
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : NpdBrokerUninitialize
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ks.h
req.include-header : Ks.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : AVStrMiniDevicePostStart
req.alt-loc : ks.h
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
req.typenames : KEYWORDSELECTOR
---


# PFNKSDEVICE callback function
An AVStream minidriver's <i>AVStrMiniDevicePostStart</i> routine is called when AVStream performs post-PnP-start processing. Use it to load drivers at start time, for example. Such events then will occur in the context of a worker thread after PnP start.

## Syntax

```
PFNKSDEVICE Pfnksdevice;

NTSTATUS Pfnksdevice(
  PKSDEVICE Device
)
{...}
```

## Parameters

`Device`

Pointer to a <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure describing the device for which the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> request was sent.


## Return Value

Should return STATUS_SUCCESS or the error code that was returned from the attempt to perform the operation. If this routine returns failure, any pending <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> requests between the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> request and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551755">IRP_MN_STOP_DEVICE</a> request will be failed. Do not return STATUS_PENDING.

## Remarks

The minidriver specifies this routine's address in the <b>PostStart</b> member of its <a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a> structure.

This routine is optional.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSDEVICE routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>