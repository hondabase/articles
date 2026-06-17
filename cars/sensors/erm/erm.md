---
summary: 'Technical overview of the UberData Engine Management (ERM) system, a legacy tuning solution for Honda OBD1 ECUs.'
tags: [ecu, tuning, obd1, legacy]
applies_to:
  obd: [1]
  models: [civic, integra, prelude]
  chassis: [ef, eg, eg-eh, ek, da, dc2]
complexity: intermediate
---

# UberData Engine Management (ERM) System

The UberData Engine Management (ERM) system is a legacy hardware and software solution designed for tuning Honda OBD1 ECUs. It provides a platform for modifying fuel and ignition maps, as well as adjusting various engine parameters for performance applications.

## System Overview

The ERM system utilizes a daughterboard installed within the factory OBD1 ECU to allow for real-time data logging and map switching. It is primarily used in conjunction with specific tuning software to interface with the ECU's processor.

> [!IMPORTANT]
> The ERM system is considered legacy hardware. Ensure your ECU is properly socketed and the daughterboard is securely seated before attempting to upload or modify calibration files.

## Hardware Requirements

To utilize the ERM system, the following hardware modifications are required:

*   **Socketed ECU:** The ECU must be equipped with a 28-pin DIP socket to accept the ERM daughterboard or the programmed EEPROM.
*   **Daughterboard:** The ERM-specific daughterboard must be soldered to the J1 header location on the ECU motherboard.
*   **EEPROM:** A compatible chip (e.g., 27SF512) is required to store the modified calibration data.

## Installation Procedure

1.  **Prepare the ECU:** Open the ECU casing and locate the J1 header position.
2.  **Socketing:** If not already socketed, desolder the factory ROM and install a 28-pin machine-pin socket.
3.  **Daughterboard Integration:** Align the ERM daughterboard with the J1 header pins. Ensure all pins are properly seated and soldered to maintain electrical continuity.
4.  **Verification:** Before powering the ECU, verify that there are no solder bridges between the pins of the J1 header or the main processor.

> [!CAUTION]
> Improper soldering or shorting pins on the J1 header can cause permanent damage to the ECU processor. Always use a multimeter to check for continuity and shorts before applying power.

## Tuning and Diagnostics

The ERM system allows for the adjustment of the following parameters:

*   **Fuel Maps:** High and low cam fuel tables.
*   **Ignition Maps:** High and low cam ignition advance tables.
*   **Rev Limiters:** Adjustable fuel and ignition cut points.
*   **VTEC Engagement:** RPM and load-based VTEC activation thresholds.

For further information on specific tuning procedures and software compatibility, refer to the documentation provided with your specific ERM software suite.