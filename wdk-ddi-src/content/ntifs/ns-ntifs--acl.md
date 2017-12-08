---
UID: NS.ntifs._ACL
title: ACL
author: windows-driver-content
description: The ACL structure is the header of an access-control list (ACL). A complete ACL consists of an ACL structure followed by an ordered list of zero or more access-control entries (ACE).
old-location: ifsk\acl.htm
old-project: ifsk
ms.assetid: dac27df2-fabd-4402-8daf-9317888dd30b
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: ACL,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ACL
req.alt-loc: ntifs.h
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

# ACL structure



## -description
<p>The ACL structure is the header of an access-control list (ACL). A complete ACL consists of an ACL structure followed by an ordered list of zero or more access-control entries (ACE). </p>


## -syntax

````
typedef struct _ACL {
  UCHAR  AclRevision;
  UCHAR  Sbz1;
  USHORT AclSize;
  USHORT AceCount;
  USHORT Sbz2;
} ACL, *PACL;
````


## -struct-fields
<dl>

### -field AclRevision

<dd>
<p>Revision level of the ACL. </p>
<p><b>Microsoft Windows NT 4.0 and earlier:</b> This value must be ACL_REVISION. </p>
<p><b>Microsoft Windows 2000 and later:</b> This value can be ACL_REVISION or ACL_REVISION_DS. It must be ACL_REVISION_DS if the ACL contains an object-specific ACE. </p>
</dd>

### -field Sbz1

<dd>
<p>A zero byte of padding that aligns the <b>AclRevision</b> member on a 16-bit boundary. </p>
</dd>

### -field AclSize

<dd>
<p>Size, in bytes, of the ACL. This value includes both the ACL structure and all the ACEs. </p>
</dd>

### -field AceCount

<dd>
<p>Number of ACEs stored in the ACL. </p>
</dd>

### -field Sbz2

<dd>
<p>Two zero bytes of padding that align the ACL structure on a 32-bit boundary. </p>
</dd>
</dl>

## -remarks
<p>An ACL includes a sequential list of zero or more ACEs. The individual ACEs in an ACL are numbered from 0 to <i>n</i>, where <i>n</i>+1 is the number of ACEs in the ACL. When editing an ACL, a driver refers to an ACE within the ACL by its index. </p>

<p>There are two types of ACL: discretionary and system. </p>

<p>A discretionary ACL (DACL) is controlled by the owner of an object or anyone granted WRITE_DAC access to the object. It specifies the access particular users and groups can have to an object. For example, the owner of a file can use a DACL to control which users and groups can and cannot have access to the file. </p>

<p>An object may also have system-level security information associated with it, in the form of a system ACL (SACL) controlled by a system administrator. A SACL can allow the system administrator to audit any attempts to gain access to an object. </p>

<p>Three ACE structures are currently defined: </p>

<p>ACCESS_ALLOWED_ACE</p>

<p>Grants specified rights to a user or group. This ACE is stored in a DACL.</p>

<p>ACCESS_DENIED_ACE</p>

<p>Denies specified rights to a user or group. This ACE is stored in a DACL.</p>

<p>SYSTEM_AUDIT_ACE</p>

<p>Specifies what types of access will cause system-level audits. This ACE is stored in a SACL.</p>

<p>A fourth ACE structure, SYSTEM_ALARM_ACE, is not currently supported. </p>

<p>The ACL structure is to be treated as though it were opaque, and drivers should not attempt to work with its members directly. To ensure that ACLs are semantically correct, drivers can use the functions listed in the See Also section to create and manipulate ACLs. </p>

<p>ACL and ACE structures must be aligned on 32-bit boundaries. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntifs\ns-ntifs--access-allowed-ace.md">ACCESS_ALLOWED_ACE</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs--access-denied-ace.md">ACCESS_DENIED_ACE</a>
</dt>
<dt>
<a href="ifsk.ace">ACE</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtladdaccessallowedace.md">RtlAddAccessAllowedAce</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlcreateacl.md">RtlCreateAcl</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlgetace.md">RtlGetAce</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlsetdaclsecuritydescriptor.md">RtlSetDaclSecurityDescriptor</a>
</dt>
<dt>
<a href="ifsk.system_alarm_ace">SYSTEM_ALARM_ACE</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs--system-audit-ace.md">SYSTEM_AUDIT_ACE</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs--token-default-dacl.md">TOKEN_DEFAULT_DACL</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20ACL structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>