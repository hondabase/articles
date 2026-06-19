---
summary: 'What is a Speed Density engine managment scheme? Speed Density systems calculate the amount of air entering a motor using sensors that monitor engine operating conditions.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
applies_to:
  brand: Honda
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Speed Density'
    url: /pgmfi/wiki/library/speed-density
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Speed Density

What is a [Speed Density](/cars/diagnostics/speed-density) engine managment scheme? [Speed Density](/cars/diagnostics/speed-density) systems calculate the amount of air entering a motor using sensors that monitor engine operating conditions. The [Ideal Gas Law](/cars/rom/ideal-gas-law) (**PV = nRT**) is the basis for this type of engine management. Instead of directly measuring the amount of air entering the motor ("n" in the above equation), speed-density systems estimate it using **n = PV / RT**, and then applying additional corrections. Fuel tables in a honda [ECU](/cars/ecu/ecu) (from a theoretical standpoint) are Volumetric Efficiency (VE) tables. Basic operation:

- A [Map Sensor](/cars/fueling/map-sensor) is used to measure the pressure of air in the intake manifold (DENSITY term in speed-density). This provides the **P** term in the [Ideal Gas Law](/cars/rom/ideal-gas-law) calulation.
- The engine's rotational speed (SPEED term in speed-density) is used to estimate the volume of air entering the motor by multiplying how much air is sucked into the cylinder `each` stroke (usually displacement divide by two) by the number of engine revolutions. This provides the **V** term in the [Ideal Gas Law](/cars/rom/ideal-gas-law) calculation.
- The [Intake Air Temperature Sensor](/cars/sensors/intake-air-temperature-sensor) measures the temperature of air entering the engine, providing the **T** term in the [Ideal Gas Law](/cars/rom/ideal-gas-law) calculation.
- **R** is a constant
- Knowing **P**, **V**, **R** and **T**, the [ECU](/cars/ecu/ecu) can then calculate an estimate of **n** (moles of air entering motor) from sensor data and **n = PV / RT**

Because speed-density calculates airflow instead of directly measuring it, additional factors are often used to provide a better estimate. The [TPS Sensor](/cars/diagnostics/tps-sensor) is key in many of these - TPS tip-in enrichment is used to provide more fuel that the [Ideal Gas Law](/cars/rom/ideal-gas-law) calculation suggests in order to provide fueling for a rush of new air prior to the [Map Sensor](/cars/fueling/map-sensor) reaching a steady state. Off-throttle leaning is used to prevent the motor running rich after sudden decreases in throttle. Here are some links to more information about speed-density systems: - [http://web.archive.org/web/20081203203734/http://web.archive.org/web/20081203203734/http://www.asashop.org/autoinc/jan97/techtotech.htm](http://web.archive.org/web/20081203203734/http://web.archive.org/web/20081203203734/http://www.asashop.org/autoinc/jan97/techtotech.htm) - decent link, not TOO techy.
- [http://web.archive.org/web/20070205103708/http://www.wincom.net:80/trog/efi.html](http://web.archive.org/web/20070205103708/http://www.wincom.net:80/trog/efi.html) - quite technical but practically oriented
- [http://www.simcar.com/literature/sae940759/sae940759.htm](http://www.simcar.com/literature/sae940759/sae940759.htm) - **highly technical** paper on practical use of speed density systems for air/fuel management. Has **excellent** figures illustrating the role of secondary correction factors, like TPS accel/decel.
- [One](http://web.archive.org/web/20050304210413/http://baen.tamu.edu:80/users/lepori/Teaching/BSEN265/Lectures/Energy_Basics.ppt) [Two](http://web.archive.org/web/20040825011344/http://baen.tamu.edu:80/users/lepori/Teaching/BSEN265/Lectures/ICEng_Power_Eff. PPT) [Three](http://baen.tamu.edu/users/lepori/Teaching/BSEN265/Lectures/Revu_GasLaws.ppt) [Four](http://web.archive.org/web/20050913080557/http://baen.tamu.edu:80/users/lepori/Teaching/BSEN265/Lectures/Engine_cycles. PPT) [Five](http://web.archive.org/web/20050304211227/http://baen.tamu.edu:80/users/lepori/Teaching/BSEN265/Lectures/PowerTrans_notes.ppt) Microsoft Powerpoint presentations from a College Engineering class on gas laws, thermodynamics and engines.
