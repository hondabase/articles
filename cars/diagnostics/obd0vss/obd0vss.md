---
summary: 'Author: George Date: 120302 22:36 Vehicle Speed Sensor (VSS), stored in RAM location 06Ch does appear to be linear (to my surprise!), but can only read up to ~157kph.'
tags: [ecu, reference, sensors, diagnostics]
applies_to:
  obd: [0]
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: OBD0VSS
    url: /pgmfi/wiki/library/obd0vss
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD0VSS

Author: George Date: 12-03-02 22:36 [Vehicle Speed Sensor](/cars/wiring/vehicle-speed-sensor) ([VSS](/cars/sensors/vss)), stored in [RAM](/cars/reference/ram) location `06Ch` does appear to be linear (to my surprise!), but can only read up to ~157kph. Using Excel the formula is approximately: Speed (kph) = 0.6229x - 2.1385
