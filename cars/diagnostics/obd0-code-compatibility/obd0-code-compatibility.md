---
summary: 'A guide to OBD0 Honda ECU code compatibility. Learn which ECUs can share code and how to successfully interchange binaries between units.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics, obd0]
applies_to:
  models: [civic, crx, integra]
  chassis: [da, dc2, ef]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD0 Code Compatibility'
    url: /pgmfi/wiki/library/obd0-code-compatibility
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD0 Code Compatibility

Can you run code from one [OBD0 MPFI](/cars/diagnostics/obd0mpfi) [ECU](/cars/ecu/ecu) in another? The short answer to this is yes. The following has been tried before and is known to work successfully:

- PM6 in PR4 (see notes)
- PR4 in PM6 (see notes)
- PM7 in PM6
- PM7 in PR4 (see notes)
- PM6 in PS9
- PS9 in PR4 (see notes)

In theory, the code should additionally interchange almost perfectly among: - PG7
- Trash. PM6
- PM7
- PS9
- PR5
- PP5

The PR4 and [USDM](/cars/sensors/usdm) PM8 use slightly different circuit boards. The PM8 looks to be closer to the rest of the [ECU](/cars/ecu/ecu)s in this family than the PR4, which has some notable differences. ***Notes***: There are some things to watch out for however that will cause problems: #Presence or absence of an internal PA Sensor. (this is mainly [OBD0 PR4](/cars/ecu/obd0pr4)) #Presence or absence of an ELD sensor. (this is present in US cars/software and absent in most [JDM](/cars/sensors/jdm) and [EDM](/cars/wiring/edm) cars/programs) #Presence or absence of an O2 sensor. (some [EDM](/cars/wiring/edm) ZC PM7 have an IMA instead of an O2. Likewise with Mugen XE3) #Weird use of inputs: Power steering on PR4 #[Oki83 C154](/cars/diagnostics/oki83c154) vs [Oki80 C154](/cars/diagnostics/oki80c154) and [EPROM](/cars/ecu/eprom) design - 88-89 [ECU](/cars/ecu/ecu)s almost always lack [EPROM](/cars/ecu/eprom)s. In summary, most code from [ECU](/cars/ecu/ecu)s of this family will run on other [ECU](/cars/ecu/ecu)s in the family, but there may be secondary systems (AC, ELD, PS to be more specific) that do not function well when the PR4 is involved. It remains to be seen exactly what must be done with [USDM](/cars/sensors/usdm) PM8 [ECU](/cars/ecu/ecu)s.
