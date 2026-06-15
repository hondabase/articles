---
summary: 'Modeling the Map Sensor voltage output into a usable number. (From the Helm Manual:) !hondastockmapvolt.'
tags: [tuning, rom, sensors, reference]
applies_to:
  obd: [0, 1, 2]
  brand: Honda
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Map Sensor Equation'
    url: /pgmfi/wiki/library/map-sensor-equation
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Map Sensor Equation

Modeling the [Map Sensor](/cars/fueling/map-sensor) voltage output into a usable number. (From the Helm Manual:) ![honda_stock_map_volt.jpg](/pgmfi/wiki/media/library/MapSensor/honda_stock_map_volt.jpg) y = mx + b y = mx + 2.85v y = (-.1)x + 2.85v (-.1)x = y - 2.85 ***x = (y - 2.85v) / (-.1)***Alldata publishes a MAP sensor spec, and I took data from my MAP sensor to compare, and added the data per the Helm-based formula:

```

05 in Hg| Alldata: 2.5 | 2.35 Helm-based formula | my actual: 2.460 
10 in Hg| Alldata: 2.0 | 1.85 Helm-based formula | my actual: 1.938 
15 in Hg| Alldata: 1.5 | 1.35 Helm-based formula | my actual: 1.509 
20 in Hg| Alldata: 1.0 | 0.85 Helm-based formula | my actual: 1.012 
25 in Hg| Alldata: 0.5 | 0.35 Helm-based formula | my actual: 0.558 
```

Based on the Alldata spec, the formula is: ***x = (y - 3.0v)/(-.1)***It looks like these two formulas can give you a reasonable range for calibration. -- markolson - 04 Mar 2005
