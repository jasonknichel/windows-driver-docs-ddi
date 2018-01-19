---
UID : NS:scsi._SES_CONFIGURATION_DIAGNOSTIC_PAGE
title : _SES_CONFIGURATION_DIAGNOSTIC_PAGE
author : windows-driver-content
description : TBD.
old-location : storage\ses_configuration_diagnostic_page.htm
old-project : storage
ms.assetid : 0FD748D6-F598-44D1-A8D3-E63764CB90C6
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _SES_CONFIGURATION_DIAGNOSTIC_PAGE, SES_CONFIGURATION_DIAGNOSTIC_PAGE, *PSES_CONFIGURATION_DIAGNOSTIC_PAGE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : scsi.h
req.include-header : Minitape.h, Storport.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows 10, version 1709 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : SES_CONFIGURATION_DIAGNOSTIC_PAGE
req.alt-loc : scsi.h
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
req.typenames : SES_CONFIGURATION_DIAGNOSTIC_PAGE, *PSES_CONFIGURATION_DIAGNOSTIC_PAGE
req.product : Windows 10 or later.
---

# _SES_CONFIGURATION_DIAGNOSTIC_PAGE structure
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

TBD

## Syntax
````
typedef struct _SES_CONFIGURATION_DIAGNOSTIC_PAGE {
  UCHAR                    PageCode;
  UCHAR                    NumberOfSecondarySubEnclosures;
  UCHAR                    PageLength[2];
  UCHAR                    GenerationCode[4];
  SES_ENCLOSURE_DESCRIPTOR Descriptors[ANYSIZE_ARRAY];
} SES_CONFIGURATION_DIAGNOSTIC_PAGE, *PSES_CONFIGURATION_DIAGNOSTIC_PAGE;
````

## Members

        
            `Descriptors`

            Specifies the enclosure descriptors for the primary and secondary enclosures. The primary enclosure is the first index.
        
            `GenerationCode`

            Specifies the value of the generation code.
        
            `NumberOfSecondarySubEnclosures`

            Specifies the number of separate subenclosures included in
the enclosure descriptor list, not including the primary subenclosure. If this is set to zero, only the primary subenclosure exists.
        
            `PageCode`

            Specifies the diagnostic page being sent or requested based on the value. For a Microcode Control diagnostic page, the value should be 0x01.
        
            `PageLength`

            Specifies the length of the diagnostic page, in bytes.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | scsi.h (include Minitape.h, Storport.h) |