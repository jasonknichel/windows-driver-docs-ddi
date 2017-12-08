# Videoagp.h header


This header is used by Display. For more information, see
- [Display](../_display/index.md)

Videoagp.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [VideoPortGetAgpServices function](nf-videoagp-videoportgetagpservices.md) | The VideoPortGetAgpServices function is obsolete and is supported only for backward compatibility with existing drivers. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PAGP_COMMIT_PHYSICAL callback](nc-videoagp-pagp-commit-physical.md) | The AgpCommitPhysical function maps system (physical) memory to the specified range of AGP-decodable physical addresses. |
| [PAGP_COMMIT_VIRTUAL callback](nc-videoagp-pagp-commit-virtual.md) | The AgpCommitVirtual function maps reserved virtual memory to an associated range of AGP-decodable physical addresses. |
| [PAGP_FREE_PHYSICAL callback](nc-videoagp-pagp-free-physical.md) | The AgpFreePhysical function frees system memory that was committed by a previous call to AgpCommitPhysical. |
| [PAGP_FREE_VIRTUAL callback](nc-videoagp-pagp-free-virtual.md) | The AgpFreeVirtual function frees virtual memory committed by a previous call to AgpCommitVirtual. |
| [PAGP_RELEASE_PHYSICAL callback](nc-videoagp-pagp-release-physical.md) | The AgpReleasePhysical function frees a physical address range reserved by a previous call to AgpReservePhysical. |
| [PAGP_RELEASE_VIRTUAL callback](nc-videoagp-pagp-release-virtual.md) | The AgpReleaseVirtual function frees system memory reserved by a previous call to AgpReserveVirtual. |
| [PAGP_RESERVE_PHYSICAL callback](nc-videoagp-pagp-reserve-physical.md) | The AgpReservePhysical function reserves a range of physical addresses on the system bus to which the AGP controller can respond. |
| [PAGP_RESERVE_VIRTUAL callback](nc-videoagp-pagp-reserve-virtual.md) | The AgpReserveVirtual function reserves a range of virtual addresses for AGP. |
| [PAGP_SET_RATE callback](nc-videoagp-pagp-set-rate.md) | The AgpSetRate function reprograms the data transfer rate of the AGP chipset. |