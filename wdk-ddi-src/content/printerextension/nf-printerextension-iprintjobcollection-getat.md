---
UID: NF.printerextension.IPrintJobCollection.GetAt
title: IPrintJobCollection::GetAt
author: windows-driver-content
description: Gets a pointer to an IPrintJob object.
old-location: print\iprintjobcollection_getat.htm
old-project: print
ms.assetid: B920E5D1-D565-4626-A15E-8500DFFBC9FF
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IPrintJobCollection, GetAt, IPrintJobCollection::GetAt
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintJobCollection.GetAt
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
req.iface: IPrintJobCollection
req.product: Windows 10 or later.
---

# IPrintJobCollection::GetAt method



## -description
<p>Gets a pointer to an <a href="..\printerextension\nn-printerextension-iprintjob.md">IPrintJob</a> object.</p>


## -syntax

````
HRESULT GetAt(
  [in]          ULONG     ulIndex,
  [out, retval] IPrintJob **ppJob
);
````


## -parameters
<dl>

### -param ulIndex [in]

<dd>
<p>Index of the <b>IPrintJob</b> object within the collection.</p>
</dd>

### -param ppJob [out, retval]

<dd>
<p>Pointer to an <b>IPrintJob</b> object.</p>
</dd>
</dl>

## -returns
<p>Returns an <b>HRESULT</b> value. If the method call was not successful, it returns the appropriate <b>HRESULT</b> error code.</p>

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
<a href="..\printerextension\nn-printerextension-iprintjob.md">IPrintJob</a>
</dt>
<dt>
<a href="..\printerextension\nn-printerextension-iprintjobcollection.md">IPrintJobCollection</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintJobCollection::GetAt method%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>