---
summary: "I got tired of typing this repeatedly on discussion boards, so I decided to add it here. If you don't know what a Piggy Back controller is, read about it first."
tags: [ecu, reference, tuning, rom, sensors]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Why Do Piggybacks Suck'
    url: /pgmfi/wiki/library/why-do-piggybacks-suck
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Why Do Piggybacks Suck

I got tired of typing this repeatedly on discussion boards, so I decided to add it here. If you don't know what a [Piggy Back](/cars/rom/piggy-back) controller is, read about it first. [Piggy Back](/cars/rom/piggy-back) controllers allow stock [ECU](/cars/ecu/ecu)s to do things that they normally can't do, like run larger injectors or deal with boost. Remember that piggyback controllers work by altering sensor signals **before** they get to the [ECU](/cars/ecu/ecu). Most of the time, the primary signal being messed with is the [Map Sensor](/cars/fueling/map-sensor). This is **critically** important in a [Speed Density](/cars/diagnostics/speed-density) car. The [Map Sensor](/cars/fueling/map-sensor) is used by the [ECU](/cars/ecu/ecu) to guess how much air is going into the car, and therefore how much fuel to supply in order to match airflow. When you "lean" out a car with an AFC, you are simply decreasing the [Map Sensor](/cars/fueling/map-sensor) signal - the [ECU](/cars/ecu/ecu) responds to the decrease in manifold pressure by supplying less fuel. When you "richen" a car with an AFC, you are simply increasing the [Map Sensor](/cars/fueling/map-sensor) signal - the [ECU](/cars/ecu/ecu) responds to the increase in manifold pressure by supplying less fuel. The change in fueling happens for a reason: if you look at a fuel table, [Map Sensor](/cars/fueling/map-sensor) values correspond with columns. When you increase or decrease the signal from the [Map Sensor](/cars/fueling/map-sensor), you are simply making the [ECU](/cars/ecu/ecu) use a different column than it originally would have used. (see [Understanding Maps](/cars/fueling/understanding-maps) if you need some help understanding reading Fuel and Ign tables) But wait, isn't the [Map Sensor](/cars/fueling/map-sensor) used for determining ignition requirements too? When you "lean" out a car with a [Piggy Back](/cars/rom/piggy-back), you also in all likelyhood **advanced timing.** When you "richen" a car with a [Piggy Back](/cars/rom/piggy-back), you also in all likelyhood **retarded timing.** Look at trends horizontally (as MAP changes) in an ignition table, and you will see why this happens. This helps explain why so many boosted cars running on the "AFC hack" have issues due to excessive ignition advance. **The bottom line:**[Piggy Back](/cars/rom/piggy-back) Controllers suck because you cannot independently adjust fuel and ignition. Any changes to fueling will produce a change in ignition too, and often this is undesirable.
