---
UID: NE.rilapitypes.RIL3GPPCALLCONTROLCAUSECODE
title: RIL3GPPCALLCONTROLCAUSECODE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril3gppcallcontrolcausecode_2.htm
old-project: netvista
ms.assetid: c71684cf-9ae9-4330-b547-96646575b45f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RIL3GPPCALLCONTROLCAUSECODE, RIL3GPPCALLCONTROLCAUSECODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RIL3GPPCALLCONTROLCAUSECODE
req.alt-loc: rilapitypes.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# RIL3GPPCALLCONTROLCAUSECODE enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax

````
typedef enum _RIL3GPPCALLCONTROLCAUSECODE { 
  RIL_3GPPCCCAUSE_NO_ROUTE_TO_DESTINATION,
  RIL_3GPPCCCAUSE_CHANNEL_UNACCEPTABLE,
  RIL_3GPPCCCAUSE_OPERATOR_DETERMINED_BARRING,
  RIL_3GPPCCCAUSE_NORMAL_CALL_CLEARING,
  RIL_3GPPCCCAUSE_USER_BUSY,
  RIL_3GPPCCCAUSE_NO_USER_RESPONDING,
  RIL_3GPPCCCAUSE_USER_ALERTING_NO_ANSWER,
  RIL_3GPPCCCAUSE_CALL_REJECTED,
  RIL_3GPPCCCAUSE_NUMBER_CHANGED,
  RIL_3GPPCCCAUSE_PREEMPTION,
  RIL_3GPPCCCAUSE_DESTINATION_OUT_OF_ORDER,
  RIL_3GPPCCCAUSE_INVALID_NUMBER_FORMAT,
  RIL_3GPPCCCAUSE_FACILITY_REJECTED,
  RIL_3GPPCCCAUSE_RESPONSE_TO_STATUS_ENQUIRY,
  RIL_3GPPCCCAUSE_NORMAL_UNSPECIFIED,
  RIL_3GPPCCCAUSE_NO_CHANNEL_AVAILABLE,
  RIL_3GPPCCCAUSE_NETWORK_OUT_OF_ORDER,
  RIL_3GPPCCCAUSE_TEMPORARY_FAILURE,
  RIL_3GPPCCCAUSE_CONGESTION,
  RIL_3GPPCCCAUSE_ACCESS_INFORMATION_DISCARDED,
  RIL_3GPPCCCAUSE_REQUESTED_CHANNEL_NOT_AVAILABLE,
  RIL_3GPPCCCAUSE_RESOURCE_UNAVAILABLE_UNSPECIFIED,
  RIL_3GPPCCCAUSE_QOS_UNAVAILABLE,
  RIL_3GPPCCCAUSE_FACILITY_NOT_SUBSCRIBED,
  RIL_3GPPCCCAUSE_INCOMING_CALLS_BARRED_IN_CUG,
  RIL_3GPPCCCAUSE_BEARER_CAPABILITY_NOT_AUTHORIZED,
  RIL_3GPPCCCAUSE_BEARER_CAPABILITY_NOT_AVAILABLE,
  RIL_3GPPCCCAUSE_SVC_NOT_AVAILABLE_UNSPECIFIED,
  RIL_3GPPCCCAUSE_BEARER_SERVICE_NOT_IMPLEMENTED,
  RIL_3GPPCCCAUSE_ACM_NOT_LESS_THAN_ACMMAX,
  RIL_3GPPCCCAUSE_FACILITY_NOT_IMPLEMENTED,
  RIL_3GPPCCCAUSE_ONLY_RESTRICTED_DIGITAL_BEARER,
  RIL_3GPPCCCAUSE_SVC_NOT_IMPLEMENTED_UNSPECIFIED,
  RIL_3GPPCCCAUSE_INVALID_TRANSACTION_ID,
  RIL_3GPPCCCAUSE_USER_NOT_MEMBER_OF_CUG,
  RIL_3GPPCCCAUSE_INCOMPATIBLE_DESTINATION,
  RIL_3GPPCCCAUSE_SEMANTICALLY_INCORRECT_MESSAGE,
  RIL_3GPPCCCAUSE_INVALID_MANDATORY_FUNCTION,
  RIL_3GPPCCCAUSE_MESSAGE_TYPE_NOT_IMPLEMENTED,
  RIL_3GPPCCCAUSE_MESSAGE_TYPE_NOT_COMPATIBLE,
  RIL_3GPPCCCAUSE_IE_NOT_IMPLEMENTED,
  RIL_3GPPCCCAUSE_CONDITIONAL_IE_ERROR,
  RIL_3GPPCCCAUSE_MESSAGE_NOT_COMPATIBLE,
  RIL_3GPPCCCAUSE_RECOVERY_ON_TIMER_EXPIRY,
  RIL_3GPPCCCAUSE_PROTOCOL_ERROR_UNSPECIFIED,
  RIL_3GPPCCCAUSE_INTERWORKING_UNSPECIFIED
} RIL3GPPCALLCONTROLCAUSECODE;
````


