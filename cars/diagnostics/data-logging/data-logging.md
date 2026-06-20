---
summary: 'Overview of OBD0 and OBD1 Honda ECU datalogging methods, including serial communication interfaces, historical software, and hardware requirements.'
tags: [datalogging, serial, diagnostics, ecu]
applies_to:
  models: [civic, del-sol]
  chassis: [eg, eh]
complexity: intermediate
---

# Honda OBD0 and OBD1 ECU Datalogging Overview

Datalogging records real-time operating conditions from a running engine. This article outlines the serial communication methods and historical software used for OBD0 and OBD1 Honda ECU diagnostics.

## Connection Methods

| Method | Description |
| :--- | :--- |
| **Stock Data Link Connector (DLC)** | Utilizes the ECU's original diagnostic communication path through the vehicle's DLC. |
| **Internal ECU Serial Connector** | Utilizes `CN2` (OBD1) or `CN3` (OBD0) headers with a modified ECU-code serial handler. |

> [!NOTE]
> Stock OBD0 and OBD1 ECUs utilize a non-standard serial baud rate. Direct connection to a standard PC serial port may require specific hardware adaptation.

For detailed physical interface specifications, refer to [Serial Communication](/cars/tuning/serial-communication) and the [Data Link Connector Reference](/cars/wiring/dlc).

## Historical Software

The following legacy tools were developed for ROMs utilizing modified serial handlers:

*   **ECUControl:** The original datalogging software with support for Windows, Palm OS, and Pocket PC.
*   **Cuddle:** OBD1 datalogging and Real-Time Programming (RTP) control software.
*   **TurboEdit:** OBD0 datalogging and offline auto-tuning software.

## Electrical Interface

If the host computer hardware does not support 5 V TTL communication, a serial adapter is required. Modern systems without native serial ports require a USB-to-serial converter.

> [!TIP]
> Refer to the [USB-to-Serial Converter Guide](/cars/tuning/second-gen-usb-to-serial-converter) and [Datalogging Troubleshooting](/cars/diagnostics/debugging-data-logging) for hardware compatibility and signal debugging.

## JDM P30 Jumper Configuration

On JDM P30 ECUs, the jumper configuration `J12 = J4` is used to facilitate communication. 

> [!IMPORTANT]
> While this configuration is confirmed for the JDM P30, its applicability to other JDM ECU variants remains unverified.

## Related Resources

*   [Serial Communication](/cars/tuning/serial-communication)
*   [Data Link Connector](/cars/wiring/dlc)
*   [TurboEdit](/cars/tuning/turbo-edit)
*   [Second-generation USB-to-serial converter](/cars/tuning/second-gen-usb-to-serial-converter)
*   [Troubleshooting ECU datalogging](/cars/diagnostics/debugging-data-logging)
*   [Logging an external 0-5 V sensor through P30 D12](/cars/tuning/how-to-log-external-data-such-as-an-egt-sensor)
