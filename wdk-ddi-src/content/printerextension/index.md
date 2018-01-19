---
UID : NA:printerextension
ms.assetid : 39fec125-0979-3b7b-9916-abfd53378c86
ms.author : windowsdriverdev
ms.date : 01/18/18
ms.keywords : 
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : portal
---

# printerextension.h header



printerextension.h contains the following programming interfaces:



## Interfaces
| Title | Description |
| ---- |:---- |
| [IPrinterBidiSetRequestCallback](nn-printerextension-iprinterbidisetrequestcallback.md) | Describes the signature of the callback object that receives the Bidi response. |
| [IPrinterExtensionAsyncOperation](nn-printerextension-iprinterextensionasyncoperation.md) | Provides the context associated with an asynchronous operation. |
| [IPrinterExtensionContext](nn-printerextension-iprinterextensioncontext.md) | Represents the context for the activation of a UWP device app for printers. |
| [IPrinterExtensionContextCollection](nn-printerextension-iprinterextensioncontextcollection.md) | Exposes a collection of IPrinterExtensionContext objects. |
| [IPrinterExtensionEventArgs](nn-printerextension-iprinterextensioneventargs.md) | Represents the context for the desktop printer extension activation. |
| [IPrinterExtensionRequest](nn-printerextension-iprinterextensionrequest.md) | Completes the given extension event with either a cancellation or success. |
| [IPrinterPropertyBag](nn-printerextension-iprinterpropertybag.md) | Provides strongly-typed get and set methods. |
| [IPrinterQueue](nn-printerextension-iprinterqueue.md) | Represents a single printer queue. |
| [IPrinterQueue2](nn-printerextension-iprinterqueue2.md) | Represents a single printer queue. |
| [IPrinterQueueEvent](nn-printerextension-iprinterqueueevent.md) | Provides the event delegate for printer queue events. |
| [IPrinterQueueView](nn-printerextension-iprinterqueueview.md) | Provides a way to change the range of print jobs being monitored. |
| [IPrinterQueueViewEvent](nn-printerextension-iprinterqueueviewevent.md) | Provides the signature of the event handler. |
| [IPrinterScriptablePropertyBag](nn-printerextension-iprinterscriptablepropertybag.md) | The IPrinterScriptablePropertyBag interface is the property bag interface passed to script clients. |
| [IPrinterScriptablePropertyBag2](nn-printerextension-iprinterscriptablepropertybag2.md) | . |
| [IPrinterScriptableStream](nn-printerextension-iprinterscriptablestream.md) | The IPrinterScriptableStream interface builds on IPrinterScriptableSequentialStream and adds IStream-like semantics. |
| [IPrinterScriptContext](nn-printerextension-iprinterscriptcontext.md) | Passed to all third-party constraints JavaScript functions, and provides access to relevant objects. |
| [IPrintJob](nn-printerextension-iprintjob.md) | Contains properties that represent a print job. |
| [IPrintJobCollection](nn-printerextension-iprintjobcollection.md) | This interfaces provides an enumeration of the jobs in the print queue. |
| [IPrintSchemaAsyncOperation](nn-printerextension-iprintschemaasyncoperation.md) | Represents an asynchronous operation context for validation, merge or commit operations. |
| [IPrintSchemaAsyncOperationEvent](nn-printerextension-iprintschemaasyncoperationevent.md) | Exposes a validation, merge, or commit completion event delegate. |
| [IPrintSchemaCapabilities](nn-printerextension-iprintschemacapabilities.md) | Provides the primary method to access PrintCapabilities. |
| [IPrintSchemaCapabilities2](nn-printerextension-iprintschemacapabilities2.md) | The IPrintSchemaCapabilities2 interface represents an extension to the IPrintSchemaCapabilities object, which provides wrapper methods over a print capabilities document. |
| [IPrintSchemaDisplayableElement](nn-printerextension-iprintschemadisplayableelement.md) | Provides the displayable string for a PrintCapabilites PrintSchema element. |
| [IPrintSchemaElement](nn-printerextension-iprintschemaelement.md) | Provides access to the underlying XML node and &#0034;name&#0034; attribute information for a Print Schema element. |
| [IPrintSchemaFeature](nn-printerextension-iprintschemafeature.md) | Exposes a Print Schema Feature element. |
| [IPrintSchemaNUpOption](nn-printerextension-iprintschemanupoption.md) | Exposes a Print Schema NUp Option element. |
| [IPrintSchemaOption](nn-printerextension-iprintschemaoption.md) | Exposes a Print Schema Option object. |
| [IPrintSchemaOptionCollection](nn-printerextension-iprintschemaoptioncollection.md) | Exposes a collection of IPrintSchemaOption objects. |
| [IPrintSchemaPageImageableSize](nn-printerextension-iprintschemapageimageablesize.md) | Exposes the PageImageableSize property of PrintCapabilities. The properties of this interface map directly to those in the PageImageableSize property of PrintCapabilities. |
| [IPrintSchemaPageMediaSizeOption](nn-printerextension-iprintschemapagemediasizeoption.md) | Exposes a Print Schema PageMediaSize Option element. |
| [IPrintSchemaParameterDefinition](nn-printerextension-iprintschemaparameterdefinition.md) | The IPrintSchemaParameterDefinition interface represents a parameter definition, as defined in the Print Schema Specification. |
| [IPrintSchemaParameterInitializer](nn-printerextension-iprintschemaparameterinitializer.md) | The IPrintSchemaParameterInitializer interface represents a parameter initialization value, as defined in the print schema specification. |
| [IPrintSchemaTicket](nn-printerextension-iprintschematicket.md) | Provides the primary method to access and validate a PrintTicket. |
| [IPrintSchemaTicket2](nn-printerextension-iprintschematicket2.md) | The IPrintSchemaTicket2 interface is an extension to the IPrintSchemaTicket interface, which provides wrapper methods over a print ticket document. |






## Enumerations
| Title | Description |
| ---- |:---- |
| [tagPrintJobStatus](ne-printerextension-tagprintjobstatus.md) | This enumeration is a one-to-one mapping to the spooler flags suppled in the JOB_INFO_X structures. |
| [tagPrintSchemaConstrainedSetting](ne-printerextension-tagprintschemaconstrainedsetting.md) | The PrintSchemaConstrainedSetting enumeration specifies whether the Option is available based on the current device configuration. The constrained attribute appears only in a PrintCapabilities document. |
| [tagPrintSchemaParameterDataType](ne-printerextension-tagprintschemaparameterdatatype.md) | The PrintSchemaParameterDataType enumeration identifies the allowed data types for the Print Schema parameter. |
| [tagPrintSchemaSelectionType](ne-printerextension-tagprintschemaselectiontype.md) | The PrintSchemaSelectionType enumeration identifies how a Feature’s options should be selected. This property appears only in a PrintCapabilities document. |