---
summary: 'The VTEC crossover point is the specific engine RPM at which the ECU activates the VTEC solenoid to transition from low-profile to high-profile camshaft lobes.'
tags: [tuning, rom, sensors, vtec]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# VTEC Crossover Point Calibration

The VTEC crossover point is the engine speed (RPM) at which the ECU energizes the VTEC solenoid. This action engages the hydraulic pin mechanism, transitioning the valvetrain from the low-lift/short-duration cam lobes to the high-lift/long-duration cam lobes.

## Operational Requirements
For the ECU to trigger the VTEC crossover, several environmental and mechanical conditions must be met simultaneously:

*   **Engine RPM:** Must be above the programmed crossover threshold.
*   **Engine Coolant Temperature (ECT):** Must be within the operating range (typically >150°F / 65°C).
*   **Vehicle Speed:** The vehicle must be in motion (VSS signal present).
*   **Oil Pressure:** Sufficient oil pressure must be detected by the VTEC pressure switch.
*   **Throttle Position:** The engine must be under sufficient load (TPS threshold).

> [!IMPORTANT]
> If any of the above conditions are not met, the ECU will inhibit VTEC engagement regardless of the RPM crossover setting in the ROM.

## Tuning Considerations
Adjusting the crossover point is a critical step in engine calibration to ensure a smooth transition in the torque curve.

*   **Lowering the Crossover:** Can improve mid-range torque if the engine's volumetric efficiency supports the high-cam profile at lower RPMs.
*   **Raising the Crossover:** Often necessary when using aftermarket camshafts with aggressive profiles that require higher RPMs to stabilize combustion.

> [!TIP]
> Use a chassis dynamometer to identify the "crossover dip." The ideal crossover point is the RPM where the torque curve of the high-cam profile intersects the torque curve of the low-cam profile.

## Diagnostic Troubleshooting
If the engine fails to transition to the high-cam profile, verify the following:

1.  **VTEC Solenoid:** Check for 12V at the solenoid connector when the crossover RPM is reached.
2.  **Oil Level:** Low engine oil levels can prevent the hydraulic pressure required to actuate the VTEC pins.
3.  **Pressure Switch:** Ensure the VTEC pressure switch is functioning and not reporting an open circuit to the ECU.

::: widget error-codes :::
