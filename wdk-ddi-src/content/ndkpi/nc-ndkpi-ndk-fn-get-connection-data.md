---
UID: NC.ndkpi.NDK_FN_GET_CONNECTION_DATA
title: NDK_FN_GET_CONNECTION_DATA
author: windows-driver-content
description: The NdkGetConnectionData (NDK_FN_GET_CONNECTION_DATA) function gets read limit values and the private data sent by the peer.
old-location: netvista\ndk_fn_get_connection_data.htm
old-project: netvista
ms.assetid: A6099DCB-7F10-4BDB-B463-422C2B7A2B3F
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdkGetConnectionData
req.alt-loc: ndkpi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.iface: 
---

# NDK_FN_GET_CONNECTION_DATA callback



## -description
<p>The <i>NdkGetConnectionData</i>  (<i>NDK_FN_GET_CONNECTION_DATA</i>) function gets read limit values and the private data sent by the peer.</p>


## -prototype

````
NDK_FN_GET_CONNECTION_DATA NdkGetConnectionData;

NTSTATUS NdkGetConnectionData(
  _In_      NDK_CONNECTOR                                                             *pNdkConnector,
  _Out_opt_ ULONG                                                                     *pInboundReadLimit,
  _Out_opt_ ULONG                                                                     *pOutboundReadLimit,
            _Out_writes_bytes_to_opt_(*pPrivateDataLength, *pPrivateDataLength) PVOID pPrivateData,
            _Inout_ ULONG                                                             *pPrivateDataLength
)
{ ... }
````


## -parameters
<dl>

### -param pNdkConnector [in]

<dd>
<p>A pointer to an NDK connector object (<a href="..\ndkpi\ns-ndkpi--ndk-connector.md">NDK_CONNECTOR</a>).</p>
</dd>

### -param pInboundReadLimit [out, optional]

<dd>
<p>The maximum number of incoming in-progress read operations to allow on the QP is returned in this location.</p>
</dd>

### -param pOutboundReadLimit [out, optional]

<dd>
<p>The maximum number of outgoing in-progress read operations to allow on the QP is returned in this location.</p>
</dd>

### -param pPrivateData 

<dd>
<p>A pointer to private data that is returned.

</p>
</dd>

### -param pPrivateDataLength 

<dd>
<p>The length, in bytes, of the private data that is provided in the <i>pPrivateData</i> parameter.</p>
<div class="alert"><b>Note</b>  The output value does not indicate the actual length of private data stored in the buffer. NDK consumers must negotiate the format and length of the actual private data. For more information about private data, see the Remarks section.</div>
<div> </div>
</dd>
</dl>

## -returns
<p>The <i>NdkGetConnectionData</i> function returns one of the following NTSTATUS codes.</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The operation completed successfully.</p><dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl><p>The value in the <i>*pPrivateDataLength</i> parameter specified a buffer size that was too small to hold the connection private data. <i>*pPrivateDataLength</i> is updated with the required size.</p><dl>
<dt><b>Other status codes</b></dt>
</dl><p>An error occurred. </p>

<p> </p>

## -remarks
<p>The <i>NdkGetConnectionData</i>   function gets the private data sent by the peer with connect, accept, or reject requests and the effective inbound and outbound read limit values. These values are derived from the local and remote peers' requested values and the provider's maximum limits.</p>

<p>To access the private data and the effective inbound read limit (IRD) and outbound read limit (ORD) values from the active side, an NDK consumer can call <i>NdkGetConnectionData</i> for a connector object that was  passed to the <a href="..\ndkpi\nc-ndkpi-ndk-fn-connect-event-callback.md">NDK_FN_CONNECT_EVENT_CALLBACK</a> function.   </p>

<p>To access the private data and effective IRD and ORD values from the passive side, the consumer can call <i>NdkGetConnectionData</i> for a connector object for which <a href="..\ndkpi\nc-ndkpi-ndk-fn-connect.md">NDK_FN_CONNECT</a> or  <a href="..\ndkpi\nc-ndkpi-ndk-fn-connect-with-shared-endpoint.md">NDK_FN_CONNECT_WITH_SHARED_ENDPOINT</a> completed successfully An NDK consumer will not call this function after it calls the <a href="..\ndkpi\nc-ndkpi-ndk-fn-accept.md">NDK_FN_ACCEPT</a> function on the passive side or the <a href="..\ndkpi\nc-ndkpi-ndk-fn-complete-connect.md">NDK_FN_COMPLETE_CONNECT</a> function  on the active side.
</p>

<p>If  the <i>pPrivateData</i> parameter  is NULL and <i>*pPrivateDataLength</i> is zero, an NDK provider must return STATUS_SUCCESS and store the required private data buffer size (<i>RDS</i>) in <i>*pPrivateDataLength</i>. </p>

<p>If <i>pPrivateData</i> is NULL and <i>*pPrivateDataLength</i> is greater than zero, this is an invalid request. A consumer must never do this.
</p>

<p>If <i>pPrivateData</i> is not NULL, the provider must copy the private data to the buffer at  <i>pPrivateData</i> up to the smaller of <i>*pPrivateDataLength</i> or <i>RDS</i> in  bytes. </p>

<p>If <i>*pPrivateDataLength</i> is greater than or equal to <i>RDS</i>, the provider must return STATUS_SUCCESS. Otherwise, the provider must return STATUS_BUFFER_TOO_SMALL. In both cases, the provider must store the <i>RDS</i> in <i>*pPrivateDataLength</i> before returning.  
</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>None supported</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.30 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndkpi.h (include Ndkpi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-connector.md">NDK_CONNECTOR</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-connector-dispatch.md">NDK_CONNECTOR_DISPATCH</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_GET_CONNECTION_DATA callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>