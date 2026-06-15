---
summary: 'Electronic Load Detector measures electrical load used to determine if the alternator should be in low or high output mode.'
tags: [sensors, reference]
applies_to:
  obd: [0, 1, 2]
  brand: Honda
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Electrical Load Detector'
    url: /pgmfi/wiki/library/electrical-load-detector
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Electrical Load Detector

Electronic Load Detector measures electrical load - used to determine if the alternator should be in low or high output mode. Since Hondas are running so lean at idle, virtually any load will cause the idle to drop. Even small electrical loads, such as the turn signals, will cause the idle to fluctuate. The electrical load detector (ELD) was added to later model Hondas to monitor for any significant electrical loads. It sends a warning signal to the ECM before the load has a chance to effect the idle. The ECM makes slight adjustments to the idle air control (IAC) valve, injector PW, and ignition timing to compensate for the electrical load.
