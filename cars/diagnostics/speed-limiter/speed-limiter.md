---
summary: 'A speed limiter limits the top speed of a car. In almost all hondas, a Speed Limiter will be implemented as a piece of code that reads the Vehicle Speed Sensor and cuts fuel above a certain speed.'
tags: [ecu, reference, sensors, diagnostics]
applies_to:
  obd: [0, 1, 2]
  brand: Honda
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Speed Limiter'
    url: /pgmfi/wiki/library/speed-limiter
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Speed Limiter

A speed limiter limits the top speed of a car. In almost all hondas, a [Speed Limiter](/cars/diagnostics/speed-limiter) will be implemented as a piece of code that reads the [Vehicle Speed Sensor](/cars/wiring/vehicle-speed-sensor) and cuts fuel above a certain speed. [JDM](/cars/sensors/jdm) [ECU](/cars/ecu/ecu)s are famous for having speed limiters. If you want to go faster than 180kph without reprogramming [ECU](/cars/ecu/ecu) you can use Hondainfo's Speed Limit Defencer device. [Hondainfo Speed Limit Defencer](http://web.archive.org/web/20041120201535/http://cvs.sourceforge.net:80/viewcvs.py/pgmfi/Speed%20Limit%20Defencer/)
