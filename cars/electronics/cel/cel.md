---
summary: 'Check Engine Light This indicator (usually on the dash) comes on to indicate that the ECU thinks something is wrong.'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: intermediate
tags:
  - hardware
  - education
  - ecu
  - tuning
  - rom
  - sensors
  - reference
  - wiring
  - conversion
  - diagnostics
---

# CEL

###  Check Engine Light 

This indicator (usually on the dash) comes on to indicate that the [ECU](/cars/electronics/ecu) thinks something is wrong. The [ECU](/cars/electronics/ecu) will usually indicate an error code by flashing the [CEL](/cars/electronics/cel) in some manner. - On [OBD0](/cars/electronics/obd0) cars, there is a window on the [ECU](/cars/electronics/ecu) through which a blinking LED can be seen to read codes.

- On [OBD1](/cars/electronics/obd1) cars, there is a connector located under the dash by the passenger footwell that must be shorted. This will cause the dash [CEL](/cars/electronics/cel) to blink, indicating which codes are being thrown.

- On [OBD2](/cars/electronics/obd2) cars, there is a connector located under the dash by the passenger footwell that must be shorted. This will cause the dash [CEL](/cars/electronics/cel) to blink, indicating which codes are being thrown. You can also use an [OBD2](/cars/electronics/obd2) scan tool which connects to the plug by the driver's side footwell. It is a gray connector that should be easily identifiable.

####  Solid Check Engine Light 

If the [CEL](/cars/electronics/cel) is lit solid and does not blink (after jumping the service check connector on [OBD1](/cars/electronics/obd1) ) and the car runs poorly the following could be the problem: - A faulty [ECU](/cars/electronics/ecu) (means any other component failure other than listed here)
- Poor soldering connections
- [Check Sum](/cars/electronics/check-sum) error
- Faulty program stored in the [ROM](/cars/electronics/rom)
- Faulty [ROM](/cars/electronics/rom) chip
- Faulty `74HC373` chip

See [Troubleshooting Solid CEL](/cars/electronics/troubleshooting-solid-cel)####  "Phantom" Check Engine Light 

Sometimes you may get a [CEL](/cars/electronics/cel) that doesn't show up when you turn the car off. In order to check these, you must do the following: - DON'T turn the ignition off
- Jump the service check connector just like normal

Now the [CEL](/cars/electronics/cel) will turn off briefly and then start flashing the codes like normal. See [Honda Error Codes](/cars/electronics/honda-error-codes)
