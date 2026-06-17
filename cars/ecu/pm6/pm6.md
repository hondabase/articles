---
summary: 'Detailed hardware specifications, pinouts, and custom codebase support for the OBD0 PM6 Civic/CRX Si SOHC ECU.'
tags: [ecu, reference]
applies_to:
  brand: Honda
  ecus: [PM6]
  obd: [0]
  models: [civic, crx, del-sol]
  chassis: [ef, eg, eg-eh, ek]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: PM6
    url: /pgmfi/wiki/library/pm6
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# PM6 ECU (OBD0) Hardware & Code Reference

The **PM6** is the factory OBD0 engine control unit (ECU) utilized in 1988–1991 USDM Honda Civic and CRX Si models powered by the SOHC 1.6L D16A6 engine. 

Due to its simple architecture and widespread availability, the PM6 has historically served as a major development platform for OBD0 Honda tuning, disassembly, and real-time programming.

## Microcontroller Architecture

The PM6 ECU is built around the OKI `83C154` / Intel `80C154` microcontroller family. The ROM code can be extracted, modified, and burnt to standard EPROMs (such as the `27C256`) to adjust fuel maps, ignition maps, rev limits, and other engine parameters.

## Development Resources

The following development files are co-located in this directory:

* [Pm6.asm](Pm6.asm): A comprehensive disassembly of the USDM 1991 PM6 stock ROM, with approximately 95% of the original assembly code fully mapped and commented for developers.

## Board Layout Reference

Below are high-resolution scans of the PM6 ECU printed circuit board (PCB) for component mapping and repair reference:

### 1. Board Top Layout

The top side of the PM6 PCB showing IC locations, capacitors, and resistor packs:

![PM6 ECU circuit board top scan showing electronic components](PM6top.jpg)

### 2. Board Underside Layout

The rear solder side of the PM6 PCB:

![PM6 ECU circuit board bottom solder scan](PM6back.jpg)