## -enum-fields

### -field RIL_3GPPCCCAUSE_NO_ROUTE_TO_DESTINATION


### -field RIL_3GPPCCCAUSE_CHANNEL_UNACCEPTABLE


### -field RIL_3GPPCCCAUSE_OPERATOR_DETERMINED_BARRING


### -field RIL_3GPPCCCAUSE_NORMAL_CALL_CLEARING


### -field RIL_3GPPCCCAUSE_USER_BUSY


### -field RIL_3GPPCCCAUSE_NO_USER_RESPONDING


### -field RIL_3GPPCCCAUSE_USER_ALERTING_NO_ANSWER


### -field RIL_3GPPCCCAUSE_CALL_REJECTED


### -field RIL_3GPPCCCAUSE_NUMBER_CHANGED


### -field RIL_3GPPCCCAUSE_PREEMPTION


### -field RIL_3GPPCCCAUSE_DESTINATION_OUT_OF_ORDER


### -field RIL_3GPPCCCAUSE_INVALID_NUMBER_FORMAT


### -field RIL_3GPPCCCAUSE_FACILITY_REJECTED


### -field RIL_3GPPCCCAUSE_RESPONSE_TO_STATUS_ENQUIRY


### -field RIL_3GPPCCCAUSE_NORMAL_UNSPECIFIED


### -field RIL_3GPPCCCAUSE_NO_CHANNEL_AVAILABLE


### -field RIL_3GPPCCCAUSE_NETWORK_OUT_OF_ORDER


### -field RIL_3GPPCCCAUSE_TEMPORARY_FAILURE


### -field RIL_3GPPCCCAUSE_CONGESTION


### -field RIL_3GPPCCCAUSE_ACCESS_INFORMATION_DISCARDED


### -field RIL_3GPPCCCAUSE_REQUESTED_CHANNEL_NOT_AVAILABLE


### -field RIL_3GPPCCCAUSE_RESOURCE_UNAVAILABLE_UNSPECIFIED


### -field RIL_3GPPCCCAUSE_QOS_UNAVAILABLE


### -field RIL_3GPPCCCAUSE_FACILITY_NOT_SUBSCRIBED


### -field RIL_3GPPCCCAUSE_INCOMING_CALLS_BARRED_IN_CUG


### -field RIL_3GPPCCCAUSE_BEARER_CAPABILITY_NOT_AUTHORIZED


### -field RIL_3GPPCCCAUSE_BEARER_CAPABILITY_NOT_AVAILABLE


### -field RIL_3GPPCCCAUSE_SVC_NOT_AVAILABLE_UNSPECIFIED


### -field RIL_3GPPCCCAUSE_BEARER_SERVICE_NOT_IMPLEMENTED


### -field RIL_3GPPCCCAUSE_ACM_NOT_LESS_THAN_ACMMAX


### -field RIL_3GPPCCCAUSE_FACILITY_NOT_IMPLEMENTED


### -field RIL_3GPPCCCAUSE_ONLY_RESTRICTED_DIGITAL_BEARER


### -field RIL_3GPPCCCAUSE_SVC_NOT_IMPLEMENTED_UNSPECIFIED


### -field RIL_3GPPCCCAUSE_INVALID_TRANSACTION_ID


### -field RIL_3GPPCCCAUSE_USER_NOT_MEMBER_OF_CUG


### -field RIL_3GPPCCCAUSE_INCOMPATIBLE_DESTINATION


### -field RIL_3GPPCCCAUSE_SEMANTICALLY_INCORRECT_MESSAGE


### -field RIL_3GPPCCCAUSE_INVALID_MANDATORY_FUNCTION


### -field RIL_3GPPCCCAUSE_MESSAGE_TYPE_NOT_IMPLEMENTED


### -field RIL_3GPPCCCAUSE_MESSAGE_TYPE_NOT_COMPATIBLE


### -field RIL_3GPPCCCAUSE_IE_NOT_IMPLEMENTED


### -field RIL_3GPPCCCAUSE_CONDITIONAL_IE_ERROR


### -field RIL_3GPPCCCAUSE_MESSAGE_NOT_COMPATIBLE


### -field RIL_3GPPCCCAUSE_RECOVERY_ON_TIMER_EXPIRY


### -field RIL_3GPPCCCAUSE_PROTOCOL_ERROR_UNSPECIFIED


### -field RIL_3GPPCCCAUSE_INTERWORKING_UNSPECIFIED


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>