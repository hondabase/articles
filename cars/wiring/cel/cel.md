---
summary: 'Check Engine Light This indicator (usually on the dash) comes on to indicate that the ECU thinks something is wrong.'
tags: [hardware, education, ecu, tuning, rom, sensors, reference, wiring, conversion, diagnostics]
applies_to:
  obd: [0, 1, 2]
  brand: Honda
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: CEL
    url: /pgmfi/wiki/library/cel
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# CEL

###  Check Engine Light 

This indicator (usually on the dash) comes on to indicate that the [ECU](/cars/ecu/ecu) thinks something is wrong. The [ECU](/cars/ecu/ecu) will usually indicate an error code by flashing the [CEL](/cars/wiring/cel) in some manner. - On [OBD0](/cars/rom/obd0) cars, there is a window on the [ECU](/cars/ecu/ecu) through which a blinking LED can be seen to read codes.

- On [OBD1](/cars/wiring/obd1) cars, there is a connector located under the dash by the passenger footwell that must be shorted. This will cause the dash [CEL](/cars/wiring/cel) to blink, indicating which codes are being thrown.

- On [OBD2](/cars/wiring/obd2) cars, there is a connector located under the dash by the passenger footwell that must be shorted. This will cause the dash [CEL](/cars/wiring/cel) to blink, indicating which codes are being thrown. You can also use an [OBD2](/cars/wiring/obd2) scan tool which connects to the plug by the driver's side footwell. It is a gray connector that should be easily identifiable.

####  Solid Check Engine Light 

If the [CEL](/cars/wiring/cel) is lit solid and does not blink (after jumping the service check connector on [OBD1](/cars/wiring/obd1) ) and the car runs poorly the following could be the problem: - A faulty [ECU](/cars/ecu/ecu) (means any other component failure other than listed here)
- Poor soldering connections
- [Check Sum](/cars/diagnostics/check-sum) error
- Faulty program stored in the [ROM](/cars/rom/rom)
- Faulty [ROM](/cars/rom/rom) chip
- Faulty `74HC373` chip

See [Troubleshooting Solid CEL](/cars/diagnostics/troubleshooting-solid-cel)####  "Phantom" Check Engine Light 

Sometimes you may get a [CEL](/cars/wiring/cel) that doesn't show up when you turn the car off. In order to check these, you must do the following: - DON'T turn the ignition off
- Jump the service check connector just like normal

Now the [CEL](/cars/wiring/cel) will turn off briefly and then start flashing the codes like normal. See [Honda Error Codes](/cars/diagnostics/honda-error-codes)
