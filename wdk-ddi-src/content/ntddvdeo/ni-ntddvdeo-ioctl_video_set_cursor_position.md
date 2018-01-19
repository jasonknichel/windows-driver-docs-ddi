---
UID : NI:ntddvdeo.IOCTL_VIDEO_SET_CURSOR_POSITION
title : IOCTL_VIDEO_SET_CURSOR_POSITION
author : windows-driver-content
description : Sets the cursor position (row and column). Miniport drivers for VGA-compatible adapters are required to support this request, which is modal. It is optional for other miniport drivers.
old-location : display\ioctl_video_set_cursor_position.htm
old-project : display
ms.assetid : 80346b99-49f5-4cbf-b524-1c5f40cf441f
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS, TAPE_WRITE_MARKS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddvdeo.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_VIDEO_SET_CURSOR_POSITION
req.alt-loc : Ntddvdeo.h
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
req.typenames : "*PTAPE_WRITE_MARKS, TAPE_WRITE_MARKS"
---

# IOCTL_VIDEO_SET_CURSOR_POSITION IOCTL
Sets the cursor position (row and column). Miniport drivers for VGA-compatible adapters are required to support this request, which is modal. It is optional for other miniport drivers.



Sets the cursor position (row and column). Miniport drivers for VGA-compatible adapters are required to support this request, which is modal. It is optional for other miniport drivers.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The VRP <b>InputBuffer</b> contains the VIDEO_CURSOR_POSITION structure to be set.

### Input Buffer Length
<text></text>

### Output Buffer
None

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
The miniport driver does not set the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntddvdeo.h |
| **IRQL** |  |