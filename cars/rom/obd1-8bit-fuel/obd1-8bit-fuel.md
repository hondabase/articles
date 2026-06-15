---
summary: "Given table value ''v'' and multiplier value ''m'', the fuel value as seen in a ROM editor is: Fuel(''v'',''m'') = ''vm''/4 The result is presumably proportional..."
tags: [ecu, reference, tuning, rom, sensors]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1 8bit Fuel'
    url: /pgmfi/wiki/library/obd1-8bit-fuel
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1 8bit Fuel

Given table value ''v'' and multiplier value ''m'', the fuel value as seen in a [ROM](/cars/rom/rom) editor is: Fuel(''v'',''m'') = ''v*m''/4

---

The result is presumably proportional to the amount of fuel entering the engine. It has an effective range of 0-16256.25 -- so how does this relate to injector duty cycle? Pulse width (ms) = PW = (''v*m''/4)/100 + 0.60ms = ''v*m''/400 + 0.60ms Max Duty Cycle is (((1000*60*2/rpm)*0.9ms) Duty Cycle = PW/TRPM = (''v*m''/400 + 0.60)/(60000/''RPM'') Simplifying, Duty Cycle = ''RPM''*(''v*m'' + 240)/24000000 ***This is based upon information provided by Didier Pelegri and not verified by myself.***--AndySloane
