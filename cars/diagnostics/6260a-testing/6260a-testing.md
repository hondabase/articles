---
summary: 'Technical analysis of the Honda 6260A ECU test code, explaining how it triggers the diagnostic LED to flash engine error codes.'
tags: [ecu, reference, sensors, diagnostics]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: '6260A Testing'
    url: /pgmfi/wiki/library/6260a-testing
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# 6260A Testing

J. Wong: about the 6260A thing... if you take a look at the code ([91 PM6_ECU_LED_CEL](/cars/diagnostics/91pm6-ecu-led-cel)) that flashes the [ECU](/cars/ecu/ecu) LED for codes you'll see that it writes #16 or #96 to X2000, depending on certain conditions. A bench experiment i want to do is to replace 16/96 with other values and see what happens... like instead of the led flashing, observe what other line would toggle
