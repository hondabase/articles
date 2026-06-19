---
summary: 'A practical overview of the parameters window in Hondata software, explaining which ECU settings it exposes and how it fits into the tuning workflow.'
tags: [tuning, software, calibration, ecu]
applies_to:
  models: [accord, civic, crx, del-sol, integra, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: Hondata Help
    title: Parameters Window
    url: https://www.hondata.com/help/smanager/parameters.htm
    license: 'All rights reserved'
    license_url: https://www.hondata.com/
    retrieved_at: '2026-06-19'
    used_for: reference
---

# Parameters Window Overview

The parameters window is the place where the software groups ECU settings into functional categories. It is less about one specific table and more about giving you a map of the editable tuning surface.

## What It Contains

The window can expose many kinds of ECU settings, including:

* Analog input parameters
* Boost control and boost parameters
* Closed-loop and wideband parameters
* Fuel compensation and injector settings
* Gear, idle, ignition, and launch control parameters
* MAP, nitrous, notes, and datalogging parameters
* Rev limits, security, shift light, traction control, TPS, and VTEC parameters

That list changes with vehicle definition and calibration package, but the idea stays the same: this is the software’s parameter index.

> [!NOTE]
> If you are searching for a setting and do not know which table it belongs to, the parameters window is usually the fastest way to find the right family of controls.

## Why It Matters

In a tuning workflow, parameters are the glue between raw tables and system behavior. They decide whether a feature is active, what sensor input it uses, and how aggressively it responds.

That makes the parameters window more than a UI convenience. It is the place where you verify that the ECU is looking at the right inputs before you start changing the maps themselves.

## 2D Graphs

The page also notes that parameter tables can be displayed as 2D graphs. That is useful when a parameter is easier to understand as a shape than as a grid of numbers.

## Practical Use

1. Use the window to locate the correct category before editing.
2. Confirm whether the ECU is using stock logic, a custom sensor input, or an alternate control path.
3. Adjust the supporting parameter family before revisiting the main calibration tables.
4. Use graph views when you need to understand how a parameter changes across its range.

> [!TIP]
> The parameters window is best treated as a navigation layer. It helps you reach the real tuning settings faster, but it does not replace checking the tables themselves.

