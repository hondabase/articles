---
summary: Historical overview of OBD0 and OBD1 Honda ECU datalogging methods, ports, adapters, and software.
applies_to:
  obd: [0, 1]
complexity: intermediate
tags: [datalogging, serial, diagnostics, ecu]
---

# Honda OBD0 and OBD1 ECU datalogging overview

Datalogging records operating conditions from a running engine. This archived overview describes the two serial-communication methods and the software commonly used by the early Honda ECU tuning community.

## Connection methods

| Method | Archived description |
| --- | --- |
| Stock Data Link Connector (DLC) | Uses the ECU's original diagnostic communication path through the vehicle DLC |
| Internal ECU serial connector | Uses CN2 on OBD1 ECUs or CN3 on OBD0 ECUs with a modified ECU-code serial handler |

Stock OBD0 and OBD1 ECUs included diagnostic communication capability. The source says the stock serial baud rate was not standard for PC serial ports, but explicitly does not remember the exact rate or establish whether a PC could use it directly.

For more detail on the physical interfaces, see [serial communication](/cars/electronics/serial-communication) and the [Data Link Connector reference](/cars/electronics/dlc).

## Historical software

The archived page names these community tools for ROMs using a modified serial handler derived from Doc's original datalogging code:

- **ECUControl:** described as the original PGMFI datalogging software, with historical Windows, Palm OS, and planned Pocket PC support.
- **Cuddle:** historical OBD1 datalogging and RTP-control software.
- **TurboEdit:** historical OBD0 datalogging and offline auto-tuning software.

The page also notes that Doc's original datalogging code contained a bug, without identifying it.

## Electrical interface

If the computer-side hardware does not support the ECU's 5 V TTL communication, the source says a serial adapter is required. Later laptops without serial ports could instead use a USB-to-serial converter.

See the archived [second-generation USB-to-serial converter guide](/cars/electronics/second-gen-usb-to-serial-converter) and [datalogging troubleshooting guide](/cars/electronics/debugging-data-logging) for related hardware notes.

## JDM P30 jumper note

The source records `J12 = J4` on a JDM P30 and says this may apply to other JDM ECUs, but explicitly marks that broader applicability as uncertain.

## Related

- [Serial communication](/cars/electronics/serial-communication)
- [Data Link Connector](/cars/electronics/dlc)
- [TurboEdit](/cars/electronics/turbo-edit)
- [Second-generation USB-to-serial converter](/cars/electronics/second-gen-usb-to-serial-converter)
- [Troubleshooting ECU datalogging](/cars/electronics/debugging-data-logging)
- [Logging an external 0-5 V sensor through P30 D12](/cars/electronics/how-to-log-external-data-such-as-an-egt-sensor)
