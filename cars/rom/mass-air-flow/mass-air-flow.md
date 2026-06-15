---
summary: 'A Mass Air Flow engine managment system uses a massairflow sensor (Maf Sensor) which is placed in the intake tract to directly measure the mass of air entering the engine.'
tags: [ecu, reference, tuning, rom, sensors]
applies_to:
  obd: [0, 1, 2]
  brand: Honda
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Mass Air Flow'
    url: /pgmfi/wiki/library/mass-air-flow
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Mass Air Flow

A Mass Air Flow engine managment system uses a mass-air-flow sensor ([Maf Sensor](/cars/wiring/maf-sensor)) which is placed in the intake tract to directly measure the mass of air entering the engine. With this information and the size of the injectors, the [ECU](/cars/ecu/ecu) is able to calculate the fuel injector pulse-width required to deliver the desired [Air Fuel Ratio](/cars/fueling/air-fuel-ratio). MAF systems typically use tables of desired [Air Fuel Ratio](/cars/fueling/air-fuel-ratio)s versus airflow. This differs from [Speed Density](/cars/diagnostics/speed-density) systems (such as those used in Honda PGM-FI systems) that use [Volumetric Efficiency](/cars/rom/volumetric-efficiency) tables combined with sensor measurements to estimate airflow without directly measuring it.
