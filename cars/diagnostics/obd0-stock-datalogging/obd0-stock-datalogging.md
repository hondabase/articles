---
summary: 'An overview of the OBD0 ECU serial communication protocol, including baud rate limitations and the implementation of Timer2 for standard datalogging.'
tags: [ecu, datalogging, obd0, serial, tuning, intel8051]
applies_to:
  obd: [0]
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: intermediate
---

# OBD0 Stock ECU Serial Datalogging

The serial interrupt code in the stock ECU utilizes a straightforward request-response protocol. A 1-byte hexadecimal address is transmitted to the ECU, which responds by returning the contents of the RAM memory at that specific address.

## Communication Limitations
The stock ECU serial port is initialized to a high baud rate, calculated as (CLK / 64). At a clock speed of 12MHz, this results in a baud rate of 187,500. This rate is non-standard and incompatible with most PC serial port hardware.

> [!NOTE]
> Refer to [Intel 8051](/cars/rom/intel8051) technical documentation for further details regarding serial port configuration and clock cycles.

## Datalogging Implementation
To enable functional datalogging with standard PC hardware, the serial port must be reconfigured to a compatible speed, typically 9600 baud. 

> [!IMPORTANT]
> Because the stock serial initialization is unsuitable for standard communication, the implementation requires the use of Timer2. As Timer2 is otherwise unused in the stock ECU code, it is repurposed to initialize the serial port to a standard 9600 baud rate.