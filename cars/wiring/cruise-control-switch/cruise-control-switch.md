---
summary: "Author: tungsten2k (12240101225.client.attbi.com) Date: 091903 01:36 fyi, for you EF people out there lookin' to do your FTS clutch switch the easy way, you've come to the right place."
tags: [ecu, reference, tuning, rom, wiring, conversion]
applies_to:
  obd: [0, 1, 2]
  chassis: [ef]
  models: {}
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Cruise Control Switch'
    url: /pgmfi/wiki/library/cruise-control-switch
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Cruise Control Switch

Author: tungsten2k (12-240-101-225.client.attbi.com) Date: 09-19-03 01:36 fyi, for you EF people out there lookin' to do your FTS clutch switch the easy way, you've come to the right place... Before : [http://www.se30.com/~grindingbassline/albums/ecu-mods/IMG_3796_002.sized.jpg](http://www.se30.com/~grindingbassline/albums/ecu-mods/IMG_3796_002.sized.jpg)After the ghetto mcgyver's personal treatment : Ghettoshift 1.0 [http://www.se30.com/~grindingbassline/albums/ecu-mods/IMG_3802.sized.jpg](http://www.se30.com/~grindingbassline/albums/ecu-mods/IMG_3802.sized.jpg)yes, that's right kids... crack open the jam nut, unscrew the original clutch stop adjuster, and slide in a brake light switch just like the one on... uh... that switch one pedal to the right ;) it cost me $2 to get into Pick-n-Pull... i walked out with 6 of these babies, (and an extra main relay, more fuses and interior screws than a Kragen store... pretty much all i could fit into my 6 pocket raver pants ;) now, this SPST Momentary Off brake switch requires that when the switch contacts are closed -> FTS rev limit, and when open -> regular limit. it might make more sense reverse the logic so that in the event of circuit failure (e.g. switch or wire not working) you're stuck in FTS limit, instead of lining up at the drags, putting in the clutch with your Im ABad Mutha Fukka With No Rev Limit.bin and listening to the valve heads break off into the piston tops. but whatever... how often do you find a brake switch failing ? :P
