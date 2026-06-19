---
summary: 'How Hondata MAP sensor parameters work, including sensor selection, scalar and offset values, boost limits, and safe sensor replacement.'
tags: [tuning, map-sensor, boost, sensors, calibration]
applies_to:
  models: [accord, civic, crx, del-sol, integra, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: advanced
sources:
  - name: Hondata Help
    title: MAP Parameters
    url: https://www.hondata.com/help/smanager/mapparameters.htm
    license: 'All rights reserved'
    license_url: https://www.hondata.com/
    retrieved_at: '2026-06-19'
    used_for: reference
---

# MAP Sensor Parameters

MAP sensor setup controls how the ECU interprets manifold pressure, which is central to load calculation, fueling, ignition, and boost protection. If the sensor scaling is wrong, the rest of the calibration sits on a bad foundation.

## What The Page Controls

The MAP parameters page typically covers four things:

* Which MAP sensor is selected
* The voltage-to-pressure scalar
* The pressure offset
* The resulting full-scale and atmospheric values

That is the entire chain from raw sensor voltage to the pressure value the ECU uses in its maps.

> [!WARNING]
> If the sensor upper limit is exceeded, the ECU can misread load and fuel the engine lean. If the boost limit is set beyond the sensor range, boost cut may not activate when you expect it to.

## Sensor Selection

The software normally lets you choose the stock MAP sensor or an alternate 5V linear sensor. When the stock sensor is selected, the ECU uses its built-in conversion and no custom scaling is needed.

If you fit a replacement sensor, you need an accurate conversion. Do not guess the values just because a sensor is "3 bar" or "4 bar."

## Scalar And Offset

MAP sensor output is treated as a linear voltage-to-pressure equation.

* Scalar defines the slope of the conversion.
* Offset defines the intercept.

Those two values determine how the ECU translates a voltage into manifold pressure. If you do not know them from the sensor documentation or measurement, stop and get them rather than inventing a pair of numbers.

> [!IMPORTANT]
> A wrong MAP conversion does not just change boost readout. It shifts the load value that drives fuel and ignition tables.

## Boost Limit

The boost limit is the pressure threshold where the ECU should react to excess manifold pressure. It must stay below the reliable operating ceiling of the sensor itself.

The practical rule is to leave margin between:

* the sensor’s full-scale range
* the ECU’s real 5V supply behavior
* the boost cut threshold you want to enforce

That margin matters because a sensor rarely reaches a mathematically perfect maximum at the exact pressure printed on the box.

## Practical Setup

1. Confirm the sensor type before changing the calibration.
2. Use the stock conversion only when the stock sensor is actually installed.
3. Enter scalar and offset from documented sensor data or measurement.
4. Keep the boost limit comfortably below the sensor’s absolute ceiling.
5. Verify atmospheric reading key-on-engine-off so the ECU is interpreting the sensor in a believable range.

> [!TIP]
> When MAP scaling is wrong, the error usually shows up everywhere at once: idle load, boost load, fuel correction, and protection. That makes MAP setup one of the first things worth checking in any new calibration.
