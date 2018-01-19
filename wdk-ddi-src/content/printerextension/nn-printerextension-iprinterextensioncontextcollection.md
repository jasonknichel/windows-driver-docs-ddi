---
UID : NN:printerextension.IPrinterExtensionContextCollection
title : IPrinterExtensionContextCollection
author : windows-driver-content
description : Exposes a collection of IPrinterExtensionContext objects.
old-location : print\iprinterextensioncontextcollection.htm
old-project : print
ms.assetid : 693DAA13-70B3-48A7-9BC2-6369691539FD
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : IPrintSchemaTicket2, IPrintSchemaTicket2::GetParameterInitializer, GetParameterInitializer
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : interface
req.header : printerextension.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IPrinterExtensionContextCollection
req.alt-loc : Printerextension.h
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
req.typenames : PrintSchemaSelectionType
req.product : Windows 10 or later.
---

# IPrinterExtensionContextCollection interface

Exposes a collection of <a href="..\printerextension\nn-printerextension-iprinterextensioncontext.md">IPrinterExtensionContext</a> objects.

## Methods

<p>The <b>IPrinterExtensionContextCollection</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [printerextension.IPrinterExtensionContextCollection.GetAt](nf-printerextension-iprinterextensioncontextcollection-getat.md) | Gets a pointer to an IPrinterExtensionContext object. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum UMDF version** |  |
| **Header** | printerextension.h |
| **DLL** |  |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/ebbff4bc-36b2-4861-9efa-ffa45e013eb5">IDispatch</a>
</dt>
<dt>
<a href="..\printerextension\nn-printerextension-iprinterextensioncontext.md">IPrinterExtensionContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/947063C6-563A-4BB7-918E-479941B4583F">IPrinterExtensionEvent::OnPrinterQueuesEnumerated</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionContextCollection interface%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>