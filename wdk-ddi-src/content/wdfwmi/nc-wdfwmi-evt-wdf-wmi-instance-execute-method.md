---
UID: NC.wdfwmi.EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD
title: EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD
author: windows-driver-content
description: A driver's EvtWmiInstanceExecuteMethod callback function executes a specified method that the driver provides for a WMI data provider's instance.
old-location: wdf\evtwmiinstanceexecutemethod.htm
old-project: wdf
ms.assetid: b14de1d7-0df2-46d1-a3bd-c23f33d3ed75
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfVerifierKeBugCheck
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfwmi.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: EvtWmiInstanceExecuteMethod
req.alt-loc: WdfWMI.h
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

# EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD callback



## -description
<p class="CCE_Message">[Applies to KMDF only]</p>
<p>A driver's <i>EvtWmiInstanceExecuteMethod</i> callback function executes a specified method that the driver provides for a WMI data provider's instance.</p>


## -prototype

````
EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD EvtWmiInstanceExecuteMethod;

NTSTATUS EvtWmiInstanceExecuteMethod(
  _In_    WDFWMIINSTANCE WmiInstance,
  _In_    ULONG          MethodId,
  _In_    ULONG          InBufferSize,
  _In_    ULONG          OutBufferSize,
  _Inout_ PVOID          Buffer,
  _Out_   PULONG         BufferUsed
)
{ ... }
````


## -parameters
<dl>

### -param WmiInstance [in]

<dd>
<p>A handle to a WMI instance object.</p>
</dd>

### -param MethodId [in]

<dd>
<p>A value that identifies a method in a provider instance. This value corresponds to the <a href="https://msdn.microsoft.com/e2d281b3-913c-43ad-921c-80dc8be09aa0">WmiMethodId</a> value that is specified in the provider's MOF file.</p>
</dd>

### -param InBufferSize [in]

<dd>
<p>The number of bytes of input data.</p>
</dd>

### -param OutBufferSize [in]

<dd>
<p>The number of bytes of output data that the buffer that <i>Buffer</i> points to can hold.</p>
</dd>

### -param Buffer [in, out]

<dd>
<p>A pointer to a buffer that is used for input, output, or both, as determined by the specified method. If both input and output data are provided, the driver overwrites the input data with the output data.</p>
</dd>

### -param BufferUsed [out]

<dd>
<p>A pointer to a location that receives the number of bytes that the driver wrote into the output buffer. If the output buffer size that the <i>OutBufferSize</i> parameter specifies is too small, the driver sets this location to the required buffer size.  </p>
</dd>
</dl>

## -returns
<p>The <i>EvtWmiInstanceExecuteMethod</i> callback function must return STATUS_SUCCESS if the operation succeeds. Otherwise, this function must return a status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>FALSE</b>. The driver must return STATUS_BUFFER_TOO_SMALL if the value of the <i>OutBufferSize</i> parameter indicates that the output buffer is too small to receive the data.</p>

## -remarks
<p>To register an <i>EvtWmiInstanceExecuteMethod</i> callback function, your driver must place the function's address in a <a href="..\wdfwmi\ns-wdfwmi--wdf-wmi-instance-config.md">WDF_WMI_INSTANCE_CONFIG</a> structure before calling <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>. </p>

<p>After a driver executes the instance method that the <i>MethodId</i> parameter specifies, the driver must use the <i>BufferUsed</i> parameter to store the number of bytes that were written to the buffer.</p>

<p>The framework does not synchronize calls to a driver's WMI event callback functions with each other or with any of the driver's other event callback functions. If an <i>EvtWmiInstanceExecuteMethod</i> callback function's data is dynamic and shared with other callback functions, your driver can use the framework's <a href="wdf.using_framework_locks">wait locks or spin locks</a> to synchronize access to the data.</p>

<p>For more information about the <i>EvtWmiInstanceExecuteMethod</i> callback function, see <a href="wdf.supporting_wmi_in_kmdf_drivers">Supporting WMI in Framework-Based Drivers</a>.</p>

<p>To define an <i>EvtWmiInstanceExecuteMethod</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define an <i>EvtWmiInstanceExecuteMethod</i> callback function that is named <i>MyWmiInstanceExecuteMethod</i>, use the <b>EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD</b> type as shown in this code example:</p>

<p>To define an <i>EvtWmiInstanceExecuteMethod</i> callback function that is named <b>MyWmiInstanceExecuteMethod</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:</p>

<p>Then, implement your callback function as follows:</p>

<p>The <b>EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD</b> function type is defined in the WdfWMI.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>WdfWMI.h (include Wdf.h)</dt>
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
<a href="..\wdfwmi\nc-wdfwmi-evt-wdf-wmi-instance-query-instance.md">EvtWmiInstanceQueryInstance</a>
</dt>
<dt>
<a href="..\wdfwmi\nc-wdfwmi-evt-wdf-wmi-instance-set-instance.md">EvtWmiInstanceSetInstance</a>
</dt>
<dt>
<a href="..\wdfwmi\nc-wdfwmi-evt-wdf-wmi-instance-set-item.md">EvtWmiInstanceSetItem</a>
</dt>
<dt>
<a href="..\wdfwmi\nc-wdfwmi-evt-wdf-wmi-provider-function-control.md">EvtWmiProviderFunctionControl</a>
</dt>
<dt>
<a href="..\wdfwmi\ns-wdfwmi--wdf-wmi-instance-config.md">WDF_WMI_INSTANCE_CONFIG</a>
</dt>
<dt>
<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_WMI_INSTANCE_EXECUTE_METHOD callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>