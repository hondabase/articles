---
summary: 'Volumetric Efficiency (VE) is a comparison of the real world volume of air/fuel mixture drawn in and the actual volume of the cylinder if it were completely filled.'
tags: [ecu, reference, tuning, rom, sensors]
applies_to:
  obd: [0, 1, 2]
  brand: Honda
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Volumetric Efficiency'
    url: /pgmfi/wiki/library/volumetric-efficiency
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Volumetric Efficiency

[Volumetric Efficiency](/cars/rom/volumetric-efficiency) (VE) is a comparison of the real world volume of air/fuel mixture drawn in and the actual volume of the cylinder if it were completely filled. "Pumping Efficiency" is another synonym. Typical figures for naturally aspirated engines is roughly 80%. Turbocharged and supercharged motors almost always have a VE greater than 100%. Fuel tables present in Honda [ECU](/cars/ecu/ecu)s are (in a slightly roundaboout way) volumetric efficiency tables. The VE value is stored as the result VE multiplied by the theoretical maximum airflow corrected for the size of the injector to give a desired [Air Fuel Ratio](/cars/fueling/air-fuel-ratio), i.e. **Injector Size x VE x Theoretical Pumping Possibility** (assumed temperature and atmospheric pressure for [Ideal Gas Law](/cars/rom/ideal-gas-law) conditions) This is merely a shortcut to save the [ECU](/cars/ecu/ecu) from having to do all the ideal gas law calculations and then multiply by VE to get airflow, and then multiply again by a factor to account for injector size. [Intake Air Temperature Sensor](/cars/sensors/intake-air-temperature-sensor) correction is then used to adjust the fueling to match the actual intake air temp rather than the one assumed in the creation of the VE table.
