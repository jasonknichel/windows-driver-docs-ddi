# Winsmcrd.h header


This header is used by Smart Card Reader Devices, Near field communications (NFC). For more information, see
- [Smart Card Reader Devices](../_smartcrd/index.md)
- [Near field communications (NFC)](../_nfpdrivers/index.md)

Winsmcrd.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [SCARD_IO_REQUEST structure](ns-winsmcrd--scard-io-request.md) | This structure is used to identify a smart card I/O request. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_SMARTCARD_EJECT IOCTL](ni-winsmcrd-ioctl-smartcard-eject.md) | The IOCTL_SMARTCARD_EJECT request ejects the currently inserted smart card from the smart card reader. |
| [IOCTL_SMARTCARD_GET_ATTRIBUTE IOCTL](ni-winsmcrd-ioctl-smartcard-get-attribute.md) | The IOCTL_SMARTCARD_GET_ATTRIBUTE control code queries for smart card attribues. |
| [IOCTL_SMARTCARD_GET_LAST_ERROR IOCTL](ni-winsmcrd-ioctl-smartcard-get-last-error.md) | The IOCTL_SMARTCARD_GET_LAST_ERROR request retrieves the error code of the most previous operation because there is no option to return an error code immediately after an overlapped operation is complete. |
| [IOCTL_SMARTCARD_GET_STATE IOCTL](ni-winsmcrd-ioctl-smartcard-get-state.md) | The IOCTL_SMARTCARD_GET_STATE control code gets the current status of the smart card. |
| [IOCTL_SMARTCARD_IS_ABSENT IOCTL](ni-winsmcrd-ioctl-smartcard-is-absent.md) | The IOCTL_SMARTCARD_IS_ABSENT control code returns immediately with STATUS_SUCCESS if no smart card is currently detected. |
| [IOCTL_SMARTCARD_IS_PRESENT IOCTL](ni-winsmcrd-ioctl-smartcard-is-present.md) | The IOCTL_SMARTCARD_IS_PRESENT control code detects whether a smart card is currently detected. |
| [IOCTL_SMARTCARD_POWER IOCTL](ni-winsmcrd-ioctl-smartcard-power.md) | Windows may require a driver to have this IOCTL to be NOP and return success. |
| [IOCTL_SMARTCARD_SET_ATTRIBUTE IOCTL](ni-winsmcrd-ioctl-smartcard-set-attribute.md) | The IOCTL_SMARTCARD_SET_ATTRIBUTE control code sets an attribute and returns STATUS_SUCCESS on SCARD_ATTR_DEVICE_IN_USE; otherwise, it returns STATUS_NOT_SUPPORTED. |
| [IOCTL_SMARTCARD_SET_PROTOCOL IOCTL](ni-winsmcrd-ioctl-smartcard-set-protocol.md) | Sets the procotol the driver communicates to the smart card with after the card is detected. |
| [IOCTL_SMARTCARD_SWALLOW IOCTL](ni-winsmcrd-ioctl-smartcard-swallow.md) | The IOCTL_SMARTCARD_SWALLOW request causes the smart card reader to swallow the card. |
| [IOCTL_SMARTCARD_TRANSMIT IOCTL](ni-winsmcrd-ioctl-smartcard-transmit.md) | Transmits data from the client to the detected smart card in ISO7816-4 compliant APDU. |