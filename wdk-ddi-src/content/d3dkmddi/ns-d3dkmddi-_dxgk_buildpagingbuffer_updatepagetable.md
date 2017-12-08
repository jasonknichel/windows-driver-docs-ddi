---
UID: NS.D3DKMDDI._DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE
title: _DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE
author: windows-driver-content
description: DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE is used as part of a page table update operation.
old-location: display\dxgk_buildpagingbuffer_updatepagetable.htm
old-project: display
ms.assetid: 734B2E28-75F8-49AE-AAAB-EB0C037C6432
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE, DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE structure



## -description
<b>DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE</b> is used as part of a page table update operation.


## -syntax

````
typedef struct _DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE {
  UINT                        PageTableLevel;
  HANDLE                      hAllocation;
  DXGK_PAGETABLEUPDATEADDRESS PageTableAddress;
  DXGK_PTE                    *pPageTableEntries;
  UINT                        StartIndex;
  UINT                        NumPageTableEntries;
  UINT                        Reserved0;
  DXGK_UPDATEPAGETABLEFLAGS   Flags;
  UINT64                      DriverProtection;
  UINT64                      AllocationOffsetInBytes;
  HANDLE                      hProcess;
  DXGK_PAGETABLEUPDATEMODE    UpdateMode;
  DXGK_PTE                    *pPageTableEntries64KB;
  D3DGPU_VIRTUAL_ADDRESS      FirstPteVirtualAddress;
} DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE;
````


## -struct-fields

### -field PageTableLevel

Level of a page table, which is updated.

### -field hAllocation

Kernel mode driver handle of an allocation, which is mapped by the page table entries. The handle is returned by the kernel mode driver from <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>. The handle can be <b>NULL</b> for allocations, which do not have a kernel mode drver   handle (page tables, page directories, etc.).

### -field PageTableAddress

Address of the page table to update. If <b>DXGK_VIRTUALADDRESSCAPS:: PageTableUpdateMode</b> is <b>DXGK_PAGETABLEUPDATE_CPU_VIRTUAL</b>, the CPU virtual address is in the <b>CpuVirtual</b> field. If <b>DXGK_VIRTUALADDRESSCAPS:: PageTableUpdateMode</b> is <b>DXGK_PAGETABLEUPDATE_GPU_VIRTUAL</b>, the GPU virtual address is in the <b>GpuVirtual</b> field. If <b>DXGK_VIRTUALADDRESSCAPS:: PageTableUpdateMode</b> is <b>DXGK_PAGETABLEUPDATE_GPU_PHYSICAL</b>, the GPU physical address is in the <b>GpuPhysical</b> field.

### -field pPageTableEntries

The entries which need to be copied. The index zero in the <b>pPageTableEntries</b> array corresponds to the <b>StartIndex</b> in the driver page table entry array.

### -field StartIndex

The starting index of a page table entry within the page table where the entries should be copied. The page table entry array index is zero-based.

### -field NumPageTableEntries

The number of entries which need to be copied.

### -field Reserved0

This member is reserved and should be set to zero.

### -field Flags


<a href="display.dxgk_updatepagetableflags">DXGK_UPDATEPAGETABLEFLAGS</a> structure describing the update operation.

### -field DriverProtection

Passed by UMD in MapGpuVirtualAddressRangeCb.

### -field AllocationOffsetInBytes

When <b>hAllocation</b> is non-NULL, this field specifies the relative offset, in bytes, from the beginning of the allocation to the first page being targeted by this update operation. If the update target multiple pages from <b>hAllocation</b>, those pages are guaranteed to be sequential. For example, video memory manager may be updating a GPU virtual address to page 4,5,6,7 in <b>hAllocation</b>. There will never be a case where a driver would see a single update operation which target non sequential pages (ex. 4,5,7). Note that although the pages are guaranteed to be sequential from the point of view of the allocation, they may not be physically contiguous in memory.

### -field hProcess

Kernel mode driver process handle for the process whose page table entries are updated. This is the value returned from <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createprocess.md">DxgkDdiCreateProcess</a>.

### -field UpdateMode

Defines the meaning of <b>PageTableAddress</b>. When initializing page tables for the paging process, the update mode is always <b>DXGK_PAGETABLEUPDATE_CPU_VIRTUAL</b> and <b>pDmaBuffer</b> is set to <b>NULL</b>. In this case the driver must update page tables immediately. In other cases the <b>UpdateMode</b> is set to the value, which is specified in <b>DXGK_VIRTUALADDRESSCAPS::GpuMmu.PageTableUpdateMode</b>.
When updating page table entries for a leaf page table, video memory manager assumes that each entry covers a 4KB page. If a GPU page is bigger (4 KB * 2n), the video memory manager will provide entries in the array, which point within GPU pages. The kernel mode driver might only need to initialize page table entries, which point to the beginning of GPU pages. The following figure illustrates this for the case when GPU page is 16 KB.

### -field pPageTableEntries64KB

The entries which need to be copied from the 64KB page tables. The index zero in the <b>pPageTableEntries</b> array corresponds to the <b>StartIndex</b> in the driver page table entry array. The array should be use only when the <b>DXGK_GPUMMUCAPS::DualPteSupported</b> cap is set.

### -field FirstPteVirtualAddress

The GPU virtual address that is mapped by the first updated page table entry.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>