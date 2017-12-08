---
UID: NS.ksmedia.PKSAUDIO_MIC_ARRAY_GEOMETRY
title: PKSAUDIO_MIC_ARRAY_GEOMETRY
author: windows-driver-content
description: The KSAUDIO_MIC_ARRAY_GEOMETRY structure specifies the type and the geometry of the microphone array.
old-location: audio\ksaudio_mic_array_geometry.htm
old-project: audio
ms.assetid: 49b8f602-8f82-4445-98f2-a63563689561
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSAUDIO_MIC_ARRAY_GEOMETRY, KSAUDIO_MIC_ARRAY_GEOMETRY, *PKSAUDIO_MIC_ARRAY_GEOMETRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSAUDIO_MIC_ARRAY_GEOMETRY
req.alt-loc: ksmedia.h
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

# PKSAUDIO_MIC_ARRAY_GEOMETRY structure



## -description
<p>The KSAUDIO_MIC_ARRAY_GEOMETRY structure specifies the type and the geometry of the microphone array. The <b>usNumberOfMicrophones</b> member indicates the number of microphones in the physical array. The KsMicCoord member is a variable of type <a href="audio.ksaudio_microphone_coordinates">KSAUDIO_MICROPHONE_COORDINATES</a> and it is an array of structures. The number of entries in this array is given by the value of the <b>usNumberOfMicrophones</b> member.</p>


## -syntax

````
typedef struct {
  USHORT                         usVersion;
  USHORT                         usMicArrayType;
  SHORT                          wVerticalAngleBegin;
  SHORT                          wVerticalAngleEnd;
  SHORT                          wHorizontalAngleBegin;
  SHORT                          wHorizontalAngleEnd;
  USHORT                         usFrequencyBandLo;
  USHORT                         usFrequencyBandHi;
  USHORT                         usNumberOfMicrophones;
  KSAUDIO_MICROPHONE_COORDINATES KsMicCoord[1];
} KSAUDIO_MIC_ARRAY_GEOMETRY, *PKSAUDIO_MIC_ARRAY_GEOMETRY;
````


## -struct-fields
<dl>

### -field usVersion

<dd>
<p>Specifies the version number of the KSAUDIO_MIC_ARRAY_GEOMETRY structure. This member is a BCD value and is currently set to 0x0100, which represents a version number of 1.0.</p>
</dd>

### -field usMicArrayType

<dd>
<p>Specifies the type of microphone array in use. This member can be any one of the KSMICARRAY_MICARRAYTYPE enumeration values shown in the following table.</p>
<table>
<tr>
<td>
<p><b>Value</b></p>
</td>
<td>
<p><b>Microphone array type</b></p>
</td>
</tr>
<tr>
<td>
<p>KSMICARRAY_MICARRAYTYPE_LINEAR</p>
</td>
<td>
<p>Linear</p>
</td>
</tr>
<tr>
<td>
<p>KSMICARRAY_MICARRAYTYPE_PLANAR</p>
</td>
<td>
<p>Planar</p>
</td>
</tr>
<tr>
<td>
<p>KSMICARRAY_MICARRAYTYPE_3D</p>
</td>
<td>
<p>3D</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field wVerticalAngleBegin

<dd>
<p>Specifies the vertical angle of the start of the working volume of the microphone array.</p>
</dd>

### -field wVerticalAngleEnd

<dd>
<p>Specifies the vertical angle of the end of the working volume of the microphone array.</p>
</dd>

### -field wHorizontalAngleBegin

<dd>
<p>Work Volume HorizontalAngle Begin</p>
</dd>

### -field wHorizontalAngleEnd

<dd>
<p>Work Volume HorizontalAngle End</p>
</dd>

### -field usFrequencyBandLo

<dd>
<p>Specifies the low end of the frequency range for the microphone array.</p>
</dd>

### -field usFrequencyBandHi

<dd>
<p>Specifies the high end of the frequency range for the microphone array.</p>
</dd>

### -field usNumberOfMicrophones

<dd>
<p>Specifies the number of microphones in the microphone array.</p>
</dd>

### -field KsMicCoord

<dd>
<p>Specifies the array of KSAUDIO_MICROPHONE_COORDINATES structures that contains the locations of the microphones in the array.</p>
</dd>
</dl>

## -remarks
<p>All angle values are expressed in units of 1/10000th of a radian. For example, 3.1416 radians is expressed as 31416 units. Acceptable values range from -31416 to 31416 units.</p>

<p>All coordinate values are expressed in millimeters. Acceptable values range from -32768 to 32767, inclusive.</p>

<p>Frequency values are expressed in Hertz (Hz).</p>

<p>For more information about how to process a microphone array in Windows Vista, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=8751">Audio Technologies for Windows </a> page on the WHDC website and refer to the following white papers:</p>

<p><a href="http://go.microsoft.com/fwlink/p/?linkid=120592">Microphone Array Support in Windows Vista</a></p>

<p><a href="http://go.microsoft.com/fwlink/p/?linkid=120593">How to Build and Use Microphone Arrays for Windows Vista</a></p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ksmedia.h (include Ksmedia.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="audio.ksaudio_microphone_coordinates">KSAUDIO_MICROPHONE_COORDINATES</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSAUDIO_MIC_ARRAY_GEOMETRY structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>