---
summary: "Author: xtensive Date: 010403 20:47 Ok, here's what I found: That whole area is data tables. The routine that calls the idle value is @279A for the pm6."
tags: [tuning, rom, sensors, reference, diagnostics, ecu]
applies_to:
  obd: [0, 1, 2]
  models: [civic, crx]
  chassis: [ef]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: '91PM6 Target Idle'
    url: /pgmfi/wiki/library/91pm6-target-idle
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# 91PM6 Target Idle

**Author:** xtensive

**Date:** 01-04-03 20:47

Ok, here's what I found: That whole area is data tables. The routine that calls the idle value is @279A for the pm6. The stock idle is set to 768 from what I can tell. It looks up the value at 398F. There are 6 idle settings there...do you know which one it picks for different circumstances? ELD, etc. I assue? George, can you answer a quick question? (This is pm6 code, but should be close to the pm7) The routine that calls this value moves the value @ x3995 to the data pointer, then checks if bit `26h`.2 is set. If it isn then it skips the next step and continues through the code. If it's not set it moves the value @ x398f into the data pointer and continues. My question is why? The value @ x3995 is exactly the same as @ 398f. Weird? Mike

---

**Author:** George

**Date:** 01-04-03 23:51

There are quite a few instances of this in the code, as it seems the PM6 code was derived from the PM7. If you look at the PM7 tables you'll see there is a slight difference - my guess is that when they reused the PM7 code they didn't bother removing that section, instead they made both tables the same. Another instance of this type of thing is in the speed limiter - the code to implement the speed limiter is still in the PM6 code, it's just been set to an extremely high speed.
