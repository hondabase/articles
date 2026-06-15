---
summary: 'NVSRAMNon Volatile SRAM fast, byte addressible, byte write, RAM that retains its contents after power is lost.'
tags: [ecu, reference, tuning, rom, sensors, wiring, conversion]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: NVSRAM
    url: /pgmfi/wiki/library/nvsram
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# NVSRAM

[NVSRAM](/cars/wiring/nvsram)**Non Volatile [SRAM](/cars/sensors/sram)** - fast, byte addressible, byte write, [RAM](/cars/reference/ram) that retains its contents after power is lost. [NVSRAM](/cars/wiring/nvsram) usually takes one of several forms: - **Battery backed [SRAM](/cars/sensors/sram)** (Dallas `DS1220`,1230, etc. TI Benchmarq chips, ST ...) - chip contains [SRAM](/cars/sensors/sram), a battery and power sense circuitry. When power fails, the battery backup kicks in and is used to provide power to the [RAM](/cars/reference/ram) preventing loss of data. **Pros:** looks just like a [SRAM](/cars/sensors/sram) electrically, old technology. **Cons:** cost, large physical size, battery can die after several years
- **EEPROM/SRAM hybrids** (ZMD, Simtek chips, others?) - chip contains [EEPROM](/cars/diagnostics/eeprom), [SRAM](/cars/sensors/sram) and power sense circuitry. On powerup, data is copied from [EEPROM](/cars/diagnostics/eeprom) to [SRAM](/cars/sensors/sram). When a powerfail condition is detected, the data in [SRAM](/cars/sensors/sram) is written to [EEPROM](/cars/diagnostics/eeprom). Often require large(r) capacitors on the power line to ensure a gradual drop on the power line occurs. **Pros:** cheaper, small packages available. **Cons:** long startup time after poweron can require electrical / logical modification of existing designs.
- **FRAM** (Ramtron) - Ferroelectric [RAM](/cars/reference/ram). Uses a ferroelectric crystal to store the bit. Has the read/write speed of [RAM](/cars/reference/ram) (~1nS) with the feature of permanently retaining data. Near unlimited write cycles. **Pros:** Available in many packages. Very high endurance cycles. Read/Write speeds the same as [RAM](/cars/reference/ram). **Cons:** Availability. Minor pinout differences from standard `27C256`. Detailed information on Ramtron's site: [http://www.ramtron.com/doc/AboutFRAM/technology.asp](http://www.ramtron.com/doc/AboutFRAM/technology.asp)
- **MRAM** (Cypress) - chip contains next generation electromagnetic storage. Supposedly overcomes the shortcomings of [EEPROM](/cars/diagnostics/eeprom)/SRAM hybrids (powerup time) and the form factor / battery life issues of battery backed [SRAM](/cars/sensors/sram) without introducing the peculiar electrical/logical characteristics of FRAM. Overall: looks to be the perfect technology for [Real Time Programming](/cars/sensors/real-time-programming) of devices not designed for it. Hope to see real parts instead of vaporware sometime `Q2` '04
