---
summary: 'The input sensors a Honda ECU reads to run fuel and ignition.'
tags: [ecu, sensors]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Ecu Sensors'
    url: /pgmfi/wiki/library/ecu-sensors
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# ECU Sensors

Sensors present on almost all honda motors:

- [Crankshaft Position Sensor](/cars/ignition/crankshaft-position-sensor) - Determines timing for fuel injection and ignition of `each` cylinder and also detects engine speed.
- Top Dead Center Sensor - Determines ignition timing at start-up (cranking) and when crank angle is abnormal.
- [Cylinder Position Sensor](/cars/sensors/cylinder-position-sensor) - Detects position of #1 cylinder for sequential spark ignition to `each` cylinder.
- Engine Coolant Temperature - or ''ECT'' thermocouple input for engine coolant temperature
- [Intake Air Temperature Sensor](/cars/sensors/intake-air-temperature-sensor) - or ''IAT'' thermocouple input for intake air temperature
- Map Sensor - Manifold Absolute Pressure Sensor, allows [ECU](/cars/ecu/ecu) to adjust Air Fuel Ratio based on density of intake air
- Oxygen Sensor - Measures oxygen content of exhaust gas
- Pressure Atmosphere - or ''PA'' or ''Barometric Pressure Sensor'' measures atmospheric pressure.
- TPS Sensor - Throttle Position Sensor
- Vehicle Speed Sensor - or ''VSS'' measures how fast ***axles*** are turning
- Idle Air Control Valve / Electronic Air Control Vale - Or ''IAC/EACV'' Helps control idle

Optional sensors: - Electrical Load Detector - or ''ELD'' present in most US cars to measure how much electrical load there is
- [Knock Sensor](/cars/ignition/knock-sensor) - A microphone-like device to listen for Pre Ignition, or knocking in DOHC VTEC motors.
- Pa Sensor - Atmospheric Pressure sensor
- VTEC Solenoid = solenoid to route oil flow to activate VTEC (on VTEC motors only :) )

---

Other [ECU](/cars/ecu/ecu) Sensors not usually present on honda motors: - Maf Sensor
