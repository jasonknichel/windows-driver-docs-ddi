---
UID: NS.ntddk._WHEA_PSHED_PLUGIN_CALLBACKS
title: WHEA_PSHED_PLUGIN_CALLBACKS
author: windows-driver-content
description: The WHEA_PSHED_PLUGIN_CALLBACKS structure describes the callback functions for a PSHED plug-in.
old-location: whea\whea_pshed_plugin_callbacks.htm
old-project: whea
ms.assetid: 3b99f2bf-0ebc-40b2-a586-acc89200132b
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WHEA_PSHED_PLUGIN_CALLBACKS, WHEA_PSHED_PLUGIN_CALLBACKS, *PWHEA_PSHED_PLUGIN_CALLBACKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WHEA_PSHED_PLUGIN_CALLBACKS
req.alt-loc: ntddk.h
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
---

# WHEA_PSHED_PLUGIN_CALLBACKS structure



## -description
<p>The WHEA_PSHED_PLUGIN_CALLBACKS structure describes the callback functions for a PSHED plug-in.</p>


## -syntax

````
typedef struct _WHEA_PSHED_PLUGIN_CALLBACKS {
  PSHED_PI_GET_ALL_ERROR_SOURCES      GetAllErrorSources;
  PVOID                               Reserved;
  PSHED_PI_GET_ERROR_SOURCE_INFO      GetErrorSourceInfo;
  PSHED_PI_SET_ERROR_SOURCE_INFO      SetErrorSourceInfo;
  PSHED_PI_ENABLE_ERROR_SOURCE        EnableErrorSource;
  PSHED_PI_DISABLE_ERROR_SOURCE       DisableErrorSource;
  PSHED_PI_WRITE_ERROR_RECORD         WriteErrorRecord;
  PSHED_PI_READ_ERROR_RECORD          ReadErrorRecord;
  PSHED_PI_CLEAR_ERROR_RECORD         ClearErrorRecord;
  PSHED_PI_RETRIEVE_ERROR_INFO        RetrieveErrorInfo;
  PSHED_PI_FINALIZE_ERROR_RECORD      FinalizeErrorRecord;
  PSHED_PI_CLEAR_ERROR_STATUS         ClearErrorStatus;
  PSHED_PI_ATTEMPT_ERROR_RECOVERY     AttemptRecovery;
  PSHED_PI_GET_INJECTION_CAPABILITIES GetInjectionCapabilities;
  PSHED_PI_INJECT_ERROR               InjectError;
} WHEA_PSHED_PLUGIN_CALLBACKS, *PWHEA_PSHED_PLUGIN_CALLBACKS;
````


## -struct-fields
<dl>

### -field GetAllErrorSources

<dd>
<p>A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed-pi-get-all-error-sources.md">GetAllErrorSources</a> callback function. If a PSHED plug-in does not participate in error source discovery, this member should be set to <b>NULL</b>.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved for system use. This member should be set to <b>NULL</b>.</p>
</dd>

### -field GetErrorSourceInfo

<dd>
<p>A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed-pi-get-error-source-info.md">GetErrorSourceInfo</a> callback function. If a PSHED plug-in does not participate in error source discovery, this member should be set to <b>NULL</b>.</p>
</dd>

### -field SetErrorSourceInfo

<dd>
<p>A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed-pi-set-error-source-info.md">SetErrorSourceInfo</a> callback function. If a PSHED plug-in does not participate in error source control, this member should be set to <b>NULL</b>.</p>
</dd>

### -field EnableErrorSource

<dd>
<p>A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed-pi-enable-error-source.md">EnableErrorSource</a> callback function. If a PSHED plug-in does not participate in error source control, this member should be set to <b>NULL</b>.</p>
</dd>

### -field DisableErrorSource

<dd>
<p>A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed-pi-disable-error-source.md">DisableErrorSource</a> callback function. If a PSHED plug-in does not participate in error source control, this member should be set to <b>NULL</b>.</p>
</dd>

### -field WriteErrorRecord

<dd>
<p>A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed-pi-write-error-record.md">WriteErrorRecord</a> callback function. If a PSHED plug-in does not participate in error record persistence, this member should be set to <b>NULL</b>.</p>
</dd>

### -field ReadErrorRecord

<dd>
<p>A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed-pi-read-error-record.md">ReadErrorRecord</a> callback function. If a PSHED plug-in does not participate in error record persistence, this member should be set to <b>NULL</b>.</p>
</dd>

### -field ClearErrorRecord

<dd>
<p>A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed-pi-clear-error-record.md">ClearErrorRecord</a> callback function. If a PSHED plug-in does not participate in error record persistence, this member should be set to <b>NULL</b>.</p>
</dd>

### -field RetrieveErrorInfo

<dd>
<p>A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed-pi-retrieve-error-info.md">RetrieveErrorInfo</a> callback function. If a PSHED plug-in does not participate in error information retrieval, this member should be set to <b>NULL</b>.</p>
</dd>

### -field FinalizeErrorRecord

<dd>
<p>A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed-pi-finalize-error-record.md">FinalizeErrorRecord</a> callback function. If a PSHED plug-in does not participate in error information retrieval, this member should be set to <b>NULL</b>.</p>
</dd>

### -field ClearErrorStatus

<dd>
<p>A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed-pi-clear-error-status.md">ClearErrorStatus</a> callback function. If a PSHED plug-in does not participate in error information retrieval, this member should be set to <b>NULL</b>.</p>
</dd>

### -field AttemptRecovery

<dd>
<p>A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed-pi-attempt-error-recovery.md">AttemptRecovery</a> callback function. If a PSHED plug-in does not participate in error recovery, this member should be set to <b>NULL</b>.</p>
</dd>

### -field GetInjectionCapabilities

<dd>
<p>A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed-pi-get-injection-capabilities.md">GetInjectionCapabilities</a> callback function. If a PSHED plug-in does not participate in error injection, this member should be set to <b>NULL</b>.</p>
</dd>

### -field InjectError

<dd>
<p>A pointer to the PSHED plug-in's <a href="..\ntddk\nc-ntddk-pshed-pi-inject-error.md">InjectError</a> callback function. If a PSHED plug-in does not participate in error injection, this member should be set to <b>NULL</b>.</p>
</dd>
</dl>

## -remarks
<p>A WHEA_PSHED_PLUGIN_CALLBACKS structure is contained within the <a href="..\ntddk\ns-ntddk--whea-pshed-plugin-registration-packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\nc-ntddk-pshed-pi-attempt-error-recovery.md">AttemptRecovery</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed-pi-clear-error-record.md">ClearErrorRecord</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed-pi-clear-error-status.md">ClearErrorStatus</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed-pi-disable-error-source.md">DisableErrorSource</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed-pi-enable-error-source.md">EnableErrorSource</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed-pi-finalize-error-record.md">FinalizeErrorRecord</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed-pi-get-all-error-sources.md">GetAllErrorSources</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed-pi-get-error-source-info.md">GetErrorSourceInfo</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed-pi-get-injection-capabilities.md">GetInjectionCapabilities</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed-pi-inject-error.md">InjectError</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed-pi-read-error-record.md">ReadErrorRecord</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed-pi-retrieve-error-info.md">RetrieveErrorInfo</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed-pi-set-error-source-info.md">SetErrorSourceInfo</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed-pi-write-error-record.md">WriteErrorRecord</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-pshed-plugin-registration-packet.md">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_PSHED_PLUGIN_CALLBACKS structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>