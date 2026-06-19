---
summary: 'Practical tips, tricks, and best practices for desoldering components from delicate ECU circuit boards.'
tags: [hardware, education]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Desoldering Tips'
    url: /pgmfi/wiki/library/desoldering-tips
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Desoldering Tips & Best Practices

Desoldering components from multi-layer ECU circuit boards requires precision to prevent lifting copper pads or destroying through-hole plating. Below are essential tips and techniques to achieve clean results.

## 1. Wait for Complete Solder Liquefaction

Patience is the most critical factor. 
* **The Mistake:** Applying suction the moment the top layer of solder appears soft.

* **The Correct Way:** Wait a few seconds for the heat to transfer all the way through the PCB hole to the opposite side of the board. The solder must be completely molten throughout the entire depth of the barrel before you apply suction. Otherwise, you will leave a plug of solder trapped midway, forcing you to re-solder and try again.

## 2. Managing Thermal Mass (Ground Pins)

The amount of heat required is directly proportional to the size of the copper traces connected to the pin.

* Pins connected to standard signal traces melt quickly.
* Pins connected to the main ground planes (such as Pin 15 on many standard ICs) act as massive heat sinks. They draw heat away from your iron tip rapidly. You will need to hold the iron tip on these pins slightly longer, or use a slightly wider tip, to get the solder to melt fully.

## 3. The "Rocking" Technique

When dealing with stubborn components, gently rock the pin back and forth with your iron tip or a pair of needle-nose pliers at a slow rhythm (about once per second). This helps break the mechanical bond between the pin and the inner walls of the plated through-hole as the solder cools.

## 4. Proper Use of Solder Braid (Wick)

Solder braid is highly effective for clean-up:

* Place clean braid directly over the joint.
* Apply the flat face of your iron tip onto the braid, pressing it into the joint.

* Once you see the braid absorb the solder (it will change color to silver), lift the braid and iron together. 
* **Caution:** Never pull the braid off the board while the solder is cold, or you may tear the copper pad off the board.
