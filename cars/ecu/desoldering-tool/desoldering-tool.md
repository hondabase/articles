---
summary: 'Overview and comparison of manual desoldering tools including desoldering pumps, braids, and bulbs.'
tags: [hardware, education]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Desoldering Tool'
    url: /pgmfi/wiki/library/desoldering-tool
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Desoldering Tools for ECU Modification

When chipping or modifying an ECU, removing factory solder cleanly without damaging the delicate copper traces is critical. A standard [Soldering Iron](/cars/ecu/soldering-iron) is used to melt the solder, while a desoldering tool is used to remove it. 

Several styles of manual desoldering tools are commonly available:

## 1. Plunger-Style Desoldering Pumps (Solder Suckers)

These tools use a spring-loaded piston inside a cylinder to generate sudden vacuum suction when a release button is triggered.
* **How it works:** The spring is compressed manually, the Teflon tip is placed directly against the molten solder joint heated by the iron, and the release button is pressed to snap the plunger back, sucking the solder into the chamber.

* **Pros/Cons:** Standard plastic models can have inconsistent suction or suffer from recoil that might scratch traces if not held steadily. High-quality professional models (with silicone tips) offer much better performance.

## 2. Bulb-Style Desoldering Tools

A rubber bulb attached to a hollow tip allows manual suction generation.

* **How it works:** The bulb is squeezed before heating, the tip is placed on the molten solder, and the bulb is released to draw solder inside.

* **Pros/Cons:** They require manual pumping, which can be tiring. There is also a risk of accidentally squeezing the bulb *while

* over the joint, which blows hot solder back onto the PCB and can create short circuits.

## 3. Solder Wick / Braid

A fine copper braid coated with rosin flux that draws molten solder out of a joint via capillary action.

* **How it works:** Place the braid directly over the solder joint, press the hot soldering iron tip onto the braid, and watch the solder get absorbed into the copper weave.

* **Pros/Cons:** Excellent for cleaning flat surface-mount pads and clearing stubborn holes, but can sometimes stick to the board if the heat is removed too early. Refer to the [Desoldering Tips](/cars/ecu/desoldering-tips) guide for details on proper usage.
