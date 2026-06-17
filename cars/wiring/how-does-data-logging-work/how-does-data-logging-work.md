---
summary: 'Technical overview of how PC-based software communicates with Honda ECUs for real-time datalogging.'
tags: [datalogging, tuning, ecu-communication]
applies_to:
  obd: [1]
  models: [civic, integra]
  chassis: [dc2, eg, eg-eh, ek]
complexity: advanced
---

# How ECU Datalogging Works

Data logging enables tuners to record real-time engine operating data directly from the ECU for analysis and performance tuning. 

---

## Communication Basics

For a PC to communicate with an OBD1 Honda ECU, a serial data connection is required.

*   **Signal Translation:** Honda ECUs communicate using **TTL (Transistor-Transistor Logic)** voltage levels, while PC serial ports utilize **RS-232** voltage levels. A signal converter/translator is required to bridge these two standards.
*   **Software Patch:** The factory ECU software does not natively support external serial data logging. Tuners must install a datalogging "patch" (such as those provided in Crome or Hondata suites) into the ECU binary file, which is then burned onto an EPROM chip.
*   **Data Exchange:** Once the patched ECU is running and connected to a PC via serial (or USB-to-serial), the logging software sends periodic requests to the ECU for specific data parameters (e.g., RPM, MAP, O2 sensor voltage). The ECU interprets these commands and returns the requested data to the PC, which logs it into a file for later review.

---

## Tuning Applications

Recorded log files allow tuners to correlate engine performance data with specific engine load and RPM points. This data is critical for refining fuel and ignition maps in ROM editing software, enabling precise tuning adjustments based on real-world operating conditions.
