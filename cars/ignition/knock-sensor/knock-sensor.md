---
summary: 'A piezo sensor that lets the ECU hear detonation and pull timing to protect the engine.'
tags: [knock, sensor, ignition]
applies_to:
  obd: [1, 2]
  engines: [B-Series, H-Series]
  models: [civic, crx, del-sol, integra, prelude]
  chassis: [bb, da, dc2, ef, eg, eg-eh, ek]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Knock Sensor'
    url: /pgmfi/wiki/library/knock-sensor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Knock Sensor

A knock sensor is a piezo "microphone" bolted to the engine block that listens for the
high-frequency rattle of pre-ignition (detonation). The ECU uses its signal to detect
knock and protect the engine.

## Where it is used

Knock sensors are fitted to DOHC VTEC engines such as the B16, B18C and H22, and to SOHC
VTEC OBD2 engines.

## How it works

The sensor feeds a dedicated knock-detection circuit (the "knock board") inside the ECU,
which watches for the engine's detonation frequency. When it hears knock, the ECU can
retard ignition timing to protect the engine.

## Limitations on boosted setups

The factory knock board is widely considered unreliable for detecting knock on
forced-induction engines. In practice it acts as a basic safeguard against bad fuel
rather than a precise knock-detection system, and it can report false positives on forged
internals.

> [!TIP]
> On a boosted build, the stock sensor is usually paired with a dedicated aftermarket knock-detection device (for example a J&S Safeguard) for accurate protection.

## Related

- [Knock sensor voltages](/cars/sensors/knock-sensor-voltages)
- [ECU trouble codes](/cars/diagnostics/ecu-trouble-codes)
