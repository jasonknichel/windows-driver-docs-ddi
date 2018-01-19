---
UID : NS:ks._KSPIN
title : _KSPIN
author : windows-driver-content
description : The KSPIN structure describes an instantiated pin.
old-location : stream\kspin.htm
old-project : stream
ms.assetid : 0d290872-0944-4599-9deb-9a4f7b2df0e5
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : _KSPIN, *PKSPIN, KSPIN
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ks.h
req.include-header : Ks.h
req.target-type : Windows
req.target-min-winverclnt : Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KSPIN
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
req.typenames : "*PKSPIN, KSPIN"
---

# _KSPIN structure
The KSPIN structure describes an instantiated pin.

## Syntax
````
typedef struct _KSPIN {
  const KSPIN_DESCRIPTOR_EX *Descriptor;
  KSOBJECT_BAG              Bag;
  PVOID                     Context;
  ULONG                     Id;
  KSPIN_COMMUNICATION       Communication;
  BOOLEAN                   ConnectionIsExternal;
  KSPIN_INTERFACE           ConnectionInterface;
  KSPIN_MEDIUM              ConnectionMedium;
  KSPRIORITY                ConnectionPriority;
  PKSDATAFORMAT             ConnectionFormat;
  PKSMULTIPLE_ITEM          AttributeList;
  ULONG                     StreamHeaderSize;
  KSPIN_DATAFLOW            DataFlow;
  KSSTATE                   DeviceState;
  KSRESET                   ResetState;
  KSSTATE                   ClientState;
} KSPIN, *PKSPIN;
````

## Members


    ## Remarks
        In many ways, pins are the focus of filter behavior. This is reflected in the fact that the pin structure has a large number of members. Many minidrivers need to refine pin behavior and maintain additional pin-associated context. For filters with fairly conventional pin behavior, no additional refinement or context is required. In many cases, default pin behavior is sufficient; the pins are accessed using <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a>.

For synchronization purposes, the lifetime of this object is the interval starting when the minidriver's PreCreate dispatch function is called and ending when the minidriver's Close dispatch function returns, assuming the function does not return STATUS_PENDING. If it does return STATUS_PENDING, the object's lifetime ends when the client indicates completion of the close request by calling <a href="..\ks\nf-ks-kscompletependingrequest.md">KsCompletePendingRequest</a>.

If the minidriver needs to determine whether it has been told to go to a specific <a href="..\ks\ne-ks-pksstate.md">KSSTATE</a>, comparing the value of the <b>DeviceState</b> member of KSPIN to that state is not a reliable method. Instead, either look at the <i>ClientState</i> member, or create a variable in the <b>SetDeviceState</b> callback and then check this variable. <b>SetDeviceState</b> is a member of <a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>.

Also see <a href="https://msdn.microsoft.com/b7ee5756-1c79-4ead-9999-d13be9a0d3d9">Object Bags</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ks\ns-ks-_kspin_descriptor_ex.md">KSPIN_DESCRIPTOR_EX</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksadditemtoobjectbag.md">KsAddItemToObjectBag</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kscompletependingrequest.md">KsCompletePendingRequest</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_kspin_dispatch.md">KSPIN_DISPATCH</a>
</dt>
<dt>
<a href="..\ks\ns-ks-kspin_descriptor.md">KSPIN_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPIN structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>