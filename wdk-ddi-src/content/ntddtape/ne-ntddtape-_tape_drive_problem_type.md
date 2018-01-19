---
UID : NE:ntddtape._TAPE_DRIVE_PROBLEM_TYPE
title : _TAPE_DRIVE_PROBLEM_TYPE
author : windows-driver-content
description : The TAPE_DRIVE_PROBLEM_TYPE enumerator is used to report problems with the tape drive.
old-location : storage\tape_drive_problem_type.htm
old-project : storage
ms.assetid : c2732686-5f95-41fd-8e47-8acf6900a44b
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _TAPE_DRIVE_PROBLEM_TYPE, TAPE_DRIVE_PROBLEM_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntddtape.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : TAPE_DRIVE_PROBLEM_TYPE
req.alt-loc : ntddtape.h
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
req.typenames : TAPE_DRIVE_PROBLEM_TYPE
---

# _TAPE_DRIVE_PROBLEM_TYPE Enumeration
The TAPE_DRIVE_PROBLEM_TYPE enumerator is used to report problems with the tape drive.

## Syntax
````
typedef enum _TAPE_DRIVE_PROBLEM_TYPE { 
  TapeDriveProblemNone          = 0,
  TapeDriveReadWriteWarning     = 1,
  TapeDriveReadWriteError       = 2,
  TapeDriveReadWarning          = 3,
  TapeDriveWriteWarning         = 4,
  TapeDriveReadError            = 5,
  TapeDriveWriteError           = 6,
  TapeDriveHardwareError        = 7,
  TapeDriveUnsupportedMedia     = 8,
  TapeDriveScsiConnectionError  = 9,
  TapeDriveTimetoClean          = 10,
  TapeDriveCleanDriveNow        = 11,
  TapeDriveMediaLifeExpired     = 12,
  TapeDriveSnappedTape          = 13
} TAPE_DRIVE_PROBLEM_TYPE;
````

## Constants

<table>

<tr>
<td>TapeDriveCleanDriveNow</td>
<td>Indicates that the tape drive requires cleaning.</td>
</tr>

<tr>
<td>TapeDriveHardwareError</td>
<td>Indicates that the tape drive had a hardware error.</td>
</tr>

<tr>
<td>TapeDriveMediaLifeExpired</td>
<td>Indicates that the media life has expired. Media needs to be replaced.</td>
</tr>

<tr>
<td>TapeDriveProblemNone</td>
<td>Indicates that there is no tape drive problem.</td>
</tr>

<tr>
<td>TapeDriveReadError</td>
<td>Indicates that the tape drive is having problems doing reads. This is a severe error.</td>
</tr>

<tr>
<td>TapeDriveReadWarning</td>
<td>Indicates that the tape drive is having problems doing reads. This is a warning.</td>
</tr>

<tr>
<td>TapeDriveReadWriteError</td>
<td>Indicates that the tape drive is having problems doing reads or writes. This is a severe error.</td>
</tr>

<tr>
<td>TapeDriveReadWriteWarning</td>
<td>Indicates that the tape drive is having problems doing reads or writes. This is a warning.</td>
</tr>

<tr>
<td>TapeDriveScsiConnectionError</td>
<td>Indicates that there is a SCSI cable or connection error.</td>
</tr>

<tr>
<td>TapeDriveSnappedTape</td>
<td>Indicates that the tape has snapped.</td>
</tr>

<tr>
<td>TapeDriveTimetoClean</td>
<td>Indicates that the tape drive requires cleaning.</td>
</tr>

<tr>
<td>TapeDriveUnsupportedMedia</td>
<td>Indicates that the media format is not supported.</td>
</tr>

<tr>
<td>TapeDriveWriteError</td>
<td>Indicates that the tape drive is having problems doing writes. This is a severe error.</td>
</tr>

<tr>
<td>TapeDriveWriteWarning</td>
<td>Indicates that the tape drive is having problems doing writes. This is a warning.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddtape.h |

## See Also

<dl>
<dt>
<a href="..\ntddtape\ns-ntddtape-_tape_wmi_operations.md">TAPE_WMI_OPERATIONS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567957">TapeMiniWMIControl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TAPE_DRIVE_PROBLEM_TYPE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>