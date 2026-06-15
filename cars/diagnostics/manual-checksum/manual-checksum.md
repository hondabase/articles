---
summary: 'There are two ways to fix a checksum error. The first is to change the program of the ROM in such a way that the checksum routine is disabled / removed.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
applies_to:
  obd: [0, 1]
  models: [civic, crx]
  chassis: [ef]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Manual Checksum'
    url: /pgmfi/wiki/library/manual-checksum
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Manual Checksum

There are two ways to fix a checksum error. The first is to change the program of the [ROM](/cars/rom/rom) in such a way that the checksum routine is disabled / removed. Learn to code if you want to do this. If you are content to workaround the checksum procedure, keep reading. The checksum in all [OBD0](/cars/rom/obd0) /1 [ROM](/cars/rom/rom)s is 8 bit - meaning it will vary from 0 to 255. (00-FF hex) To figure out what the checkum is, you need to do a 8-bit [Check Sum](/cars/diagnostics/check-sum) over the file. I believe the PM6 cares about the area from 0000-4FFF. Most [OBD1](/cars/wiring/obd1) [ECU](/cars/ecu/ecu)s care about the whole [ROM](/cars/rom/rom). I believe winhex can calculate this, and you can also get a utility called check8 from [http://www.keil.com](http://www.keil.com). This will work nicely too... Anyways, lets say you run the checksum program and you get a checksum of A3 (hex). Subtract A3 from FF: FF -A3 = 5C Now find a "FF" somewhere in the range the [ECU](/cars/ecu/ecu) is using for checksum. It's best to look for a block of "FF"s as that generally indicates unused [ROM](/cars/rom/rom) space. Change the FF to whatever the result of your subtraction is. Voila. Checksum fixed.
