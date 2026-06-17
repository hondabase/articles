---
summary: 'A detailed technical overview of the Electronic Air Control Valve (EACV), also known as the Idle Air Control Valve (IACV), and its function in regulating Honda engine idle speed.'
tags: [sensors, eacv, iacv, idle, diagnostics]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Electronic Air Control Valve (EACV) Operation

The Electronic Air Control Valve (EACV), commonly referred to as the Idle Air Control Valve (IACV), is a solenoid-operated valve responsible for regulating engine idle speed by controlling the amount of bypass air entering the intake manifold.

## Functionality
The ECU modulates the EACV to maintain a target idle RPM under varying engine loads, such as:
* Cold start warm-up cycles.
* Electrical load activation (headlights, cooling fans).
* Air conditioning compressor engagement.
* Power steering pump load.

> [!NOTE]
> The EACV is pulse-width modulated (PWM) by the ECU. By varying the duty cycle of the signal, the ECU can precisely control the valve's opening position.

## Troubleshooting and Diagnostics
If the engine experiences erratic idle, hunting (surging), or fails to maintain idle speed, the EACV is a primary component for inspection.

### Common Failure Modes
* **Carbon Buildup:** Internal passages become restricted by oil vapor and carbon deposits, preventing the valve from moving freely.
* **Solenoid Failure:** The internal coil may develop an open or short circuit, preventing the ECU from actuating the valve.
* **Vacuum Leaks:** Faulty gaskets or cracked hoses connected to the EACV can introduce unmetered air into the intake.

> [!TIP]
> Before replacing the unit, attempt to clean the internal valve assembly with a high-quality carburetor or throttle body cleaner to remove carbon deposits.

### Testing Procedures
1. **Resistance Test:** Measure the resistance across the two terminals of the EACV solenoid. Refer to the specific service manual for your chassis, as values typically range between 8–15 ohms.
2. **Voltage Test:** With the ignition ON, verify that battery voltage is present at one of the two pins on the harness connector.
3. **Actuation Test:** Use a diagnostic scan tool or a jumper wire to command the valve to open/close while the engine is idling to observe changes in engine RPM.

::: widget error-codes :::