---
summary: 'NVSRAMNon Volatile SRAM fast, byte addressible, byte write, RAM that retains its contents after power is lost.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - wiring
  - conversion
---

# NVSRAM

[NVSRAM](/cars/electronics/nvsram)**Non Volatile [SRAM](/cars/electronics/sram)** - fast, byte addressible, byte write, [RAM](/cars/electronics/ram) that retains its contents after power is lost. [NVSRAM](/cars/electronics/nvsram) usually takes one of several forms: - **Battery backed [SRAM](/cars/electronics/sram)** (Dallas `DS1220`,1230, etc. TI Benchmarq chips, ST ...) - chip contains [SRAM](/cars/electronics/sram), a battery and power sense circuitry. When power fails, the battery backup kicks in and is used to provide power to the [RAM](/cars/electronics/ram) preventing loss of data. **Pros:** looks just like a [SRAM](/cars/electronics/sram) electrically, old technology. **Cons:** cost, large physical size, battery can die after several years
- **EEPROM/SRAM hybrids** (ZMD, Simtek chips, others?) - chip contains [EEPROM](/cars/electronics/eeprom), [SRAM](/cars/electronics/sram) and power sense circuitry. On powerup, data is copied from [EEPROM](/cars/electronics/eeprom) to [SRAM](/cars/electronics/sram). When a powerfail condition is detected, the data in [SRAM](/cars/electronics/sram) is written to [EEPROM](/cars/electronics/eeprom). Often require large(r) capacitors on the power line to ensure a gradual drop on the power line occurs. **Pros:** cheaper, small packages available. **Cons:** long startup time after poweron can require electrical / logical modification of existing designs.
- **FRAM** (Ramtron) - Ferroelectric [RAM](/cars/electronics/ram). Uses a ferroelectric crystal to store the bit. Has the read/write speed of [RAM](/cars/electronics/ram) (~1nS) with the feature of permanently retaining data. Near unlimited write cycles. **Pros:** Available in many packages. Very high endurance cycles. Read/Write speeds the same as [RAM](/cars/electronics/ram). **Cons:** Availability. Minor pinout differences from standard `27C256`. Detailed information on Ramtron's site: [http://www.ramtron.com/doc/AboutFRAM/technology.asp](http://www.ramtron.com/doc/AboutFRAM/technology.asp)
- **MRAM** (Cypress) - chip contains next generation electromagnetic storage. Supposedly overcomes the shortcomings of [EEPROM](/cars/electronics/eeprom)/SRAM hybrids (powerup time) and the form factor / battery life issues of battery backed [SRAM](/cars/electronics/sram) without introducing the peculiar electrical/logical characteristics of FRAM. Overall: looks to be the perfect technology for [Real Time Programming](/cars/electronics/real-time-programming) of devices not designed for it. Hope to see real parts instead of vaporware sometime `Q2` '04
