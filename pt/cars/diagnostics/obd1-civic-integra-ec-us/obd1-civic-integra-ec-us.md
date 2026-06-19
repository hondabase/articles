---
summary: 'Technical overview of OBD1 Honda ECU compatibility, hardware architecture, and requirements for external ROM modification.'
tags: [ecu, tuning, rom, obd1, diagnostics]
applies_to:
  models: [Civic, Integra]
complexity: advanced
---

# OBD1 Civic and Integra ECU Architecture

Most OBD1 ECUs used in 1992–1995 Honda Civic and Acura Integra models share electrical compatibility. This generation of ECU utilizes the 66207 MCU. While most units are factory-equipped with internal ROM, the PCB design includes provisions for external ROM implementation.

> [!NOTE]
> This information applies primarily to USDM ECUs. JDM units typically feature external ROMs from the factory. EDM P28/P30 ECUs follow the same modification procedures as USDM variants.

## Hardware Modification for External ROM
To enable external ROM support, the following components must be populated on the PCB:

*   **74HC373:** Octal transparent latch.
*   **J1 Jumper:** Enables the external ROM circuit.
*   **ROM Socket:** Required for chip installation.
*   **Passive Components:** One resistor and two capacitors (refer to specific board schematics for values).

## ECU Components and Interfaces

### I/O Control
The **82C55** chip serves as the primary I/O controller, managing the majority of the ECU's output signals.

### Data Logging
The **J12** jumper controls the ECU's serial interface. This jumper must be configured correctly to enable data logging functionality.

## Compatibility and Resources
ECU hardware modifications allow for cross-compatibility between different ECU models within the OBD1 family. For detailed information on matching specific engine management code to ECU hardware, refer to the following resources:

*   [OBD1 Code Compatibility](/cars/wiring/obd1-code-compatibility)
*   [ECU Hardware Mods](/cars/rom/ecu-hardware-mods)

::: widget error-codes :::
