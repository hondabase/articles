---
summary: 'A hardware/software interaction will determine whether a program in an ECU behaves as a manual or auto.'
tags: [ecu, reference, sensors, diagnostics]
applies_to:
  obd: [0, 1, 2]
  models: [civic, crx, del-sol, integra]
  chassis: [dc2, ef, eg, eg-eh]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Auto Or Manual'
    url: /pgmfi/wiki/library/auto-or-manual
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Auto Or Manual

A hardware/software interaction will determine whether a program in an [ECU](/cars/ecu/ecu) behaves as a manual or auto. Hardware configuration of RP17/RP18 determines whether the [ECU](/cars/ecu/ecu) hardware is setup for auto or manual. See [Auto To Manual](/cars/wiring/auto-to-manual) to learn how to change the hardware. If an [ECU](/cars/ecu/ecu) is jumpered to be a manual, it will always run like a manual. [ECU](/cars/ecu/ecu) programs are responsible for checking the jumper configuration in order to enable auto transmission control. What this means is that you can make a [ECU](/cars/ecu/ecu) that is jumpered to be an automatic think that it is a manual using a program that has the auto circuitry check disabled. The most notable example of this type of program are the numerous "mugen" programs. Also, (I may be mistaken on this) some stock programs ([EDM](/cars/wiring/edm) P30???) do not check for the auto trans jumper config. Most [USDM](/cars/sensors/usdm) (P74/P75, P28, PM6, etc.) definately ***do*** check for the auto trans jumpers.

### Summary: 

- If you need to make an automatic [ECU](/cars/ecu/ecu) manual, you can either modify the hardware per [Auto To Manual](/cars/wiring/auto-to-manual) ***OR*** disable the check for the jumpers in software using a modified program(***OR*** do both).
- If you require the [ECU](/cars/ecu/ecu) to control an automatic transmission, you must make sure that you use a base program that checks for the auto trans jumpers and has the necessary code. [USDM](/cars/sensors/usdm) P28 is my failsafe (Dave B)
