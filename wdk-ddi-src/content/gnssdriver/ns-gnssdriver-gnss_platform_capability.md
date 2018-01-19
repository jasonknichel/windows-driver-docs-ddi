---
UID : NS:gnssdriver.GNSS_PLATFORM_CAPABILITY
title : GNSS_PLATFORM_CAPABILITY
author : windows-driver-content
description : This structure is used to communicate the platform/HLOS capabilities to the underlying GNSS driver.
old-location : sensors\gnss_platform_capability.htm
old-project : sensors
ms.assetid : A97DE517-26ED-452F-9066-94F73BC47BDE
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : GNSS_PLATFORM_CAPABILITY, GNSS_PLATFORM_CAPABILITY, *PGNSS_PLATFORM_CAPABILITY
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : gnssdriver.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : GNSS_PLATFORM_CAPABILITY
req.alt-loc : gnssdriver.h
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
req.typenames : GNSS_PLATFORM_CAPABILITY, *PGNSS_PLATFORM_CAPABILITY
---

# GNSS_PLATFORM_CAPABILITY structure
This structure is used to communicate the platform/HLOS capabilities to the underlying GNSS driver.

## Syntax
````
typedef struct {
  ULONG Size;
  ULONG Version;
  BOOL  SupportAgnssInjection;
  ULONG AgnssFormatSupported;
  BOOL  Reserved;
  BYTE  Unused[512];
} GNSS_PLATFORM_CAPABILITY, *PGNSS_PLATFORM_CAPABILITY;
````

## Members

        
            `AgnssFormatSupported`

            Specifies a bitmask containing the different AGNSS formats (GNSS_AGNSSFORMAT_*) that the GNSS driver or device supports.
        
            `Size`

            Structure size.
        
            `SupportAgnssInjection`

            Indicates that the platform supports AGNSS injection via the location platform.
        
            `Version`

            Version number.

    ## Remarks
        This is a list of individual capability support of the GNSS adapter. The platform capability is represented in the same way as the device capabilities are represented.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | gnssdriver.h |