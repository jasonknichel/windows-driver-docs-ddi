---
UID: NS.ntddcdrm._CDROM_SUB_Q_DATA_FORMAT
title: CDROM_SUB_Q_DATA_FORMAT
author: windows-driver-content
description: The CDROM_SUB_Q_DATA_FORMAT structure is used with device control IRPs of type IOCTL_CDROM_READ_Q_CHANNEL.
old-location: storage\cdrom_sub_q_data_format.htm
old-project: storage
ms.assetid: 0eac3cc1-9c1c-4438-ab20-51c65018cea0
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: CDROM_SUB_Q_DATA_FORMAT, CDROM_SUB_Q_DATA_FORMAT, *PCDROM_SUB_Q_DATA_FORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CDROM_SUB_Q_DATA_FORMAT
req.alt-loc: ntddcdrm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
---

# CDROM_SUB_Q_DATA_FORMAT structure



## -description
<p>The CDROM_SUB_Q_DATA_FORMAT structure is used with device control IRPs of type <a href="..\ntddcdrm\ni-ntddcdrm-ioctl-cdrom-read-q-channel.md">IOCTL_CDROM_READ_Q_CHANNEL</a>. </p>


## -syntax

````
typedef struct _CDROM_SUB_Q_DATA_FORMAT {
  UCHAR Format;
  UCHAR Track;
} CDROM_SUB_Q_DATA_FORMAT, *PCDROM_SUB_Q_DATA_FORMAT;
````


## -struct-fields
<dl>

### -field Format

<dd>
<p>Specifies which subset of the Q data the read operation should return, as follows: </p>
<p></p>
<dl>

### -field IOCTL_CDROM_CURRENT_POSITION 

<dd>
<p>Indicates that the read operation should return position information such as the track number, the index number, the absolute address, and the track relative address. If the IOCTL_CDROM_Q_CHANNEL device control IRP specifies this format, the information is returned in the <a href="..\ntddcdrm\ns-ntddcdrm--sub-q-current-position.md">SUB_Q_CURRENT_POSITION</a> member of the <a href="..\ntddcdrm\ns-ntddcdrm--sub-q-channel-data.md">SUB_Q_CHANNEL_DATA</a> structure.</p>
</dd>
</dl>
<p></p>
<dl>

### -field IOCTL_CDROM_MEDIA_CATALOG

<dd>
<p>Indicates that the read operation should return the media catalog number. If the IOCTL_CDROM_Q_CHANNEL device control IRP specifies this format, the information is returned in the <a href="..\ntddcdrm\ns-ntddcdrm--sub-q-media-catalog-number.md">SUB_Q_MEDIA_CATALOG_NUMBER</a> member of the <a href="..\ntddcdrm\ns-ntddcdrm--sub-q-channel-data.md">SUB_Q_CHANNEL_DATA</a> structure.</p>
</dd>
</dl>
<p></p>
<dl>

### -field IOCTL_CDROM_TRACK_ISRC

<dd>
<p>Indicates that the read operation should return the ISO/IEC 3901 Track International Standard Recording Code (ISRC). This code gives a unique number to an audio track. If the IOCTL_CDROM_Q_CHANNEL device control IRP specifies this format, the information is returned in the <a href="..\ntddcdrm\ns-ntddcdrm--sub-q-track-isrc.md">SUB_Q_TRACK_ISRC</a> member of the <a href="..\ntddcdrm\ns-ntddcdrm--sub-q-channel-data.md">SUB_Q_CHANNEL_DATA</a> structure.</p>
</dd>
</dl>
</dd>

### -field Track

<dd>
<p>Indicates the track number where the CD-ROM driver must read the Q subchannel data. If <b>Format</b> is set to IOCTL_CDROM_MEDIA_CATALOG, then the <b>Track</b> member must be set to zero.</p>
</dd>
</dl>

## -remarks
<p>The CDROM_SUB_Q_DATA_FORMAT structure indicates the track from which to read the Q part of the subchannel data and the format of the read.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddcdrm.h (include Ntddcdrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl-cdrom-read-q-channel.md">IOCTL_CDROM_READ_Q_CHANNEL</a>
</dt>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm--sub-q-channel-data.md">SUB_Q_CHANNEL_DATA</a>
</dt>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm--sub-q-current-position.md">SUB_Q_CURRENT_POSITION</a>
</dt>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm--sub-q-media-catalog-number.md">SUB_Q_MEDIA_CATALOG_NUMBER</a>
</dt>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm--sub-q-track-isrc.md">SUB_Q_TRACK_ISRC</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_SUB_Q_DATA_FORMAT structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>