---
UID: NS.ksmedia.PKSPROPERTY_TUNER_FREQUENCY_S
title: PKSPROPERTY_TUNER_FREQUENCY_S
author: windows-driver-content
description: The KSPROPERTY_TUNER_FREQUENCY_S structure describes the frequency of a TV or radio tuner device.
old-location: stream\ksproperty_tuner_frequency_s.htm
old-project: stream
ms.assetid: 19d2c3cc-69e3-4216-9eb7-32b522fe058b
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSPROPERTY_TUNER_FREQUENCY_S, KSPROPERTY_TUNER_FREQUENCY_S, *PKSPROPERTY_TUNER_FREQUENCY_S
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
req.alt-api: KSPROPERTY_TUNER_FREQUENCY_S
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

# PKSPROPERTY_TUNER_FREQUENCY_S structure



## -description
<p>The KSPROPERTY_TUNER_FREQUENCY_S structure describes the frequency of a TV or radio tuner device.</p>


## -syntax

````
typedef struct {
  KSPROPERTY Property;
  ULONG      Frequency;
  ULONG      LastFrequency;
  ULONG      TuningFlags;
  ULONG      VideoSubChannel;
  ULONG      AudioSubChannel;
  ULONG      Channel;
  ULONG      Country;
} KSPROPERTY_TUNER_FREQUENCY_S, *PKSPROPERTY_TUNER_FREQUENCY_S;
````


## -struct-fields
<dl>

### -field Property

<dd>
<p>Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.</p>
</dd>

### -field Frequency

<dd>
<p>Specifies the frequency of the tuner. If the request is a Get request, the minidriver returns the current frequency of the tuner. If the request is a Set request, the minidriver should set the frequency of the tuner to the specified value. This value is specified in hertz (Hz).</p>
</dd>

### -field LastFrequency

<dd>
<p>Specifies the last frequency tuned.</p>
</dd>

### -field TuningFlags

<dd>
<p>Specifies tuning flags that describe the granularity of a tuning operation. If the request is a Get request, the minidriver returns the current tuning flags. If the request is a Set request, the minidriver should use the specified tuning method. This member must be set to one of the values from the <a href="..\ksmedia\ne-ksmedia-ks-tuner-tuning-flags.md">KS_TUNER_TUNING_FLAGS</a> enumeration.</p>
</dd>

### -field VideoSubChannel

<dd>
<p>Specifies the video subchannel of a digital television source. If the request is a Get request, the minidriver should return the video subchannel for the digital television source to the specified value. If the request is a Set request, the minidriver should set the video subchannel for the digital television source. This member is only used by devices that support the DSS tuner mode (KSPROPERTY_TUNER_MODE_DSS).</p>
</dd>

### -field AudioSubChannel

<dd>
<p>Specifies the audio subchannel of a digital television source. If the request is a Get request, the minidriver should return the audio subchannel for the digital television source. If the request is a Set request, the minidriver should set the audio subchannel for the digital television source. This member is only used by devices that support the DSS tuner mode (KSPROPERTY_TUNER_MODE_DSS).</p>
</dd>

### -field Channel

<dd>
<p>Specifies the video subchannel of a digital television source. If the request is a Get request, the minidriver should return the video subchannel for the digital television source to the specified value. If the request is a Set request, the minidriver should set the video subchannel for the digital television source. This member is only used by devices that support the DSS tuner mode (KSPROPERTY_TUNER_MODE_DSS).</p>
</dd>

### -field Country

<dd>
<p>Specifies the current country code for the tuning operation. Country codes follow the Telephony API (TAPI) region code values that correspond to the international long distance dialing codes. </p>
</dd>
</dl>

## -remarks


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
<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>
</dt>
<dt>
<a href="..\ksmedia\ne-ksmedia-ks-tuner-tuning-flags.md">KS_TUNER_TUNING_FLAGS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567800">PROPSETID_TUNER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565833">KSPROPERTY_TUNER_FREQUENCY</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_TUNER_FREQUENCY_S structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>