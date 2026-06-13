---
summary: 'the Ideal Gas Law is an equation you may or may not remember from high school chemistry. PV = nRT P = Pressure (must be an Absolute Pressure scale) V =...'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - tuning
  - rom
  - sensors
  - reference
---

# Ideal Gas Law

the Ideal Gas Law is an equation you may or may not remember from high school chemistry. **PV = nRT**

- **P** = Pressure (must be an [Absolute Pressure](/cars/electronics/absolute-pressure) scale)
- **V** = Volume
- **n** = number of moles (number of atoms) gas
- **R** = ideal gas constant = 8.3145 J/mol K
- **T** = temperature (always in degrees Kelvin for this calculation - absolute scale)

The form of the ideal gas law most applicable to engine management is **n = PV / RT** By solving for **n**, we are solving for the actual airflow into the motor as estimated by pressure, temperature and volume factors measured elsewhere. One random googled writeup from a college class: [http://www.chm.davidson.edu/ChemistryApplets/GasLaws/GasConstant.html](http://www.chm.davidson.edu/ChemistryApplets/GasLaws/GasConstant.html)
