---
UID : NS:bdatypes._BDA_WMDRM_KEYINFOLIST
title : _BDA_WMDRM_KEYINFOLIST
author : windows-driver-content
description : .
old-location : stream\bda_wmdrm_keyinfolist.htm
old-project : stream
ms.assetid : 0A151425-C22F-4201-855F-FF6FECE611D7
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : _BDA_WMDRM_KEYINFOLIST, BDA_WMDRM_KEYINFOLIST, *PBDA_WMDRM_KEYINFOLIST
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : bdatypes.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : BDA_WMDRM_KEYINFOLIST
req.alt-loc : Bdatypes.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : BDA_WMDRM_KEYINFOLIST, *PBDA_WMDRM_KEYINFOLIST
---

# _BDA_WMDRM_KEYINFOLIST structure


## Syntax
````
typedef struct _BDA_WMDRM_KEYINFOLIST {
  PBDARESULT lResult;
  ULONG      ulKeyuuidBufferLen;
  GUID       argKeyuuidBuffer[MIN_DIMENSION];
} BDA_WMDRM_KEYINFOLIST, *PBDA_WMDRM_KEYINFOLIST;
````

## Members

        
            `argKeyuuidBuffer`

            
        
            `lResult`

            
        
            `ulKeyuuidBufferLen`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bdatypes.h |