---
summary: 'All you need to do is remove R135. When I modify some P05 ecus I would sometimes get a solid Cruise control light when using an Ex cluster.'
tags: [ecu, reference, sensors]
applies_to:
  obd: [0, 1, 2]
  models: [civic]
  chassis: [eg]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Get Rid Of Cruise Control Upshift Light'
    url: /pgmfi/wiki/library/get-rid-of-cruise-control-upshift-light
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Get Rid Of Cruise Control Upshift Light

All you need to do is remove `R135`. When I modify some [P05](/cars/wiring/p05) ecus I would sometimes get a solid Cruise control light when using an Ex cluster. Or a solid Upshift Light when using a Cx/Vx cluster. So I went in and found that the cruise and upshift light use the same pin on the ECU D18. So i followed the traces and it lead to the `R135` resistor. I removed that resistor and bam, Cruise/Upshift light gone.
