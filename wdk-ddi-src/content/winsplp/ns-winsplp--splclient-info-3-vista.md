---
UID: NS.winsplp._SPLCLIENT_INFO_3_VISTA
title: SPLCLIENT_INFO_3_VISTA
author: windows-driver-content
description: Contains a super-set of the information in both a SPLCLIENT_INFO_1 and SPLCLIENT_INFO_2 structure. It also contains additional information needed by the provider.
old-location: print\splclient_info_3_vista.htm
old-project: print
ms.assetid: 076ECB20-CFAD-4A16-9B01-6936E0DD7E50
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: SPLCLIENT_INFO_3_VISTA, SPLCLIENT_INFO_3_VISTA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SPLCLIENT_INFO_3_VISTA
req.alt-loc: Winsplp.h
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
req.product: Windows 10 or later.
---

# SPLCLIENT_INFO_3_VISTA structure



## -description
<p>Contains a super-set of the information in both a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562674">SPLCLIENT_INFO_1</a> and <b>SPLCLIENT_INFO_2</b> structure. It also contains additional information needed by the provider.</p>


## -syntax

````
typedef struct _SPLCLIENT_INFO_3_VISTA {
  UINT             cbSize;
  DWORD            dwFlags;
  DWORD            dwSize;
  PWSTR            pMachineName;
  PWSTR            pUserName;
  DWORD            dwBuildNum;
             DWORD dwMajorVersion;
  DWORD            dwMinorVersion;
  WORD             wProcessorArchitecture;
  UINT64           hSplPrinter;
} SPLCLIENT_INFO_3_VISTA;
````


## -struct-fields
<dl>

### -field cbSize

<dd>
<p>Specifies the size in bytes of this structure.</p>
</dd>

### -field dwFlags

<dd>
<p>Specifies open printer additional flags to the provider.</p>
</dd>

### -field dwSize

<dd>
<p>Reserved. Used for compatibility with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562674">SPLCLIENT_INFO_1</a> structure.</p>
</dd>

### -field pMachineName

<dd>
<p>Specifies the client machine name.</p>
</dd>

### -field pUserName

<dd>
<p>Specifies the client user name.</p>
</dd>

### -field dwBuildNum

<dd>
<p>Specifies the client build number.</p>
</dd>

### -field dwMajorVersion

<dd>
<p>Specifies the major version of the client machine.</p>
</dd>

### -field dwMinorVersion

<dd>
<p>Specifies the minor version of the client machine.</p>
</dd>

### -field wProcessorArchitecture

<dd>
<p>Specifies the client machine architecture.</p>
</dd>

### -field hSplPrinter

<dd>
<p>Specifies the server-side handle to be used for direct calls.</p>
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
<dt>Winsplp.h</dt>
</dl>
</td>
</tr>
</table>