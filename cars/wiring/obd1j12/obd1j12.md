---
summary: "In its stock configuration, an OBD1 car has a diagnostic connector under the dash which is wired to the ECU's serial port."
tags: [hardware, education, ecu, tuning, rom, sensors, reference, wiring, conversion, diagnostics]
applies_to:
  obd: [1]
  models: [civic, del-sol]
  chassis: [eg, eg-eh]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: OBD1J12
    url: /pgmfi/wiki/library/obd1j12
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1J12

In its stock configuration, an [OBD1](/cars/wiring/obd1) car has a diagnostic connector under the dash which is wired to the [ECU](/cars/ecu/ecu)'s serial port. The [ECU](/cars/ecu/ecu)'s serial port is also wired to [CN2](/cars/wiring/obd1cn2). This diagnostic connector works in half-duplex, meaning there is only one wire which is used for receiving and transmitting by both the diagnostic tool and the [ECU](/cars/ecu/ecu), and thus only one device can transmit at once. `J12`, when removed, disconnects the receive line from the transmit line, so the serial port can work in full-duplex mode, meaning both devices can send to one another simultaneously through [CN2](/cars/wiring/obd1cn2). This, of course, breaks the stock diagnostic connector under the dash. However, the benefit of full-duplex mode is more reliable [Data Logging](/cars/diagnostics/data-logging). Some programming work is in progress to take advantage of this to log data at a much higher sample rate without clobbering any commands sent to the [ECU](/cars/ecu/ecu). On a [JDM](/cars/sensors/jdm) P30 (Small Sqaure) [ECU](/cars/ecu/ecu) it is the `J4`. picture of [OBD](/cars/wiring/obd)1 `J12`: (12/4/03 - Lego Z)
 ![j12.jpg](j12.jpg)
