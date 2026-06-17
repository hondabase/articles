---
summary: "Honda ECUs utilize 5V TTL signaling for serial communication. This guide outlines the necessary serial adapters required to interface with ECU hardware for data logging."
tags: [ecu, tuning, serial, ttl, diagnostics]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
---

# Honda ECU Serial Communication Adapters

Honda ECUs utilize 5V TTL signaling for serial communication. If your data logging hardware does not natively support 5V TTL levels, you must use a serial adapter to bridge the connection between the ECU and your interface device.

> [!IMPORTANT]
> Ensure the adapter provides 5V logic levels. Using standard RS232 voltage levels (which can reach ±12V) without proper conversion will cause permanent damage to the ECU communication circuitry.

## Common Serial Adapters

The following table lists common adapters used to convert various interfaces to the required 5V TTL signal format.

| Unit | From Interface | To Interface |
| :--- | :--- | :--- |
| Super Droid Robots | RS232 | 5V TTL |
| CompSys MAX233 | RS232 | 5V TTL |
| Lucas Schaar | RS232 | 5V TTL |
| Gigatechnology | USB 1.1 | 5V TTL |

## Implementation Notes

*   **Signal Integrity:** Keep cable lengths between the adapter and the ECU as short as possible to minimize signal noise and data corruption during high-speed logging.
*   **Grounding:** Ensure a common ground is established between the ECU chassis ground and the adapter ground to prevent ground loops.
*   **Baud Rate:** Verify that your software settings match the specific baud rate requirements of the ECU protocol (typically 9600 or 38400 baud depending on the generation).