---
summary: 'A Mass Air Flow engine managment system uses a massairflow sensor (Maf Sensor) which is placed in the intake tract to directly measure the mass of air entering the engine.'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
---

# Mass Air Flow

A Mass Air Flow engine managment system uses a mass-air-flow sensor ([Maf Sensor](/cars/electronics/maf-sensor)) which is placed in the intake tract to directly measure the mass of air entering the engine. With this information and the size of the injectors, the [ECU](/cars/electronics/ecu) is able to calculate the fuel injector pulse-width required to deliver the desired [Air Fuel Ratio](/cars/electronics/air-fuel-ratio). MAF systems typically use tables of desired [Air Fuel Ratio](/cars/electronics/air-fuel-ratio)s versus airflow. This differs from [Speed Density](/cars/electronics/speed-density) systems (such as those used in Honda PGM-FI systems) that use [Volumetric Efficiency](/cars/electronics/volumetric-efficiency) tables combined with sensor measurements to estimate airflow without directly measuring it.
