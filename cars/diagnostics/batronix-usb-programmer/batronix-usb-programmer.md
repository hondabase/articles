---
summary: 'The Batronix USB Programmer is a slightly more polished product than their Eprommer3.3. As of October 9, 2003, it costs $248.'
tags: [tuning, rom, sensors, reference, diagnostics, ecu]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Batronix USB Programmer'
    url: /pgmfi/wiki/library/batronix-usb-programmer
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Batronix USB Programmer

The [Batronix USB Programmer](http://web.archive.org/web/20061114093738/http://www.progshop.com/shop/programmer/usb-chip-programmer/index.shtml) is a slightly more polished product than their Eprommer3.3. As of October 9, 2003, it costs $248. At that price, I'd look elsewhere, but that's just me... (Dave) Some comments:

**Author:** alphajesse

**Date:** 08-22-03 02:21

Got all the stuff tonight when I got home from work! This thing has got some mass to it! The software looks good too... It burns really fast- a 256k UV chip was done in seconds! Too bad I can't test it out yet- my sockets and other stuff have yet to arrive from futurlec- hopefully tomorrow. Having some issues with the flash 27SF chips batronix sells... sorry for the double post on this! Also, how do I know which pin is pin #1? right now I'm getting that error trying to burn `27SF256` that I bought from batronix... the 27c256b chips I got burn no problem though. It looks like it doesn't program the chip at all- subsequent reads show everything as 00... wtf?? I'm using the USB programmer, so it gets power from my USB hub (a powered unit) and the UV-erase chips I have work perfect... I've got the latest version 5.24 as well... supposedly this thing supports the flash chips, though!

**EDIT:** My problems had to do with me putting the chips in backwards! I am a retard! This thing works without fail 100% of the time. Chips are burned and verified in less than 10 seconds.
