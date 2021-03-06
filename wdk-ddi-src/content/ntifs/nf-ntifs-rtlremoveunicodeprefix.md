---
UID: NF:ntifs.RtlRemoveUnicodePrefix
title: RtlRemoveUnicodePrefix function
author: windows-driver-content
description: The RtlRemoveUnicodePrefix routine removes an element from a prefix table.
old-location: ifsk\rtlremoveunicodeprefix.htm
old-project: ifsk
ms.assetid: b2f996b1-0c1a-4ad5-a4c4-5d84ca94c5a1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlRemoveUnicodePrefix, RtlRemoveUnicodePrefix routine [Installable File System Drivers], ifsk.rtlremoveunicodeprefix, ntifs/RtlRemoveUnicodePrefix, rtlref_a6eb361a-f00b-4377-913c-8494c49d4064.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: Windows Server 2003
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlRemoveUnicodePrefix
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlRemoveUnicodePrefix function


## -description


The <b>RtlRemoveUnicodePrefix</b> routine removes an element from a prefix table. 


## -parameters




### -param PrefixTable [in]

Pointer to the prefix table. The table must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff553015">RtlInitializeUnicodePrefix</a>.


### -param PrefixTableEntry [in]

Pointer to the prefix table element to be deleted. 


## -returns



None




## -remarks



File systems must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff553015">RtlInitializeUnicodePrefix</a> to initialize the prefix table before using any other <b>Rtl..UnicodePrefix</b> routines on it. The initialized prefix table structure should be considered opaque.

Callers of the <b>Rtl..UnicodePrefix</b> routines are responsible for synchronizing access to the prefix table. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552272">RtlFindUnicodePrefix</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553015">RtlInitializeUnicodePrefix</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553038">RtlInsertUnicodePrefix</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553123">RtlNextUnicodePrefix</a>
 

 

