---
summary: 'It is possible to replace the ignitor in the distributor with a solid state circuit to trigger the input of a MSD/Crane/etc.'
tags: [ecu, reference]
applies_to:
  obd: [0, 1, 2]
  brand: Honda
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Ignitor Replacement'
    url: /pgmfi/wiki/library/ignitor-replacement
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Ignitor Replacement

It is possible to replace the ignitor in the distributor with a solid state circuit to trigger the input of a MSD/Crane/etc.

---

Dave: Note that the ZTX857 is not an absolute requirement. It's just that it was the same size as the transistor it replaced. You could use any power Darlington NPN that can handle a couple amps. Mirror away. John at jands.com (J&S Safeguard) ---

schematic: 
 ![HondaToMSD.gif](HondaToMSD.gif)
