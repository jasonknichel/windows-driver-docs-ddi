---
UID: NS.ntddstor._STORAGE_CRYPTO_DESCRIPTOR
title: STORAGE_CRYPTO_DESCRIPTOR
author: windows-driver-content
description: Reserved for system use.
old-location: storage\storage_crypto_descriptor.htm
old-project: storage
ms.assetid: 1D948882-2286-4080-A41B-D20714FC0A66
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: STORAGE_CRYPTO_DESCRIPTOR, STORAGE_CRYPTO_DESCRIPTOR, *PSTORAGE_CRYPTO_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_CRYPTO_DESCRIPTOR
req.alt-loc: Ntddstor.h
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

# STORAGE_CRYPTO_DESCRIPTOR structure



## -description
<p>Reserved for system use.</p>


## -syntax

````
typedef struct _STORAGE_CRYPTO_DESCRIPTOR {
  DWORD                                                          Version;
  DWORD                                                          Size;
  DWORD                                                          NumKeysSupported;
  DWORD                                                          NumCryptoCapabilities;
   _Field_size_(NumCryptoCapabilities) STORAGE_CRYPTO_CAPABILITY CryptoCapabilities[ANYSIZE_ARRAY];
} STORAGE_CRYPTO_DESCRIPTOR, *PSTORAGE_CRYPTO_DESCRIPTOR;
````


## -struct-fields
<dl>

### -field Version

<dd>
<p>Reserved for system use.</p>
</dd>

### -field Size

<dd>
<p>Reserved for system use.</p>
</dd>

### -field NumKeysSupported

<dd>
<p>Reserved for system use.</p>
</dd>

### -field NumCryptoCapabilities

<dd>
<p>Reserved for system use.</p>
</dd>

### -field CryptoCapabilities

<dd>
<p>Reserved for system use.</p>
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
<dt>Ntddstor.h</dt>
</dl>
</td>
</tr>
</table>