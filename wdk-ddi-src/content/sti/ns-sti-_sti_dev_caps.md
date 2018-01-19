---
UID : NS:sti._STI_DEV_CAPS
title : _STI_DEV_CAPS
author : windows-driver-content
description : The STI_DEV_CAPS structure is used as a parameter to the IStiDevice::GetCapabilities method. It is also a member of the STI_DEVICE_INFORMATION and STI_WIA_DEVICE_INFORMATION structures.
old-location : image\sti_dev_caps.htm
old-project : image
ms.assetid : 99e0f896-19d2-4895-8b01-deaf30ec5fe9
ms.author : windowsdriverdev
ms.date : 1/17/2018
ms.keywords : _STI_DEV_CAPS, STI_DEV_CAPS, *PSTI_DEV_CAPS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : sti.h
req.include-header : Sti.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : STI_DEV_CAPS
req.alt-loc : sti.h
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
req.typenames : STI_DEV_CAPS, *PSTI_DEV_CAPS
req.product : Windows 10 or later.
---

# _STI_DEV_CAPS structure
The STI_DEV_CAPS structure is used as a parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543745">IStiDevice::GetCapabilities</a> method. It is also a member of the <a href="..\sti\ns-sti-_sti_device_informationw.md">STI_DEVICE_INFORMATION</a> and <a href="..\sti\ns-sti-_sti_wia_device_informationw.md">STI_WIA_DEVICE_INFORMATION</a> structures.

## Syntax
````
typedef struct _STI_DEV_CAPS {
  DWORD dwGeneric;
} STI_DEV_CAPS, *PSTI_DEV_CAPS;
````

## Members

        
            `dwGeneric`

            Contains bit flags identifying device capabilities. The following flags are defined.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | sti.h (include Sti.h) |