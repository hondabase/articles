---
summary: 'An overview of dual-map ROM configurations for Honda ECUs, enabling switchable engine tuning profiles for different fuel or boost requirements.'
tags: [tuning, rom, ecu, maps]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Dual-Map ROM Tuning for Honda ECUs

Dual-map setups allow a single Honda ECU to store and toggle between two distinct tuning profiles. This is commonly utilized for switching between different fuel types (e.g., pump gas vs. E85) or varying boost levels without requiring a laptop connection.

## Overview
A dual-map configuration typically involves modifying the ECU hardware to support a larger memory chip (EEPROM) and adding a physical switch to toggle the high-order address line of the chip. By grounding or pulling this address line high, the ECU is forced to read from a different memory bank, effectively switching the entire calibration.

## Implementation Requirements
To implement a dual-map system, the following components and modifications are required:

*   **Memory Chip:** Upgrade to a 29C256 or similar 32KB EEPROM capable of holding two 16KB maps.
*   **Address Line Switching:** A physical toggle switch wired to the appropriate address pin on the ROM chip.
*   **Calibration:** Two separate binary files must be combined into a single file, ensuring the memory addresses are correctly aligned for the switch to toggle between them.

> [!IMPORTANT]
> Ensure that both maps are tuned specifically for the hardware configuration of the vehicle. Switching maps while the engine is under load can result in catastrophic engine failure if the secondary map is not properly calibrated.

## Wiring Considerations
When installing the toggle switch, use a high-quality, weather-resistant switch mounted in a location accessible to the driver. 

*   **Pin Selection:** The switch must toggle the A14 address line (Pin 1 on a 28-pin 27C256/29C256 chip).
*   **Grounding:** Use a clean chassis ground for the switch to prevent electrical noise from causing intermittent map switching.

> [!TIP]
> Use a shielded wire for the switch connection to minimize electromagnetic interference (EMI) from the ignition system, which can cause the ECU to reset or switch maps unexpectedly.

## Related Configurations
For more information on hardware requirements and memory addressing, refer to the following resources:

*   [Dual ROMs](/cars/tuning/dual-roms)
*   {{> ecu-chip-installation-guide }}
