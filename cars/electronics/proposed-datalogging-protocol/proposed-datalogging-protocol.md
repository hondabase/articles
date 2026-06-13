---
summary: 'Technical specification of the proposed high-speed, stream-based custom datalogging and Real-Time Programming (RTP) protocol for Honda ECUs.'
applies_to:
  obd: [1]
complexity: advanced
tags:
  - datalogging
  - serial
  - protocol
---

# Proposed Datalogging & RTP Protocol

This document defines the specification for a custom, stream-based serial communication protocol designed to replace the legacy polled serial interrupt handlers in Honda OBD0 and OBD1 ECUs. 

The protocol aims to provide a cross-platform, high-efficiency connection that supports both high-speed datalogging and Real-Time Programming (RTP) emulation.

## Core Design Principles

1. **Continuous Streaming (Non-Polling)**: Instead of the PC constantly requesting (polling) data, the ECU continuously streams standard datalogging packets at high speed. This minimizes serial latency and CPU overhead on the ECU.
2. **On-Demand Polling**: While primary sensor telemetry streams continuously, the PC can inject short command packets to query arbitrary memory locations or ROM registers.
3. **Memory Space Querying**: Supports reading any location within the 16-bit address space (RAM and ROM).
4. **Data Validation**: Employs checksum verification and complement verification (`CPL`) on write operations to ensure communication integrity before writing to emulation memory (RTP).
5. **Bulk Writing**: Supports a locked-interrupt bulk write mode for rapid ROM re-flashes.

---

## Technical Workflow for Real-Time Programming (RTP)

To ensure that random serial glitches do not write corrupt values to running engine tables, a two-step validation write sequence is used:

1. **Data Transfer**: The PC sends the payload (1 or 2 bytes) to the ECU using a `Byte Write` (`0x10`) or `Word Write` (`0x11`) packet.
2. **ECU Buffering**: The ECU stores the data in a temporary memory buffer ("byte storage" or "word storage") and echoes a `Destination Request` packet (`0xA0` / `0xA1`) containing the received data back to the PC.
3. **Verification**: The PC receives the destination request and verifies the echoed data matches what was sent.
4. **Execution**: 
   * If correct, the PC sends a `Destination` packet (`0x20` / `0x21` / `0x22` / `0x23`) specifying the final target memory address.
   * Upon receiving the destination packet, the ECU moves the buffered data to the final target address in RAM/ROM space.
   * If the verification fails, the PC discards the buffer and restarts from Step 1.

---

## PC-to-ECU Command Packets

Packets sent from the PC to the ECU consist of 5 bytes. A checksum byte is calculated as the 8-bit sum of the address or data bytes.

| Command Name | Byte 1 (ID) | Byte 2 | Byte 3 | Byte 4 | Byte 5 | Function & Reply Behavior |
| :--- | :---: | :---: | :---: | :---: | :---: | :--- |
| **Byte RAM Read** | `0x02` | `Addr (Hi)` | `Addr (Lo)` | `CS` | `0x02` | Reads a byte from RAM. Replies with `0x82` packet. |
| **Word RAM Read** | `0x03` | `Addr (Hi)` | `Addr (Lo)` | `CS` | `0x03` | Reads a word from RAM. Replies with `0x83` packet. |
| **Byte ROM Read** | `0x04` | `Addr (Hi)` | `Addr (Lo)` | `CS` | `0x04` | Reads a byte from ROM. Replies with `0x84` packet. |
| **Word ROM Read** | `0x05` | `Addr (Hi)` | `Addr (Lo)` | `CS` | `0x05` | Reads a word from ROM. Replies with `0x85` packet. |
| **Byte Write** | `0x10` | `Data` | `CPL Data` | `CS` | `0x10` | Sends a RAM byte to temporary storage. Replies with `0xA0`. |
| **Word Write** | `0x11` | `Data 1` | `Data 2` | `CS` | `0x11` | Sends a RAM word to temporary storage. Replies with `0xA1`. |
| **8-bit RAM Dest** | `0x20` | `Addr` | `Addr` | `CS` | `0x20` | Writes buffered byte to an 8-bit RAM address. |
| **16-bit RAM Dest** | `0x21` | `Addr (Hi)` | `Addr (Lo)` | `CS` | `0x21` | Writes buffered byte to a 16-bit RAM address. |
| **16-bit ROM Dest** | `0x22` | `Addr (Hi)` | `Addr (Lo)` | `CS` | `0x22` | Writes buffered byte to a 16-bit ROM address (RTP). |
| **16-bit ROM Word Dest** | `0x23` | `Addr (Hi)` | `Addr (Lo)` | `CS` | `0x23` | Writes buffered word to a 16-bit ROM address (RTP). |
| **Bulk Write Address** | `0x80` | `Addr (Hi)` | `Addr (Lo)` | `0x00` | `0x80` | Sets data pointer and locks ECU in serial interrupt. |
| **Bulk Write Start** | `0x81` | `Length` | `Data...` | - | - | Writes `Length` bytes to ROM starting at data pointer. |

*Note: `CS` is the 8-bit checksum byte, and `CPL` is the bitwise complement (~).*

---

## ECU-to-PC Reply Packets

ECU reply packets are 5 bytes long, with the first byte acting as the packet type identifier.

| Packet Type | Byte 1 (ID) | Byte 2 | Byte 3 | Byte 4 | Byte 5 | Description / Payload |
| :--- | :---: | :---: | :---: | :---: | :---: | :--- |
| **Continuous Telemetry** | `0x01`–`0x7F` | `Data 1` | `Data 2` | `Data 3` | `CS` | Real-time streaming sensor values. |
| **Bulk Write Addr Reply** | `0x80` | `Addr (Hi)` | `Addr (Lo)` | `0x00` | `0x00` | Confirms the target bulk write address. |
| **Bulk Write Verification** | `0x81` | `CS` | `0x00` | `0x00` | `0x00` | Confirms the integrity of the bulk-written block. |
| **Read RAM Byte Reply** | `0x82` | `Data` | `CPL Data` | `Data` | `CS` | Returns the requested 8-bit RAM value. |
| **Read RAM Word Reply** | `0x83` | `Data 1` | `Data 2` | `CS (D1)` | `CS (D2)` | Returns the requested 16-bit RAM value. |
| **Read ROM Byte Reply** | `0x84` | `Data` | `CPL Data` | `Data` | `CS` | Returns the requested 8-bit ROM value. |
| **Read ROM Word Reply** | `0x85` | `Data 1` | `Data 2` | `CS (D1)` | `CS (D2)` | Returns the requested 16-bit ROM value. |
| **Byte Dest Request** | `0xA0` | `Data` | `CPL Data` | `CS` | `Data` | Confirms byte is held in buffer, awaiting destination. |
| **Word Dest Request** | `0xA1` | `Data 1` | `Data 2` | `CS (D1)` | `CS (D2)` | Confirms word is held in buffer, awaiting destination. |
| **Negative Ack (NAK)** | `0xFF` | `0x00` | `0xFF` | `0x00` | `0xFF` | Sent if an invalid or corrupt packet is received. |
