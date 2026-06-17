---
summary: 'Overview of developmental Honda ECU boost control features, utilizing PWM signals for wastegate solenoid pressure regulation.'
tags: [ecu, reference, tuning, rom, sensors]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'ECU Boost Controller'
    url: /pgmfi/wiki/library/ecu-boost-controller
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# ECU Boost Controller

The [Boost Controller](/cars/rom/boost-controller) feature is a DEVELOPMENTAL feature where the [ECU](/cars/ecu/ecu) controls boost by sending a [PWM](/cars/sensors/pwm) signal to a bleed solenoid on the wastegate pressure line, just like an [Electronic Boost Controller](/cars/rom/electronic-boost-controller) would.
