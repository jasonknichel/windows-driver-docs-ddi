---
UID: NS.netdispumdddi.MIRACAST_CHUNK_DATA
title: MIRACAST_CHUNK_DATA
author: windows-driver-content
description: Contains encode chunk data that is used when a user-mode driver calls the wireless display (Miracast) GetNextChunkData function.
old-location: display\miracast_chunk_data.htm
old-project: display
ms.assetid: 1ff4af0b-df1c-4529-9f80-c9e44d889a63
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: MIRACAST_CHUNK_DATA, MIRACAST_CHUNK_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MIRACAST_CHUNK_DATA
req.alt-loc: Netdispumdddi.h
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

# MIRACAST_CHUNK_DATA structure



## -description
<p>Contains encode chunk data that is used when a user-mode driver calls the wireless display (Miracast) <a href="..\netdispumdddi\nc-netdispumdddi-pfn-get-next-chunk-data.md">GetNextChunkData</a> function.</p>


## -syntax

````
typedef struct {
  MIRACAST_CHUNK_INFO ChunkInfo;
  UINT                PrivateDriverDataSize;
  UCHAR               PrivateDriverData[1];
} MIRACAST_CHUNK_DATA;
````


## -struct-fields
<dl>

### -field ChunkInfo

<dd>
<p>A <a href="..\netdispumdddi\ns-netdispumdddi-miracast-chunk-info.md">MIRACAST_CHUNK_INFO</a> encode chunk information structure that the user-mode display driver wants to report.</p>
</dd>

### -field PrivateDriverDataSize

<dd>
<p>The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to.</p>
</dd>

### -field PrivateDriverData

<dd>
<p>Private data, of type <b>UCHAR</b>, that the user-mode display driver sends when it calls the <a href="..\netdispumdddi\nc-netdispumdddi-pfn-get-next-chunk-data.md">GetNextChunkData</a> function.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Netdispumdddi.h (include Netdispumdddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\netdispumdddi\nc-netdispumdddi-pfn-get-next-chunk-data.md">GetNextChunkData</a>
</dt>
<dt>
<a href="..\netdispumdddi\ns-netdispumdddi-miracast-chunk-info.md">MIRACAST_CHUNK_INFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20MIRACAST_CHUNK_DATA structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>