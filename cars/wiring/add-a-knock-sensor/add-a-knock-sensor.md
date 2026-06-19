---
summary: 'Hardware modification guide for adding a knock sensor to a Honda P75/P72 ECU board.'
tags: [ecu, tuning, wiring, knock-sensor, hardware-modification]
applies_to:
  models: [civic, del-sol, integra]
  chassis: [dc2, eg, eg-eh]
complexity: intermediate
---

# Adding a Knock Sensor to a Honda ECU

This guide outlines the hardware modifications required to add a knock sensor circuit to a Honda P75 ECU board, effectively upgrading it to support P72 knock sensor functionality.

---

## Installation Procedure

1.  **Prepare ECU Board:** Acquire a knock sensor board (e.g., from a P72 ECU).
2.  **Connector Strip:** Install the connector strip. If using a JDM P72 board, you may need to move the connector strip from the connector port B to connector port A.
3.  **Resistor Modifications:**
    *   Remove **R12**.
    *   Install **R15** and **R11** (100 Ohm resistors; you can reuse the removed R12 if appropriate).
4.  **Final Installation:** Solder the knock board onto the P75/P72 conversion location (FC1).

---

## Verification and Setup

Once the hardware installation is complete, the ECU board should be functionally equivalent to a P72.

*   **Software Configuration:** You must enable the knock sensor in your ECU management software/ROM configuration.
*   **Verification:** Ensure all connections are secure and verify the knock sensor wiring on the engine harness side is correct.

*Always verify your board layout and component markings before soldering. Knock sensor functionality is critical for engine protection in turbocharged or high-compression applications.*
