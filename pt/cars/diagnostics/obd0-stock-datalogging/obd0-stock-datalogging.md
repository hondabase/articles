---
summary: 'Technical overview of OBD0 stock ECU serial datalogging, including baud rate limitations and the implementation of Timer2 for PC communication.'
tags: [ecu, datalogging, obd0, serial, tuning]
complexity: intermediate
---

# OBD0 Stock ECU Datalogging

The serial interrupt code in the factory ECU utilizes a simple request-response protocol. A 1-byte hexadecimal address is sent to the ECU, which responds with the contents of the RAM at that specific memory address.

## Serial Communication Limitations

The factory ECU serial port is initialized at a high baud rate, calculated as (CLK / 64). At a clock speed of 12MHz, this results in a baud rate of 187,500. This frequency is incompatible with standard PC serial ports.

> [!IMPORTANT]
> Refer to the [Intel 8051](/cars/ecu/intel8051) documentation for detailed specifications regarding the serial port hardware and clock configuration.

## Implementing Datalogging

To enable functional datalogging with standard PC hardware, the **Timer2** peripheral—which remains unused in the factory firmware—is repurposed. By configuring Timer2, the serial port can be initialized to a standard 9600 baud rate, allowing for reliable communication between the ECU and a PC.

### Technical Requirements
* **Protocol:** 1-byte hex address request.
* **Standard Baud Rate:** 9600 bps.
* **Hardware Resource:** Timer2 (repurposed for baud rate generation).

{{> serial-communication-notes }}
