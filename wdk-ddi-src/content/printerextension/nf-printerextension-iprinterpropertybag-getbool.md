---
UID: NF.printerextension.IPrinterPropertyBag.GetBool
title: IPrinterPropertyBag::GetBool
author: windows-driver-content
description: Reads a specified boolean property.
old-location: print\iprinterpropertybag_getbool.htm
old-project: print
ms.assetid: 0C7ED962-F4E2-4F2F-B2CF-96DCFC71C4DD
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IPrinterPropertyBag, GetBool, IPrinterPropertyBag::GetBool
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printerextension.h
req.include-header: Printerextension.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrinterPropertyBag.GetBool
req.alt-loc: Printerextension.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.iface: IPrinterPropertyBag
req.product: Windows 10 or later.
---

# IPrinterPropertyBag::GetBool method



## -description
<p>Reads a specified boolean property.</p>


## -syntax

````
HRESULT GetBool(
  [in]          BSTR bstrName,
  [out, retval] BOOL *pbValue
);
````


## -parameters
<dl>

### -param bstrName [in]

<dd>
<p>The name of the property.</p>
</dd>

### -param pbValue [out, retval]

<dd>
<p>The returned property value.</p>
</dd>
</dl>

## -returns
<p>This method returns an <b>HRESULT</b> value.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Printerextension.h (include Printerextension.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterPropertyBag::GetBool method%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>