---
summary: 'OBD1 Civic Integra ECUs are a common hardware platform. What this means is that you can (with minor modifications) run essentially any code on any ECU in the family.'
applies_to:
  obd: [1]
  brand: Acura/Honda
complexity: advanced
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - wiring
  - conversion
  - diagnostics
---

# OBD1 Code Compatibility

[OBD1 Civic Integra](/cars/electronics/obd1-civic-integra) [ECU](/cars/electronics/ecu)s are a common hardware platform. What this means is that you can (with minor modifications) run essentially any code on any [ECU](/cars/electronics/ecu) in the family. There are rules however: - [VTEC](/cars/electronics/vtec) programs ([P28](/cars/electronics/p28), [P30](/cars/electronics/p30), [P72](/cars/electronics/p72), ...) require a [VTEC](/cars/electronics/vtec) [ECU](/cars/electronics/ecu) or a [Non Vtec-To-Vtec](/cars/electronics/non-vtec-to-vtec) conversion.
- Non-[VTEC](/cars/electronics/vtec) programs run in a [VTEC](/cars/electronics/vtec) [ECU](/cars/electronics/ecu) without any problems.
- [VTEC](/cars/electronics/vtec) programs run in non-Vtec [ECU](/cars/electronics/ecu)s with VTEC disabled. (DB: they may even work with VTEC xover above redline although I think the sensor checks for VTP/VTS will cause issues.)
- 1-wire O2 [ECU](/cars/electronics/ecu)s like [P05](/cars/electronics/p05), [P08](/cars/electronics/p08) require ***either*** [One Wire To4 Wire O2 Sensor](/cars/electronics/one-wire-to4-wire-o2-sensor) conversion of the hardware ***or*** to disable the [O2 Heater Circuit](/cars/electronics/o2-heater-circuit) in the [ROM](/cars/electronics/rom).
- [DOHC](/cars/electronics/dohc) [VTEC](/cars/electronics/vtec) programs ([P30](/cars/electronics/p30), [P72](/cars/electronics/p72), ...) generally have a [Knock Sensor](/cars/electronics/knock-sensor) enabled. To use these programs on [ECU](/cars/electronics/ecu)s lacking the [Knock Board](/cars/electronics/knock-board) ([P28](/cars/electronics/p28), [P08](/cars/electronics/p08), conversions, ...) you must first disable the [Knock Sensor](/cars/electronics/knock-sensor).

For information on disabling [Knock Sensor](/cars/electronics/knock-sensor) or the [O2 Heater Circuit](/cars/electronics/o2-heater-circuit) in software, please consult the [Rom Maps](/cars/electronics/rom-maps) for the code you are working with. Additionally, different markets received different features in their [ECU](/cars/electronics/ecu)s. - [USDM](/cars/electronics/usdm) [ECU](/cars/electronics/ecu)s are by far the most full-featured. Almost any code will run in a [USDM](/cars/electronics/usdm) [ECU](/cars/electronics/ecu) if the above rules are followed.
- [JDM](/cars/electronics/jdm) [ECU](/cars/electronics/ecu)s generally lack several things that must either be physically added to the [ECU](/cars/electronics/ecu) or disabled in the [ROM](/cars/electronics/rom). The [Pressure Atmosphere](/cars/electronics/pressure-atmosphere) (PA) sensor [Electrical Load Detector](/cars/electronics/electrical-load-detector) (ELD) and [Injector Test Circuit](/cars/electronics/injector-test-circuit) are the most notable things here.
- [EDM](/cars/electronics/edm) [ECU](/cars/electronics/ecu)s are generally the most bare. They generally lack PA, ELD, Injector test like the [JDM](/cars/electronics/jdm) [ECU](/cars/electronics/ecu)s, and will occaisonally lack the [Knock Sensor](/cars/electronics/knock-sensor) and knock board present in [JDM](/cars/electronics/jdm) [ECU](/cars/electronics/ecu)s too.
