yaml
---
summary: Adjust throttle position sensor (TPS) output voltage by rotating the sensor housing and securing with rivets or screws. Simple procedure suitable for OBD0, OBD1, and OBD2 systems.
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - throttle position sensor
  - TPS
  - sensor adjustment
  - voltage calibration
  - tuning
---

# Throttle Position Sensor (TPS) Adjustment

## Overview

The throttle position sensor output voltage can be adjusted by rotating the sensor housing relative to its mounting bracket. This procedure allows you to calibrate the TPS to output the correct voltage at idle and wide-open throttle (WOT).

## Required Tools

- Dremel or rotary tool with cutting disc
- Slot-head screwdriver
- Multimeter with test probes
- Replacement rivets or fastening hardware (optional)

## Adjustment Procedure

### Step 1: Create Adjustment Slots

Use a Dremel or rotary tool to cut a small slot across each rivet head. This allows you to apply torque for loosening without damaging the rivet.

> [!NOTE]
> Make shallow cuts only. The goal is to create enough purchase for a screwdriver, not to remove the rivet entirely.

### Step 2: Loosen the TPS Housing

Use a slot-head screwdriver in the cuts you created to slightly loosen (but not remove) the rivets or fasteners securing the TPS to its bracket.

### Step 3: Rotate and Measure

- Carefully rotate the TPS housing left or right to adjust the internal wiper position.
- Connect your multimeter probes to the center terminal (wiper) and one outer terminal.
- Rotate the sensor gradually while monitoring the voltage output.

### Step 4: Set Voltage Targets

Adjust the TPS position until you achieve:

| Condition | Target Voltage |
|-----------|-----------------|
| Idle (closed throttle) | 0.5 V |
| WOT (wide-open throttle) | 4.5 V |

> [!IMPORTANT]
> Use consistent probe placement. Typically, you will measure between the wiper (center) and one of the outer terminals. Verify against your ECU's expected range if available.

### Step 5: Secure the Adjustment

Once the correct position is found, re-tighten the fasteners. You may either:
- Re-secure the original rivets
- Replace with new fasteners (M3 socket head cap screws are ideal for accessibility in tight engine bay spaces)

> [!TIP]
> Socket head cap screws offer superior adjustability compared to rivets and are easier to remove if future adjustments are needed.

## Verification

After securing, confirm that throttle movement still produces the full voltage range (0.5 V to 4.5 V). If adjustment has shifted, loosen and repeat Step 3.

## See Also

- [Throttle Position Sensor Diagnostics](/cars/diagnostics/tps-sensor)
- [Wide-Open Throttle (WOT)](/cars/reference/wot)