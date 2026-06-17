---
summary: 'Technical overview of the 1-wire VTEC ROM codebase, which utilizes the automatic transmission lockup solenoid to control VTEC engagement on OBD0 ECUs.'
tags: [ecu, rom, tuning, vtec, obd0]
applies_to:
  obd: [0]
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: intermediate
---

# 1-Wire VTEC Conversion

The **1-wire VTEC** codebase is a specialized ROM modification for OBD0 MPFI ECUs. It repurposes the [Automatic Transmission Lockup Solenoid](/cars/sensors/automatic-transmission-lockup-solenoid) output to control VTEC engagement, enabling VTEC functionality on early OBD0 engine control systems.

---

## Overview

This modification is designed for users operating OBD0 MPFI ECUs who wish to run VTEC-equipped engines. By utilizing the existing wiring and output intended for the automatic transmission lockup solenoid, it simplifies the wiring requirements for VTEC activation.

### Development and Implementation
*   **Hardware:** The necessary hardware changes for this modification are detailed in the [Hardware For One Wire VTEC](/cars/rom/hardware-for-one-wire-vtec) guide.
*   **Source Code:** The project is open-source. Codebase contributions and development can be found via the [Source Forge](/cars/wiring/source-forge) project repository.

---

## Important Considerations

*   **Testing:** This conversion is functional, but thorough testing is required when implementing custom code modules.
*   **Wiring:** This modification requires specific ECU hardware changes and engine harness modifications to repurpose the lockup solenoid output. Ensure all connections are secure and verified against your specific ECU board layout.
