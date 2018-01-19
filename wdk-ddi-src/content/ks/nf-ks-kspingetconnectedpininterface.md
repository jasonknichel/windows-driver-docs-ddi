---
UID : NF:ks.KsPinGetConnectedPinInterface
title : KsPinGetConnectedPinInterface function
author : windows-driver-content
description : The KsPinGetConnectedPinInterface function queries the pin to which Pin is connected for a COM style interface.
old-location : stream\kspingetconnectedpininterface.htm
old-project : stream
ms.assetid : 594614ee-0d30-4574-81ad-a523e7fadc2c
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsPinGetConnectedPinInterface
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Universal
req.target-min-winverclnt : Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KsPinGetConnectedPinInterface
req.alt-loc : Ks.lib,Ks.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ks.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : 
---


# KsPinGetConnectedPinInterface function
The<b> KsPinGetConnectedPinInterface</b> function queries the pin to which <i>Pin</i> is connected for a COM style interface.

## Syntax

````
NTSTATUS KsPinGetConnectedPinInterface(
  _In_        PKSPIN Pin,
  _In_  const GUID   *InterfaceId,
  _Out_       PVOID  *Interface
);
````

## Parameters

`Pin`

A pointer to a <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure. AVStream queries the pin connected to <i>Pin</i> for the requested interface.

`InterfaceId`

A pointer to the GUID specifying the interface type to be obtained. A <b>QueryInterface</b> call is automatically performed for this interface.

`Interface`

A pointer to a pointer that AVStream sets to the location of the COM interface.


## Return Value

<b>KsPinGetConnectedPinInterface</b> returns STATUS_SUCCESS or STATUS_NOINTERFACE. See details below.

## Remarks

<i>Interface</i> has a corresponding reference count and <b>must</b> be released by the caller as in COM.

This routine returns STATUS_SUCCESS if the interface exists on the connected pin or in the AVStream thunk. If STATUS_SUCCESS is returned, AVStream deposits the interface pointer into <i>*Interface</i>. Otherwise, the routine returns STATUS_NOINTERFACE. This corresponds to the COM HRESULT E_NOINTERFACE.

By default, objects support the <b>IUnknown</b> interface and the <a href="..\ks\nn-ks-ikscontrol.md">IKsControl</a> interface. If the connected pin is an AVStream pin, the query and the returned interface pointer are direct calls to the other driver. If, on the other hand, the connected pin does not belong to an AVStream driver, a thunk is created that provides <i>IKsControl </i>support through synchronous calls to the driver containing the connected pin, using <a href="..\wdm\nf-wdm-iocalldriver.md">IoCallDriver</a>.

The most common usage of <b>KsPinGetConnectedPinInterface</b> is to acquire the control interface for the connected pin. This control interface can be used for property, method, or event calls down to the connected pin or can query for interfaces that have been aggregated onto the connected pin. If the connected pin is an AVStream pin; AVStream only provides thunking for <b>IKsControl</b> and <b>IUnknown</b> for non-AVStream pins.

The thunk is only created if<i> Pin</i> is a source pin; thus, the calls only work if one or more of the following is true:

The connection is intra-AVStream (<i>Pin</i>'s connected pin is an AVStream pin).

<i>Pin</i> is a source pin.

Otherwise, STATUS_UNSUCCESSFUL is returned.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ks\nf-ks-kspingetconnectedfilterinterface.md">KsPinGetConnectedFilterInterface</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kspingetreferenceclockinterface.md">KsPinGetReferenceClockInterface</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgetouterunknown.md">KsGetOuterUnknown</a>
</dt>
<dt>
<a href="..\ks\nn-ks-ikscontrol.md">IKsControl</a>
</dt>
<dt>
<a href="..\ks\nn-ks-iksreferenceclock.md">IKsReferenceClock</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksfiltergetouterunknown.md">KsFilterGetOuterUnknown</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksregisteraggregatedclientunknown.md">KsRegisterAggregatedClientUnknown</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinGetConnectedPinInterface function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>