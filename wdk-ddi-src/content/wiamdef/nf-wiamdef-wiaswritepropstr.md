---
UID : NF:wiamdef.wiasWritePropStr
title : wiasWritePropStr function
author : windows-driver-content
description : The wiasWritePropStr function writes a single string property value to a WIA item.
old-location : image\wiaswritepropstr.htm
old-project : image
ms.assetid : 542e4196-164b-4ae1-87ad-2d6adb9c8904
ms.author : windowsdriverdev
ms.date : 1/17/2018
ms.keywords : wiasWritePropStr
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wiamdef.h
req.include-header : Wiamdef.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : wiasWritePropStr
req.alt-loc : Wiaservc.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wiaservc.lib
req.dll : Wiaservc.dll
req.irql : 
req.typenames : "*PDEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, DEVICEDIALOGDATA2"
req.product : Windows 10 or later.
---


# wiasWritePropStr function
The <b>wiasWritePropStr</b> function writes a single string property value to a WIA item.

## Syntax

````
HRESULT _stdcall wiasWritePropStr(
  _In_     BYTE   *pWiasContext,
           PROPID propid,
  _In_opt_ BSTR   bstr
);
````

## Parameters

`pWiasContext`

Pointer to a WIA item context.

`propid`

Specifies the property identifier.

`bstr`

Specifies the string property value to write to the item.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wiamdef.h (include Wiamdef.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiaswritepropbin.md">wiasWritePropBin</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiaswritepropfloat.md">wiasWritePropFloat</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiaswritepropguid.md">wiasWritePropGuid</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiaswriteproplong.md">wiasWritePropLong</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiasreadpropstr.md">wiasReadPropStr</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasWritePropStr function%20 RELEASE:%20(1/17/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>