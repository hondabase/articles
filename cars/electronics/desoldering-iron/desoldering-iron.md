---
summary: 'Guide to using and modifying budget-friendly bulb-style desoldering irons for ECU chipping and through-hole solder removal.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - hardware
  - education
sources:
  - name: 'pgmfi.org wiki'
    title: 'Desoldering Iron'
    url: /pgmfi/wiki/library/desoldering-iron
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Guide to Bulb-Style Desoldering Irons

A desoldering iron is a budget-friendly tool that combines a heated hollow tip with a manual vacuum mechanism—most commonly a rubber squeeze bulb. It serves as a middle ground between using a separate soldering iron and manual pump, and purchasing an expensive professional [desoldering station](/cars/electronics/desoldering-station).

---

## 1. Operating Instructions

To use a standard bulb-style desoldering iron:

1.  **Compress the Bulb:** Squeeze the rubber bulb completely before applying heat to the board.
2.  **Heat the Joint:** Place the hollow heated tip flat over the component pin. Wait 1–2 seconds for the solder to melt completely.
3.  **Release for Suction:** Release the rubber bulb to create vacuum suction. This draws the molten solder up through the tip and into the collection chamber.
4.  **Clear the Tip:** Squeeze the bulb over a heat-resistant tray to expel the waste solder before moving to the next pin.

> [!CAUTION]
> Squeezing the bulb while the iron is near the board is clumsy. If the tip slips, it can scratch the board mask or destroy copper traces. Always compress the bulb *before* touching the pin.

---

## 2. The DIY Vacuum Cleaner Mod

Using the manual squeeze bulb can be frustrating, as the suction is brief and often fails to clear the through-hole completely on the first try. A common hobbyist modification converts the manual iron into a continuous-vacuum tool:

1.  Remove the rubber squeeze bulb from the metal suction tube of the iron.
2.  Connect a flexible high-temperature silicone hose to the iron's metal tube.
3.  Attach the other end of the hose to a standard household vacuum cleaner pipe using tape and a rubber reducer.
4.  Turning on the vacuum cleaner provides continuous, high-volume suction. When the heated tip melts the solder, the vacuum instantly clears the entire through-hole.

### Drawbacks of the Vacuum Mod:
*   **Rapid Tip Cooling:** The high volume of air drawn through the tip cools the heating element quickly. You must use a higher-wattage iron (at least 45W) to prevent the tip from freezing to the board.
*   **Acoustic Noise:** Running a household vacuum during a long desoldering session is loud.
*   **Thermal Shock:** Pulling large volumes of room-temperature air across the hot PCB pad can warp the board or lift pads if the tip is held in place too long.

---

## 3. Alternative Budget Tools
If a desoldering station is out of your budget and the bulb iron is too clumsy, consider using a high-quality manual solder pump (such as the **Engineer SS-02**, which features a flexible silicone tip that seals against the joint) in combination with a standard soldering iron.
