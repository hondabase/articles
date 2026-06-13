---
summary: 'The serial interrupt code in the stock ECU is very simple. A 1 byte hex address is sent to the ECU, and the ECU responds with the contents of RAM memory at that address.'
applies_to:
  obd: [0]
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - diagnostics
---

# OBD0 Stock Datalogging

The serial interrupt code in the stock [ECU](/cars/electronics/ecu) is very simple. A 1 byte hex address is sent to the [ECU](/cars/electronics/ecu), and the [ECU](/cars/electronics/ecu) responds with the contents of [RAM](/cars/electronics/ram) memory at that address. The reason that the stock [ECU](/cars/electronics/ecu) code is not suitable for datalogging under most circumstances is that the serial port is initialized to a very high baud rate. It runs at (CLK / 64 baud), or 12Mhz / 64 (187,500 baud), which is not terribly serial-port friendly. See [Intel8051](/cars/electronics/intel8051) tutorials for information about this. In order to do datalogging currently, Timer2, which is unused elsewhere in the code, is used to initialize the serial port to a speed that is close to 9600 baud, which PC serial ports can communicate at.
