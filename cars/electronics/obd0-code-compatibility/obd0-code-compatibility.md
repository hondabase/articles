---
summary: 'Can you run code from one OBD0 MPFI ECU in another? The short answer to this is yes. The following has been tried before and is known to work successfully:...'
applies_to:
  obd: [0]
complexity: advanced
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - diagnostics
---

# OBD0 Code Compatibility

Can you run code from one [OBD0 MPFI](/cars/electronics/obd0mpfi) [ECU](/cars/electronics/ecu) in another? The short answer to this is yes. The following has been tried before and is known to work successfully:

- PM6 in PR4 (see notes)
- PR4 in PM6 (see notes)
- PM7 in PM6
- PM7 in PR4 (see notes)
- PM6 in PS9
- PS9 in PR4 (see notes)

In theory, the code should additionally interchange almost perfectly among: - PG7
- Trash.PM6
- PM7
- PS9
- PR5
- PP5

The PR4 and [USDM](/cars/electronics/usdm) PM8 use slightly different circuit boards. The PM8 looks to be closer to the rest of the [ECU](/cars/electronics/ecu)s in this family than the PR4, which has some notable differences. ***Notes***: There are some things to watch out for however that will cause problems: #Presence or absence of an internal PA Sensor. (this is mainly [OBD0 PR4](/cars/electronics/obd0pr4)) #Presence or absence of an ELD sensor. (this is present in US cars/software and absent in most [JDM](/cars/electronics/jdm) and [EDM](/cars/electronics/edm) cars/programs) #Presence or absence of an O2 sensor. (some [EDM](/cars/electronics/edm) ZC PM7 have an IMA instead of an O2. Likewise with Mugen XE3) #Weird use of inputs: Power steering on PR4 #[Oki83 C154](/cars/electronics/oki83c154) vs [Oki80 C154](/cars/electronics/oki80c154) and [EPROM](/cars/electronics/eprom) design - 88-89 [ECU](/cars/electronics/ecu)s almost always lack [EPROM](/cars/electronics/eprom)s. In summary, most code from [ECU](/cars/electronics/ecu)s of this family will run on other [ECU](/cars/electronics/ecu)s in the family, but there may be secondary systems (AC, ELD, PS to be more specific) that do not function well when the PR4 is involved. It remains to be seen exactly what must be done with [USDM](/cars/electronics/usdm) PM8 [ECU](/cars/electronics/ecu)s.
