# Smart Card Reader Devices

Overview of the Smart Card Reader Devices technology.

To develop Smart Card Reader Devices, you need these headers:

 * [smclib.h](..\smclib\index.md)
 * [winsmcrd.h](..\winsmcrd\index.md)

For the programming guide, see [Smart Card Reader Devices](===404===https://docs.microsoft.com/en-us/windows-hardware/drivers/smartcrd).

## Structures

| Title   | Description   |
| ---- |:---- |
| [CLOCK_RATE_CONVERSION structure](..\smclib\ns-smclib--clock-rate-conversion.md) | The CLOCK_RATE_CONVERSION structure holds a value that determines the duration of a bit of data and the corresponding maximum operating frequency that accompanies the indicated bit length. |
| [PTS_DATA structure](..\smclib\ns-smclib--pts-data.md) | The PTS_DATA structure is used for protocol type selection (PTS). |
| [SCARD_CARD_CAPABILITIES structure](..\smclib\ns-smclib--scard-card-capabilities.md) | The SCARD_CARD_CAPABILITIES structure declaration defines the data that is stored in the CardCapabilites member of the SMARTCARD_EXTENSION structure and holds all information that is specific to the particular smart card that is currently used. |
| [SCARD_READER_CAPABILITIES structure](..\smclib\ns-smclib--scard-reader-capabilities.md) | The SCARD_READER_CAPABILITIES structure holds state information about the smart card reader. |
| [SMARTCARD_EXTENSION structure](..\smclib\ns-smclib--smartcard-extension.md) | The SMARTCARD_EXTENSION structure is used by both the smart card reader driver and the smart card driver library to access all other smart card data structures. |
| [SMARTCARD_EXTENSION structure](..\smclib\ns-smclib--smartcard-extension~r1.md) | The SMARTCARD_EXTENSION structure is used by both the smart card reader driver and the smart card driver library to access all other smart card data structures. |
| [SMARTCARD_REPLY structure](..\smclib\ns-smclib--smartcard-reply.md) | Describes the reply buffer received from the smart card. |
| [SMARTCARD_REQUEST structure](..\smclib\ns-smclib--smartcard-request.md) | Describes the request buffer that contains data to send to the card. |
| [T0_DATA structure](..\smclib\ns-smclib--t0-data.md) | The T0_DATA structure is used by the smart card driver library to process T0 I/O. |
| [T1_DATA structure](..\smclib\ns-smclib--t1-data.md) | The T1_DATA structure is used by the smart card driver library to process T1 I/O. |
| [VENDOR_ATTR structure](..\smclib\ns-smclib--vendor-attr.md) | The VENDOR_ATTR structure defines the data that is stored in the VendorAttr member of the SMARTCARD_EXTENSION structure. VENDOR_ATTR also holds information that identifies the smart card reader, such as the vendor name, unit number, and serial number. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_SMARTCARD_EJECT IOCTL](..\winsmcrd\ni-winsmcrd-ioctl-smartcard-eject.md) | The IOCTL_SMARTCARD_EJECT request ejects the currently inserted smart card from the smart card reader. |
| [IOCTL_SMARTCARD_GET_LAST_ERROR IOCTL](..\winsmcrd\ni-winsmcrd-ioctl-smartcard-get-last-error.md) | The IOCTL_SMARTCARD_GET_LAST_ERROR request retrieves the error code of the most previous operation because there is no option to return an error code immediately after an overlapped operation is complete. |
| [IOCTL_SMARTCARD_SWALLOW IOCTL](..\winsmcrd\ni-winsmcrd-ioctl-smartcard-swallow.md) | The IOCTL_SMARTCARD_SWALLOW request causes the smart card reader to swallow the card. |