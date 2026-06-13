---
summary: "I got tired of typing this repeatedly on discussion boards, so I decided to add it here. If you don't know what a Piggy Back controller is, read about it first."
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
---

# Why Do Piggybacks Suck

I got tired of typing this repeatedly on discussion boards, so I decided to add it here. If you don't know what a [Piggy Back](/cars/electronics/piggy-back) controller is, read about it first. [Piggy Back](/cars/electronics/piggy-back) controllers allow stock [ECU](/cars/electronics/ecu)s to do things that they normally can't do, like run larger injectors or deal with boost. Remember that piggyback controllers work by altering sensor signals **before** they get to the [ECU](/cars/electronics/ecu). Most of the time, the primary signal being messed with is the [Map Sensor](/cars/electronics/map-sensor). This is **critically** important in a [Speed Density](/cars/electronics/speed-density) car. The [Map Sensor](/cars/electronics/map-sensor) is used by the [ECU](/cars/electronics/ecu) to guess how much air is going into the car, and therefore how much fuel to supply in order to match airflow. When you "lean" out a car with an AFC, you are simply decreasing the [Map Sensor](/cars/electronics/map-sensor) signal - the [ECU](/cars/electronics/ecu) responds to the decrease in manifold pressure by supplying less fuel. When you "richen" a car with an AFC, you are simply increasing the [Map Sensor](/cars/electronics/map-sensor) signal - the [ECU](/cars/electronics/ecu) responds to the increase in manifold pressure by supplying less fuel. The change in fueling happens for a reason: if you look at a fuel table, [Map Sensor](/cars/electronics/map-sensor) values correspond with columns. When you increase or decrease the signal from the [Map Sensor](/cars/electronics/map-sensor), you are simply making the [ECU](/cars/electronics/ecu) use a different column than it originally would have used. (see [Understanding Maps](/cars/electronics/understanding-maps) if you need some help understanding reading Fuel and Ign tables) But wait, isn't the [Map Sensor](/cars/electronics/map-sensor) used for determining ignition requirements too? When you "lean" out a car with a [Piggy Back](/cars/electronics/piggy-back), you also in all likelyhood **advanced timing.** When you "richen" a car with a [Piggy Back](/cars/electronics/piggy-back), you also in all likelyhood **retarded timing.** Look at trends horizontally (as MAP changes) in an ignition table, and you will see why this happens. This helps explain why so many boosted cars running on the "AFC hack" have issues due to excessive ignition advance. **The bottom line:**[Piggy Back](/cars/electronics/piggy-back) Controllers suck because you cannot independently adjust fuel and ignition. Any changes to fueling will produce a change in ignition too, and often this is undesirable.
