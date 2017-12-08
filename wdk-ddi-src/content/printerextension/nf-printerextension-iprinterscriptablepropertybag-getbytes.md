---
UID: NF.printerextension.IPrinterScriptablePropertyBag.GetBytes
title: IPrinterScriptablePropertyBag::GetBytes
author: windows-driver-content
description: Gets a byte array property.
old-location: print\iprinterscriptablepropertybag_getbytes.htm
old-project: print
ms.assetid: 419BCBB6-634A-421D-A940-8690BCCF1AC6
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IPrinterScriptablePropertyBag, GetBytes, IPrinterScriptablePropertyBag::GetBytes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrinterScriptablePropertyBag.GetBytes
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
req.iface: IPrinterScriptablePropertyBag
req.product: Windows 10 or later.
---

# IPrinterScriptablePropertyBag::GetBytes method



## -description
<p>Gets a byte array property.</p>


## -syntax

````
HRESULT GetBytes(
  [in]          BSTR      bstrName,
  [out, retval] IDispatch **ppdispArray
);
````


## -parameters
<dl>

### -param bstrName [in]

<dd>
<p>The property to read.</p>
</dd>

### -param ppdispArray [out, retval]

<dd>
<p>The returned JavaScript array.</p>
</dd>
</dl>

## -returns
<p>This method returns an <b>HRESULT</b> value.</p>

## -remarks
<p>A call to <b>GetBytes</b> will throw an exception, if the specified property is not found. We recommend that you use a try-catch statement around calls to this method, to allow your app to handle any failures gracefully.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
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
<dt>Printerextension.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\printerextension\nn-printerextension-iprinterscriptablepropertybag.md">IPrinterScriptablePropertyBag</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterScriptablePropertyBag::GetBytes method%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>