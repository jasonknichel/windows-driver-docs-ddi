---
UID : NS:gnssdriver.GNSS_SUPL_CERT_CONFIG
title : GNSS_SUPL_CERT_CONFIG
author : windows-driver-content
description : This structure contains SUPL certificate information.
old-location : sensors\gnss_supl_cert_config.htm
old-project : sensors
ms.assetid : F974D5E2-7230-4F85-9C1A-7CE7E240DBE1
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : GNSS_SUPL_CERT_CONFIG, GNSS_SUPL_CERT_CONFIG, *PGNSS_SUPL_CERT_CONFIG
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : gnssdriver.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : GNSS_SUPL_CERT_CONFIG
req.alt-loc : gnssdriver.h
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
req.typenames : GNSS_SUPL_CERT_CONFIG, *PGNSS_SUPL_CERT_CONFIG
---

# GNSS_SUPL_CERT_CONFIG structure
This structure contains SUPL certificate information.

## Syntax
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

## Members

        
            `CertAction`

            A <a href="..\gnssdriver\ne-gnssdriver-gnss_supl_cert_action.md">GNSS_SUPL_CERT_ACTION</a> enumeration value that specifies the action to take on the certificate.

<table></table>
 

<table>
<tr>
<td>
<b>GNSS_SUPL_CERT_INJECT</b>

</td>
<td>
Inject the certificate.

</td>
</tr>
<tr>
<td>
<b>GNSS_SUPL_CERT_DELETE</b>

</td>
<td>
Delete the certificate specified by <b>SuplCertName</b>. The values of <b>CertSize</b> and <b>CertData</b> are ignored.

</td>
</tr>
<tr>
<td>
<b>GNSS_SUPL_CERT_PURGE</b>

</td>
<td>
Delete all the certificates injected to the GNSS driver previously. The values of <b>SuplCertName</b> , <b>CertSize</b>, and <b>CertData</b> are ignored.

</td>
</tr>
</table>
        
            `CertSize`

            The size of the certificate in bytes.
        
            `Size`

            Structure size.
        
            `Version`

            Version number.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | gnssdriver.h |