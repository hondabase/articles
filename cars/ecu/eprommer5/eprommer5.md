---
summary: 'Technical reference and cross-reference documentation for the EPROMer5 parallel-port EPROM programmer.'
tags: [hardware, eprom, programming, tuning]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# EPROMer5 Parallel-Port EPROM Programmer

The EPROMer5 is a parallel-port based hardware device used for reading and writing EPROM chips for Honda ECU tuning. 

> [!NOTE]
> This article serves as a reference for the EPROMer5 hardware. For comprehensive technical specifications, component configuration, and troubleshooting procedures, refer to the [EPROMer5 Device Programmer Guide](/cars/ecu/epromer5).

## Hardware Overview
The EPROMer5 utilizes a standard parallel port interface to communicate with the host computer. It is designed to support various EPROM chip types commonly used in OBD0, OBD1, and OBD2 ECU modifications.

## Technical Requirements
To ensure successful operation, verify the following:

* **Interface:** Parallel port (LPT) connection.
* **Power:** External power supply requirements as specified in the hardware guide.
* **Software:** Compatible EPROM programming software configured for the EPROMer5 hardware profile.

## Troubleshooting
If the device is not recognized by the host system:

1. **Verify Port Settings:** Ensure the parallel port mode in the BIOS is set to EPP or ECP.
2. **Cable Integrity:** Inspect the parallel cable for continuity and ensure a secure connection at both the programmer and the PC.
3. **Driver Configuration:** Confirm that the necessary drivers are installed and that no resource conflicts exist with other hardware.
