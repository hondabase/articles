---
summary: 'A comprehensive overview of the primary and optional sensors utilized by Honda ECUs to manage fuel injection, ignition timing, and engine operation.'
tags: [ecu, sensors, diagnostics, engine-management]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Honda ECU Sensors

Honda engine management systems rely on a specific array of sensors to calculate fuel delivery, ignition timing, and idle control.

## Primary Sensors
These sensors are standard on most Honda engine platforms:

*   **Crankshaft Position Sensor (CKP):** Determines timing for fuel injection and ignition for each cylinder; also detects engine speed.
*   **Top Dead Center Sensor (TDC):** Determines ignition timing during cranking and provides a reference when the crank angle signal is abnormal.
*   **Cylinder Position Sensor (CYP):** Detects the position of the #1 cylinder to facilitate sequential ignition.
*   **Engine Coolant Temperature (ECT):** Thermocouple input used to monitor engine operating temperature for fuel enrichment and cooling fan control.
*   **Intake Air Temperature (IAT):** Thermocouple input used to measure the temperature of incoming air for air density calculations.
*   **Manifold Absolute Pressure (MAP):** Measures intake manifold pressure, allowing the ECU to adjust the air-fuel ratio based on engine load.
*   **Oxygen Sensor (O2):** Measures oxygen content in the exhaust gas to facilitate closed-loop fuel control.
*   **Barometric Pressure Sensor (PA/BARO):** Measures atmospheric pressure to compensate for altitude changes.
*   **Throttle Position Sensor (TPS):** Monitors the angle of the throttle plate to determine driver demand.
*   **Vehicle Speed Sensor (VSS):** Measures the rotational speed of the transmission output shaft or axles.
*   **Idle Air Control Valve (IACV/EACV):** Regulates bypass air to maintain a stable idle speed under varying loads.

## Optional and Auxiliary Sensors
These components are engine-specific or market-dependent:

*   **Electrical Load Detector (ELD):** Found in most North American vehicles to monitor total electrical system load.
*   **Knock Sensor (KS):** A piezoelectric sensor used to detect engine detonation (knock), primarily on DOHC VTEC engines.
*   **VTEC Solenoid:** An electro-hydraulic valve that routes oil pressure to actuate the VTEC mechanism.

> [!NOTE]
> Most Honda ECUs do not utilize a Mass Air Flow (MAF) sensor, relying instead on Speed-Density calculations derived from the MAP, IAT, and TPS sensors.

{{> sensor-troubleshooting-guide }}