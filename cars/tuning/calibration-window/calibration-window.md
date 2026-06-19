---
summary: 'How the calibration window is organized in Hondata tuning software, including parameter groups, change indicators, right-click table actions, and graph views.'
tags: [tuning, software, calibration, ecu]
applies_to:
  models: [accord, civic, crx, del-sol, integra, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: Hondata Help
    title: Calibration Window
    url: https://www.hondata.com/help/flashpro/calibration_window.htm
    license: 'All rights reserved'
    license_url: https://www.hondata.com/
    retrieved_at: '2026-06-19'
    used_for: reference
---

# Calibration Window Overview

The calibration window is the part of the tuning software where the ECU’s editable tables live. It is the main place you change fuel, ignition, idle, sensor, and protection behavior before writing the calibration back to the ECU.

## What It Contains

The calibration window is organized into related groups rather than a single flat sheet. Typical groups include:

* Calibration parameters
* Fuel parameters
* Ignition parameters
* VTEC and VTC parameters
* Closed-loop parameters
* Knock control parameters
* Rev limit parameters
* Idle parameters
* Sensor parameters
* Miscellaneous parameters
* Traction control parameters

That layout matters because it tells you where a given change belongs. Fuel corrections should not be buried in ignition settings, and sensor setup should not be mixed with the base fuel map.

> [!NOTE]
> Different vehicles and calibration types expose different groups. A calibration editor is not a fixed template; it adapts to the ECU definition behind it.

## Change Indicators

The editor uses visual markers to show whether a parameter has been touched:

| Indicator | Meaning |
| :--- | :--- |
| No marker | Factory default value |
| Red dot | Changed in the current editing session |
| Yellow dot | Changed in a previous editing session |

That is a simple but important safety check. It lets you see whether a value is still stock, freshly edited, or already carried forward from an earlier revision.

## Table Editing

Right-clicking a calibration table opens the editing actions for the selected cells. The useful actions are:

* Increase selection
* Decrease selection
* Adjust
* Revert to last save
* Reset to default
* Import from calibration

Those controls make it easier to do controlled table edits instead of replacing values manually cell by cell.

> [!IMPORTANT]
> Revert and reset do different jobs. Revert returns the table to the last saved state, while reset restores the vehicle default.

## 2D Graph View

Tables can also be displayed as 2D graphs. That is useful for spotting shape problems, abrupt transitions, or cells that do not follow the surrounding pattern.

## Practical Use

Use the calibration window in this order:

1. Identify the parameter group you need.
2. Check whether the current value is stock, newly changed, or previously changed.
3. Edit the table with small steps.
4. Revisit the graph view to confirm the shape still makes sense.
5. Save only after the correction is coherent across the full table.

> [!TIP]
> When a table looks wrong on the graph but the numbers seem plausible, the graph usually makes the problem easier to see than the grid.
