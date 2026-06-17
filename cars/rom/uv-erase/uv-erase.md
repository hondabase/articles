---
summary: 'Technical guide to using UV light for erasing EPROM chips with transparent windows for re-programming.'
tags: [tuning, rom, eprom, hardware]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# UV EPROM Erasure Procedures

Many EPROM chips feature a quartz glass window on the top of the package. Exposing the silicon die to short-wave ultraviolet (UV-C) light will erase the stored data, allowing the chip to be reprogrammed and reused.

## Requirements for Erasure
To successfully erase an EPROM, the chip must be exposed to high-intensity UV-C light (typically 254 nm wavelength).

> [!WARNING]
> UV-C light is harmful to human skin and eyes. Always operate UV erasure equipment inside a light-tight enclosure and avoid direct exposure to the light source.

> [!IMPORTANT]
> Standard "blacklight" (UV-A) lamps and direct sunlight are insufficient for erasing EPROM chips. These sources lack the necessary intensity and wavelength to clear the memory cells.

## Erasure Process
1. **Preparation:** Ensure the EPROM window is clean and free of debris or labels.
2. **Exposure:** Place the chip inside a dedicated UV EPROM eraser.
3. **Duration:** Follow the manufacturer's specifications for the specific chip model. Typical exposure times range from 15 to 30 minutes depending on the intensity of the UV source and the age of the bulb.
4. **Verification:** After the cycle is complete, verify the chip is blank using an EPROM programmer before attempting to write new data.

## Equipment
If a commercial UV eraser is unavailable, a DIY solution can be constructed using a germicidal UV-C bulb. Ensure the housing is constructed from opaque, light-blocking material to prevent UV leakage.

> [!TIP]
> If a chip fails to verify as blank after a standard exposure cycle, increase the exposure time. Over-exposure to UV light will not damage the chip, provided the housing remains intact.