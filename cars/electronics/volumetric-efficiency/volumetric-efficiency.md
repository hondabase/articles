---
summary: 'Volumetric Efficiency (VE) is a comparison of the real world volume of air/fuel mixture drawn in and the actual volume of the cylinder if it were completely filled.'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
---

# Volumetric Efficiency

[Volumetric Efficiency](/cars/electronics/volumetric-efficiency) (VE) is a comparison of the real world volume of air/fuel mixture drawn in and the actual volume of the cylinder if it were completely filled. "Pumping Efficiency" is another synonym. Typical figures for naturally aspirated engines is roughly 80%. Turbocharged and supercharged motors almost always have a VE greater than 100%. Fuel tables present in Honda [ECU](/cars/electronics/ecu)s are (in a slightly roundaboout way) volumetric efficiency tables. The VE value is stored as the result VE multiplied by the theoretical maximum airflow corrected for the size of the injector to give a desired [Air Fuel Ratio](/cars/electronics/air-fuel-ratio), i.e. **Injector Size x VE x Theoretical Pumping Possibility** (assumed temperature and atmospheric pressure for [Ideal Gas Law](/cars/electronics/ideal-gas-law) conditions) This is merely a shortcut to save the [ECU](/cars/electronics/ecu) from having to do all the ideal gas law calculations and then multiply by VE to get airflow, and then multiply again by a factor to account for injector size. [Intake Air Temperature Sensor](/cars/electronics/intake-air-temperature-sensor) correction is then used to adjust the fueling to match the actual intake air temp rather than the one assumed in the creation of the VE table.
