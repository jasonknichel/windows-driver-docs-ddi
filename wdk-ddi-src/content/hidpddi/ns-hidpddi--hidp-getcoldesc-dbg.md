---
UID: NS.hidpddi._HIDP_GETCOLDESC_DBG
title: HIDP_GETCOLDESC_DBG
author: windows-driver-content
description: Contains the error code indicating the failure in parsing the report descriptor. This structure is used in the HidP_GetCollectionDescription call.
old-location: hid\hidp_getcoldesc_dbg.htm
old-project: hid
ms.assetid: 65EEEDED-14FE-4275-9314-276E544427DE
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: HIDP_GETCOLDESC_DBG, HIDP_GETCOLDESC_DBG, *PHIDP_GETCOLDESC_DBG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hidpddi.h
req.include-header: Hidpddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HIDP_GETCOLDESC_DBG
req.alt-loc: Hidpddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# HIDP_GETCOLDESC_DBG structure



## -description
<p>Contains the error code indicating the failure in parsing the report 
                                      descriptor. This structure is used in the <a href="..\hidpddi\nf-hidpddi-hidp-getcollectiondescription.md">HidP_GetCollectionDescription</a> call.</p>


## -syntax

````
typedef struct _HIDP_GETCOLDESC_DBG {
  ULONG BreakOffset;
  ULONG ErrorCode;
  ULONG Args[6];
} HIDP_GETCOLDESC_DBG, *PHIDP_GETCOLDESC_DBG;
````


## -struct-fields
<dl>

### -field BreakOffset

<dd>
<p>The byte offset in the report descriptor where the parsing error occurred.</p>
</dd>

### -field ErrorCode

<dd>
<p>Indicates the parsing error, if it’s not HIDP_GETCOLDESC_SUCCESS.

All possible values are defined in hidpddi.h, from HIDP_GETCOLDESC_SUCCESS to the end  of the file.
</p>
</dd>

### -field Args

<dd>
<p>Error-specific arguments. These are described as comments in the possible values for <b>ErrorCode</b> in hidpddi.h.</p>
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
<dt>Hidpddi.h (include Hidpddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hidpddi\nf-hidpddi-hidp-getcollectiondescription.md">HidP_GetCollectionDescription</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HIDP_GETCOLDESC_DBG structure%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>