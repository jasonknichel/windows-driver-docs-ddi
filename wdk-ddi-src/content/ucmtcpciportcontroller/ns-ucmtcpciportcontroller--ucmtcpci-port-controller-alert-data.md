---
UID: NS.ucmtcpciportcontroller._UCMTCPCI_PORT_CONTROLLER_ALERT_DATA
title: UCMTCPCI_PORT_CONTROLLER_ALERT_DATA
author: windows-driver-content
description: Contains information about hardware alerts received on the port controller object. This structure is used in the UcmTcpciPortControllerAlert call. Call UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT to initialize this structure.
old-location: buses\ucmtcpci_port_controller_alert_data.htm
old-project: usbref
ms.assetid: 4b3c2fc8-d7c3-4223-a88e-5db9ad852618
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: UCMTCPCI_PORT_CONTROLLER_ALERT_DATA, UCMTCPCI_PORT_CONTROLLER_ALERT_DATA, *PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucmtcpciportcontroller.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UCMTCPCI_PORT_CONTROLLER_ALERT_DATA
req.alt-loc: ucmtcpciportcontroller.h
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
req.iface: 
req.product: Windows 10 or later.
---

# UCMTCPCI_PORT_CONTROLLER_ALERT_DATA structure



## -description
<p>
                 Contains information about hardware alerts received on the port controller object. This structure is used in the <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrolleralert.md">UcmTcpciPortControllerAlert</a> call. Call <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpci-port-controller-alert-data-init.md">UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT</a> to initialize this structure.
             </p>


## -syntax

````
typedef struct _UCMTCPCI_PORT_CONTROLLER_ALERT_DATA {
  ULONG                               Size;
  UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE AlertType;
  union {
    UCMTCPCI_PORT_CONTROLLER_CC_STATUS       CCStatus;
    UCMTCPCI_PORT_CONTROLLER_POWER_STATUS    PowerStatus;
    UCMTCPCI_PORT_CONTROLLER_FAULT_STATUS    FaultStatus;
    PUCMTCPCI_PORT_CONTROLLER_RECEIVE_BUFFER ReceiveBuffer;
  };
} UCMTCPCI_PORT_CONTROLLER_ALERT_DATA, *PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA;
````


## -struct-fields
<dl>

### -field Size

<dd>
<p>Size of this structure.
                     
                 </p>
</dd>

### -field AlertType

<dd>
<p>A <a href="..\ucmtcpciportcontroller\ne-ucmtcpciportcontroller--ucmtcpci-port-controller-alert-type.md">UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE</a> value that indicates the type of hardware alert.
                     
                 </p>
</dd>

### -field CCStatus

<dd>
<p>A 
                     <b>UCMTCPCI_PORT_CONTROLLER_CC_STATUS</b> structure that contains status information about the CC lines of the port controller.
                 This structure is defined in UcmTcpciSpec.h.</p>
</dd>

### -field PowerStatus

<dd>
<p>A 
                     <b>UCMTCPCI_PORT_CONTROLLER_POWER_STATUS</b> structure that contains the power status of the port controller.
                 This structure is defined in UcmTcpciSpec.h.</p>
</dd>

### -field FaultStatus

<dd>
<p>A 
                     <b>UCMTCPCI_PORT_CONTROLLER_FAULT_STATUS</b> structure that contains the fault status of the port controller.
                 This structure is defined in UcmTcpciSpec.h.</p>
</dd>

### -field ReceiveBuffer

<dd>
<p>
                     A pointer to a 
                 <a href="https://msdn.microsoft.com/e8fab87d-7019-4b35-bbf9-fabb70ef579e">UCMTCPCI_PORT_CONTROLLER_RECEIVE_BUFFER</a> structure that represents the buffer for receiving the alert from the port controller. This structure is defined in UcmTcpciSpec.h.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ucmtcpciportcontroller.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrolleralert.md">UcmTcpciPortControllerAlert</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCMTCPCI_PORT_CONTROLLER_ALERT_DATA structure%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>