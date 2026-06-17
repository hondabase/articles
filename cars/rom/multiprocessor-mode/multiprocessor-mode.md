---
summary: 'An overview of 8051-based multiprocessor communication protocols, detailing the use of 9-bit serial modes for selective master-slave data transmission.'
tags: [tuning, rom, sensors, reference, serial-communication]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
---

# Multiprocessor Communication Protocols

In applications where multiple controllers perform tasks jointly, the master controller must communicate selectively with individual slave units. This is achieved by identifying the target slave with an address byte before transmitting a data block.

## 9-Bit Serial Mode
The 8051 serial port provides a 9-bit mode to facilitate multiprocessor communication. The 9th bit allows the controller to distinguish between address bytes and data bytes.

In this mode, a total of 11 bits are transmitted or received:
* **Start bit:** 0
* **Data bits:** 8 (LSB first)
* **9th bit:** Programmable
* **Stop bit:** 1

### Bit Identification
The 9th bit acts as a flag for the receiving controller:
* **Address Byte:** 9th bit set to 1.
* **Data Byte:** 9th bit set to 0.

> [!NOTE]
> A typical data stream follows the sequence: `[ADDRESS BYTE] [DATA BYTE] [DATA BYTE] ...`

## Slave Configuration and Interrupts
Initially, the slave is configured to receive only address bytes. Once the slave identifies its specific address, it reconfigures itself to receive subsequent data bytes.

### Hardware-Based Recognition
On standard 8051 serial ports, an address byte interrupts all slaves to perform an address comparison. However, on the 83C51FA, **Automatic Address Recognition** allows the addressed slave to be the only unit interrupted. In this configuration, the address comparison occurs in hardware rather than software, allowing the master to communicate with specific slaves without requiring all units to process the transmission.

![Multiprocessor communication timing diagram](mpcomm.jpg)
*Serial data stream timing for 9-bit multiprocessor communication*