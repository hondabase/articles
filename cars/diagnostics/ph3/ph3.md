---
summary: 'THe 8889 Accord OBD0 B20A ECU uses an Electronic Advance distributor. It has an External 27c256 ROM and is oki 80c154 based This ECU is very similar to the PK2 ECU for the 8891 Prelude.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
applies_to:
  obd: [0, 1, 2]
  brand: Honda
  models: [accord, civic, integra, prelude]
  chassis: [dc2, eg, ek]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: PH3
    url: /pgmfi/wiki/library/ph3
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# PH3

THe 88-89 Accord [OBD](/cars/wiring/obd)-0 B20A [ECU](/cars/ecu/ecu) uses an Electronic Advance distributor. It has an External `27C256` [ROM](/cars/rom/rom) and is oki `80C154` based
This [ECU](/cars/ecu/ecu) is very similar to the PK2 [ECU](/cars/ecu/ecu) for the 88-91 Prelude. However, it has the second O2 sensor disabled via BR8

The 86-87 Accord [OBD](/cars/wiring/obd)-0 B20A is oki80c514 based but has a 27c128 rom.
It does not have a backup processor but seems to use 2 OKI processors instead
This [ECU](/cars/ecu/ecu) has 2 diagnostics Leds Note, the latest PH3 and PK2 [ECU](/cars/ecu/ecu)s share almost the same board they are 99% similar, only slight differences can be seens between them.
They are so similar that they can even share the same program so far.

---

I posted the Options Close-up for the PH3-0732 and PH3-0632 88-89 Accord B20A [ECU](/cars/ecu/ecu)s. The 0732 is supposedly from an auto car and the 0632 a manual. I don't know if these options are related to the transmisson type or emissions. The manual PK2 [ECU](/cars/ecu/ecu) has the same options configuration as this Auto [ECU](/cars/ecu/ecu) so I'm not sure what these do yet There is also a close-up of the BR8 jumper. This jumper seems to be the one deactivating O2 sensor B input on the PH3 board. It's connected directly on the Sensor's pin. The PK2 shares almost the same Boads as the PH3 but has this jumper Blank. (see the PK2 [ECU](/cars/ecu/ecu) section) Carotman | **Attachment:** | **Modify:** | **Size:** | **Date:** | **Who:** | **Comment:** | | :--- | :--- | :--- | :--- | :--- | :--- | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [ph3\\_0732.jpg](ph3_0732.jpg) | mod | 212615 | 30 Jan 2006 - 07:01 | carotman | 88-89 Accord B20A PH3 [ECU](/cars/ecu/ecu) | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [ph3\\_043.jpg](ph3_043.jpg) | mod | 341522 | 30 Jan 2006 - 07:08 | carotman | 86-87 Accord B20A PH3 [ECU](/cars/ecu/ecu) | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [ph3-0632\\_manual\\_options.jpg](ph3-0632_manual_options.jpg) | mod | 1056389 | 07 Apr 2006 - 02:44 | carotman | PH3-0632 Manual [ECU](/cars/ecu/ecu) (Options Close-up) | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [ph3-0632\\_manual.jpg](ph3-0632_manual.jpg) | mod | 1054856 | 07 Apr 2006 - 02:45 | carotman | PH3-0632 Accord ECU (Manual) | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [ph3-0732\\_auto\\_options.jpg](ph3-0732_auto_options.jpg) | mod | 1059425 | 07 Apr 2006 - 02:46 | carotman | PH3-0732 Auto [ECU](/cars/ecu/ecu) (Options Close-up) | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [ph3-0732\\_auto.jpg](ph3-0732_auto.jpg) | mod | 1082686 | 07 Apr 2006 - 02:49 | carotman | PH3-0732 Auto [ECU](/cars/ecu/ecu) | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [BR8-PH3.jpg](BR8-PH3.jpg) | mod | 1061228 | 07 Apr 2006 - 03:03 | carotman | BR8 Jumper that seem to cancel O2 sensor B input |
