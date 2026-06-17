---
summary: 'Step-by-step hardware guide for adding a knock sensor circuit to non-equipped Honda OBD1 ECUs using specific component modifications.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
applies_to:
  obd: [1]
  models: [civic, del-sol, integra]
  chassis: [dc2, eg, eh]
complexity: intermediate
---

# Adding Knock Sensor Circuitry to OBD1 ECUs

This guide outlines the hardware modifications required to add knock sensor (KS) functionality to OBD1 Honda ECUs (such as the P75 or P29) that lack the factory circuit.

> [!WARNING]
> Modifying ECU hardware requires precision soldering skills. Incorrect installation can result in permanent damage to the ECU or engine failure due to improper knock detection.

## Component Modifications by Board Revision

The required components vary based on the specific PCB revision of your ECU. Identify your board revision (e.g., 1720, 11F0, or 1550) before proceeding.

### 1720 and 11F0 Boards
To enable the knock sensor circuit on these revisions, perform the following modifications:

*   **Remove:** `R140`, `R141` (10k resistors).
*   **Add:** `R107`, `R115`, `R116` (220R resistors).
*   **Optional Components:**
    *   `C94`: 4.7µF 16V Tantalum capacitor.
    *   `Q20`: A143 transistor.

### 1550 and 1550x Boards
For 1550-series boards, use the following configuration:

*   **Remove:** `R78`, `R77` (located on the reverse side).
*   **Add:**
    *   `R37` (Reverse Side).
    *   `R50` (Reverse Side).
    *   `R38` (221 resistor).
    *   `C82`: 4.7µF 16V Tantalum capacitor.

## Technical Considerations

### Knock Board Calibration
The knock sensor board is tuned to specific engine characteristics to filter mechanical noise from actual detonation. 

*   **Frequency Tuning:** The knock sensor frequency is determined by the values of `R12` and `R15` on the knock board.
*   **Engine Compatibility:** Because the knock board is calibrated to the bore size and harmonic profile of the engine it was designed for, using a knock board from a different engine family may result in ineffective knock detection or false positives.

### ECU Conversion
It is possible to convert a non-VTEC ECU (such as a P75) to P30 or P72 specifications. When performing these conversions, ensure that all necessary peripheral circuits—such as heated O2 sensor control and VTEC solenoid drivers—are populated if the target calibration requires them.

> [!NOTE]
> Always verify the ECU board revision before sourcing components, as internal layouts may differ between regional variants (e.g., US vs. JDM).