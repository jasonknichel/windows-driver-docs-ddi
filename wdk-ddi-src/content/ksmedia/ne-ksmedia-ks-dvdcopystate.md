---
UID: NE.ksmedia.KS_DVDCOPYSTATE
title: KS_DVDCOPYSTATE
author: windows-driver-content
description: The KS_DVDCOPYSTATE enumeration describes the progress of the DVD copyright protection initialization, authentication and key negotiation sequence.
old-location: stream\ks_dvdcopystate.htm
old-project: stream
ms.assetid: 4072eaf1-d4cc-4255-90c1-177d6d58bb0a
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSIDEFAULTCLOCK, KSIDEFAULTCLOCK, *PKSIDEFAULTCLOCK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KS_DVDCOPYSTATE
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

# KS_DVDCOPYSTATE enumeration



## -description
<p>The KS_DVDCOPYSTATE enumeration describes the progress of the DVD copyright protection initialization, authentication and key negotiation sequence.</p>


## -syntax

````
typedef enum  { 
  KS_DVDCOPYSTATE_INITIALIZE                   = 0,
  KS_DVDCOPYSTATE_INITIALIZE_TITLE             = 1,
  KS_DVDCOPYSTATE_AUTHENTICATION_NOT_REQUIRED  = 2,
  KS_DVDCOPYSTATE_AUTHENTICATION_REQUIRED      = 3,
  KS_DVDCOPYSTATE_DONE                         = 4
} KS_DVDCOPYSTATE;
````


## -enum-fields
<dl>

### -field KS_DVDCOPYSTATE_INITIALIZE

<dd>
<p>Indicates that the full copyright protection sequence is starting.</p>
</dd>

### -field KS_DVDCOPYSTATE_INITIALIZE_TITLE

<dd>
<p>Indicates that a title key copyright protection sequence is starting.</p>
</dd>

### -field KS_DVDCOPYSTATE_AUTHENTICATION_NOT_REQUIRED

<dd>
<p>Indicates that no authentication is required.</p>
</dd>

### -field KS_DVDCOPYSTATE_AUTHENTICATION_REQUIRED

<dd>
<p>Indicates that authentication is required.</p>
</dd>

### -field KS_DVDCOPYSTATE_DONE

<dd>
<p>Indicates that the copyright protection sequence is complete.</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565147">KSPROPERTY_DVDCOPY_SET_COPY_STATE</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia--ks-dvdcopy-set-copy-state.md">KS_DVDCOPY_SET_COPY_STATE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DVDCOPYSTATE enumeration%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>