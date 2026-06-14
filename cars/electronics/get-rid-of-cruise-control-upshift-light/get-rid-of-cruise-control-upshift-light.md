---
summary: 'All you need to do is remove R135. When I modify some P05 ecus I would sometimes get a solid Cruise control light when using an Ex cluster.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ecu
  - reference
  - sensors
---

# Get Rid Of Cruise Control Upshift Light

All you need to do is remove `R135`. When I modify some [P05](/cars/electronics/p05) ecus I would sometimes get a solid Cruise control light when using an Ex cluster. Or a solid Upshift Light when using a Cx/Vx cluster. So I went in and found that the cruise and upshift light use the same pin on the ECU D18. So i followed the traces and it lead to the `R135` resistor. I removed that resistor and bam, Cruise/Upshift light gone.
