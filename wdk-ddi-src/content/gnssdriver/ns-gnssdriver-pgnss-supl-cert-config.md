---
UID: NS.gnssdriver.PGNSS_SUPL_CERT_CONFIG
title: PGNSS_SUPL_CERT_CONFIG
author: windows-driver-content
description: This structure contains SUPL certificate information.
old-location: sensors\gnss_supl_cert_config.htm
old-project: sensors
ms.assetid: F974D5E2-7230-4F85-9C1A-7CE7E240DBE1
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: PGNSS_SUPL_CERT_CONFIG, GNSS_SUPL_CERT_CONFIG, *PGNSS_SUPL_CERT_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GNSS_SUPL_CERT_CONFIG
req.alt-loc: gnssdriver.h
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
req.iface: 
---

# PGNSS_SUPL_CERT_CONFIG structure



## -description
<p>This structure contains SUPL certificate information.</p>


## -syntax

````
typedef struct {
  ULONG                 Size;
  ULONG                 Version;
  GNSS_SUPL_CERT_ACTION CertAction;
  WCHAR                 SuplCertName[MAX_PATH];
  BOOL                  IsRoot;
  ULONG                 CertSize;
  BYTE                  Unused[512];
  BYTE                  CertData[ANYSIZE_ARRAY];
} GNSS_SUPL_CERT_CONFIG, *PGNSS_SUPL_CERT_CONFIG;
````


## -struct-fields
<dl>

### -field Size

<dd>
<p>Structure size.</p>
</dd>

### -field Version

<dd>
<p>Version number.</p>
</dd>

### -field CertAction

<dd>
<p>A <a href="..\gnssdriver\ne-gnssdriver-gnss-supl-cert-action.md">GNSS_SUPL_CERT_ACTION</a> enumeration value that specifies the action to take on the certificate.</p>
<table></table>
<p> </p>
<table>
<tr>
<td>
<p><b>GNSS_SUPL_CERT_INJECT</b></p>
</td>
<td>
<p>Inject the certificate.</p>
</td>
</tr>
<tr>
<td>
<p><b>GNSS_SUPL_CERT_DELETE</b></p>
</td>
<td>
<p>Delete the certificate specified by <b>SuplCertName</b>. The values of <b>CertSize</b> and <b>CertData</b> are ignored.</p>
</td>
</tr>
<tr>
<td>
<p><b>GNSS_SUPL_CERT_PURGE</b></p>
</td>
<td>
<p>Delete all the certificates injected to the GNSS driver previously. The values of <b>SuplCertName</b> , <b>CertSize</b>, and <b>CertData</b> are ignored.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field SuplCertName[MAX_PATH]

<dd>
<p>String containing the certificate name.</p>
</dd>

### -field IsRoot

<dd>
<p>Specify whether the certificate is a root certificate.</p>
<p>Multiple root certificates can be configured since some mobile operator require this functionality. An IHV supporting SUPL should have support for multiple certificates.</p>
</dd>

### -field CertSize

<dd>
<p>The size of the certificate in bytes.</p>
</dd>

### -field Unused[512]

<dd>
<p>Padding buffer.</p>
</dd>

### -field CertData[ANYSIZE_ARRAY]

<dd>
<p>The binary content of the certificate.  The total size of the bytes is defined by <b>CertSize</b>. The certificate is Base64 encoded.</p>
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
<dt>Gnssdriver.h</dt>
</dl>
</td>
</tr>
</table>