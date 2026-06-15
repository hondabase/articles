---
summary: 'OBD1 Civic Integra ECUs are a common hardware platform. What this means is that you can (with minor modifications) run essentially any code on any ECU in the family.'
tags: [ecu, reference, tuning, rom, sensors, wiring, conversion, diagnostics]
applies_to:
  obd: [1]
  brand: Acura/Honda
  models: [civic, del-sol, integra]
  chassis: [dc2, eg, eg-eh]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1 Code Compatibility'
    url: /pgmfi/wiki/library/obd1-code-compatibility
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1 Code Compatibility

[OBD1 Civic Integra](/cars/sensors/obd1-civic-integra) [ECU](/cars/ecu/ecu)s are a common hardware platform. What this means is that you can (with minor modifications) run essentially any code on any [ECU](/cars/ecu/ecu) in the family. There are rules however: - [VTEC](/cars/sensors/vtec) programs ([P28](/cars/sensors/p28), [P30](/cars/sensors/p30), [P72](/cars/sensors/p72), ...) require a [VTEC](/cars/sensors/vtec) [ECU](/cars/ecu/ecu) or a [Non Vtec-To-Vtec](/cars/wiring/non-vtec-to-vtec) conversion.
- Non-[VTEC](/cars/sensors/vtec) programs run in a [VTEC](/cars/sensors/vtec) [ECU](/cars/ecu/ecu) without any problems.
- [VTEC](/cars/sensors/vtec) programs run in non-Vtec [ECU](/cars/ecu/ecu)s with VTEC disabled. (DB: they may even work with VTEC xover above redline although I think the sensor checks for VTP/VTS will cause issues.)
- 1-wire O2 [ECU](/cars/ecu/ecu)s like [P05](/cars/wiring/p05), [P08](/cars/wiring/p08) require ***either*** [One Wire To4 Wire O2 Sensor](/cars/wiring/one-wire-to4-wire-o2-sensor) conversion of the hardware ***or*** to disable the [O2 Heater Circuit](/cars/wiring/o2-heater-circuit) in the [ROM](/cars/rom/rom).
- [DOHC](/cars/sensors/dohc) [VTEC](/cars/sensors/vtec) programs ([P30](/cars/sensors/p30), [P72](/cars/sensors/p72), ...) generally have a [Knock Sensor](/cars/ignition/knock-sensor) enabled. To use these programs on [ECU](/cars/ecu/ecu)s lacking the [Knock Board](/cars/sensors/knock-board) ([P28](/cars/sensors/p28), [P08](/cars/wiring/p08), conversions, ...) you must first disable the [Knock Sensor](/cars/ignition/knock-sensor).

For information on disabling [Knock Sensor](/cars/ignition/knock-sensor) or the [O2 Heater Circuit](/cars/wiring/o2-heater-circuit) in software, please consult the [Rom Maps](/cars/wiring/rom-maps) for the code you are working with. Additionally, different markets received different features in their [ECU](/cars/ecu/ecu)s. - [USDM](/cars/sensors/usdm) [ECU](/cars/ecu/ecu)s are by far the most full-featured. Almost any code will run in a [USDM](/cars/sensors/usdm) [ECU](/cars/ecu/ecu) if the above rules are followed.
- [JDM](/cars/sensors/jdm) [ECU](/cars/ecu/ecu)s generally lack several things that must either be physically added to the [ECU](/cars/ecu/ecu) or disabled in the [ROM](/cars/rom/rom). The [Pressure Atmosphere](/cars/rom/pressure-atmosphere) (PA) sensor [Electrical Load Detector](/cars/sensors/electrical-load-detector) (ELD) and [Injector Test Circuit](/cars/diagnostics/injector-test-circuit) are the most notable things here.
- [EDM](/cars/wiring/edm) [ECU](/cars/ecu/ecu)s are generally the most bare. They generally lack PA, ELD, Injector test like the [JDM](/cars/sensors/jdm) [ECU](/cars/ecu/ecu)s, and will occaisonally lack the [Knock Sensor](/cars/ignition/knock-sensor) and knock board present in [JDM](/cars/sensors/jdm) [ECU](/cars/ecu/ecu)s too.
