---
summary: 'Learn how ECU hardware configuration and software programming interact to determine automatic or manual transmission operation in Honda ECUs.'
tags: [ecu, transmission, wiring, diagnostics, tuning]
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
---

# ECU Transmission Configuration: Automatic vs. Manual

The operational mode of a Honda ECU is determined by an interaction between physical hardware configuration and software logic.

## Hardware Configuration
The physical state of the ECU is determined by the presence or absence of shunts at locations **RP17** and **RP18**. These shunts define whether the ECU hardware is configured for automatic or manual transmission control.

> [!IMPORTANT]
> Refer to the [Auto to Manual Conversion](/cars/wiring/auto-to-manual) guide for specific instructions on modifying the PCB shunts to change the hardware state.

## Software Logic
ECU firmware is responsible for polling the hardware shunts to determine if automatic transmission control should be enabled. 

*   **Manual-configured hardware:** If the ECU is physically configured for manual (via shunts), it will operate as a manual ECU regardless of the software.
*   **Automatic-configured hardware:** If the ECU is configured for automatic, the software determines the behavior. It is possible to force an automatic-configured ECU to operate as a manual unit by using a calibration that has the automatic transmission circuit check disabled.
*   **Factory Variations:** Some factory calibrations (such as specific EDM P30 variants) do not perform a check on the automatic transmission shunt configuration. Conversely, most USDM calibrations (e.g., P74, P75, P28, PM6) perform a mandatory check of these shunts.

## Summary of Procedures

*   **Converting Automatic to Manual:** You may modify the hardware shunts according to the [Auto to Manual](/cars/wiring/auto-to-manual) guide, disable the shunt check within the software calibration, or perform both actions.
*   **Maintaining Automatic Control:** To ensure the ECU successfully controls an automatic transmission, you must use a base calibration that includes the necessary code to poll the transmission shunts. The USDM P28 is a standard, reliable choice for automatic applications.