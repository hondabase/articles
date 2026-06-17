---
summary: 'A guide to implementing Full Throttle Shift (FTS) in Honda OBD1 ECUs, allowing for faster gear changes by maintaining boost and RPM during shifts.'
tags: [ecu, tuning, rom, sensors, diagnostics]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: intermediate
---

# Full Throttle Shift Implementation for OBD1 ECUs

Full Throttle Shift (FTS) is an extension of the Launch Control concept, allowing for a secondary rev limit while the vehicle is in motion. This feature enables faster gear changes by maintaining boost pressure and engine RPM during the shift sequence.

## Implementation Overview

FTS functions by modifying the existing rev limiter logic to utilize a secondary limit threshold triggered by a digital input. This input is typically tied to a clutch-mounted switch.

### Hardware Requirements

To implement FTS, you must install a switch that detects clutch pedal engagement.

*   **Switch Selection:** For vehicles not equipped with cruise control, the factory cruise control clutch switch is the most straightforward mounting solution.
*   **Wiring:**
    *   Connect one side of the switch to a chassis ground.
    *   Connect the opposing side of the switch to the designated digital input pin on the ECU.

> [!TIP]
> Pin B7 (off 00211h.5) is a common and recommended digital input for FTS implementation on OBD1 ECUs.

## ECU Configuration

The implementation requires modification of the ECU firmware to recognize the clutch switch input and apply the secondary rev limit.

1.  **Firmware Modification:** Update the ECU assembly code to include the FTS routine. This routine must monitor the state of the chosen digital input pin.
2.  **Logic Integration:** Hook the existing rev limiter code to reference the secondary limit when the clutch switch signal is active (grounded).
3.  **Calibration:** Define the secondary RPM threshold within the ROM to suit the specific engine and turbocharger setup.

> [!WARNING]
> Improper calibration of the FTS rev limit can lead to engine damage. Ensure the secondary limit is set to an appropriate RPM range that prevents engine over-revving while maintaining sufficient turbocharger spool.