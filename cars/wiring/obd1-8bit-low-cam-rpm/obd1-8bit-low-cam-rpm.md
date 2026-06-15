---
summary: 'This is the conversion from the "low cam" 8bit RPM values used for VTEC crossover points and in the lowcam tables.'
tags: [ecu, reference, tuning, rom, sensors, wiring, conversion, diagnostics]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1 8bit Low Cam RPM'
    url: /pgmfi/wiki/library/obd1-8bit-low-cam-rpm
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1 8bit Low Cam RPM

This is the conversion from the "low cam" 8-bit [RPM](/cars/sensors/rpm) values used for VTEC crossover points and in the low-cam tables. It involves some modular arithmetic, so it's easier to break it up into a couple extra steps. # Y = input value, 0 to 256 # let H = floor(Y/64) ''Where floor(x) = trunc(x) = int(x) = integer part of x. Fractional part truncated. Whatever you want to call it'' # let L = Y - (H-1)*64 # [RPM](/cars/sensors/rpm) = 1875000 * L * 2^H / 240000 You can also do it this way, using the modulo operator: # Y = input value, 0 to 256 # Q = Y div 64 ''(integer division, same as floor(Y/64) above)'' # R = Y mod 64 ''(modulus, i.e. remainder after division)'' # [RPM](/cars/sensors/rpm) = (2^Q)*(floor(R*500/64) + 500) This turns out to be a piecewise linear scale:

- `00h`-`40h` = 500-1000 [RPM](/cars/sensors/rpm)
- `40h`-`80h` = 1000-2000 [RPM](/cars/sensors/rpm)
- `80h`-`C0h` = 2000-4000 [RPM](/cars/sensors/rpm)
- `C0h`-`100h` = 4000-8000 [RPM](/cars/sensors/rpm)

---

EDITED COMMENT: <---- Linear scale??? yeah right!...this formula need to go back to the "drawing board". The values below shows a perfect exponential scale! I have trying this equation and it does not get exact values. Ben's equation on [BRE](/cars/electronics/bre) are more accurate at least on test values...( I don't know the formula for [BRE](/cars/electronics/bre))) That's ''piecewise''-linear. Four linear ranges. It's not a smooth exponential curve. The first formula fairly closely follows the [OBD1](/cars/wiring/obd1) code, while the second is a simplification which gets slightly different results with integer math. By what measure do you consider which is more accurate? See [https://web.archive.org/web/http://pgmfi.org/phorum/read.php?f=13&i=3314&t=2968]() for reference. --AndySloane
