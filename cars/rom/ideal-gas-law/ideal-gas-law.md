---
summary: 'Application of the Ideal Gas Law in Honda speed-density engine management systems for calculating fuel requirements based on pressure and temperature.'
tags: [tuning, rom, sensors, reference]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Ideal Gas Law'
    url: /pgmfi/wiki/library/ideal-gas-law
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Ideal Gas Law

the Ideal Gas Law is an equation you may or may not remember from high school chemistry. **PV = nRT**

- **P** = Pressure (must be an [Absolute Pressure](/cars/diagnostics/absolute-pressure) scale)
- **V** = Volume
- **n** = number of moles (number of atoms) gas
- **R** = ideal gas constant = 8.3145 J/mol K
- **T** = temperature (always in degrees Kelvin for this calculation - absolute scale)

The form of the ideal gas law most applicable to engine management is **n = PV / RT** By solving for **n**, we are solving for the actual airflow into the motor as estimated by pressure, temperature and volume factors measured elsewhere. One random googled writeup from a college class: [http://www.chm.davidson.edu/ChemistryApplets/GasLaws/GasConstant.html](http://www.chm.davidson.edu/ChemistryApplets/GasLaws/GasConstant.html)
