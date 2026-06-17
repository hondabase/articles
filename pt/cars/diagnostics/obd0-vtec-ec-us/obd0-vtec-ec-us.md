---
summary: "Technical overview of OBD0 VTEC ECUs (PR3 and PW0) used in 1989-1991 B16A1 applications, including hardware specifications and compatibility notes."
tags: [ecu, obd0, vtec, b16a1, tuning]
applies_to:
  obd: [0]
  models: [crx, civic, integra]
complexity: beginner
---

# OBD0 VTEC ECU Reference: PR3 and PW0

The PR3 and PW0 are the primary OBD0 ECUs designed for VTEC-equipped B16A1 engines found in 1989–1991 vehicles. 

## Hardware Specifications
These units utilize a 7.900 MHz crystal oscillator. 

> [!IMPORTANT]
> There is no code interchangeability between the PR3 and PW0 units. Despite their similar application, the internal firmware and hardware mapping are distinct.

## ECU Compatibility
The following table outlines the primary application for these units:

| ECU Model | Engine | Chassis | Region |
| :--- | :--- | :--- | :--- |
| **PR3** | B16A1 | EF8 / EF9 | JDM |
| **PW0** | B16A1 | EF8 / EF9 | JDM |

## Tuning and Diagnostics
Current development support for these specific OBD0 VTEC units is limited. Users looking to perform advanced tuning or diagnostics on these platforms should note the following:

* **Hardware Limitations:** Due to the age of the hardware and the lack of modern emulation support, these units are generally considered legacy platforms.
* **Diagnostics:** Standard OBD0 diagnostic procedures apply. 

::: widget error-codes :::

> [!TIP]
> For users requiring VTEC functionality in an OBD0 environment, ensure the ECU is correctly pinned for the VTEC solenoid and pressure switch inputs, as these are not present on non-VTEC OBD0 harnesses.