---
summary: 'An overview of engine compression ratios, defining the relationship between cylinder volume and the compression stroke.'
tags: [engine, theory, compression, tuning]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Engine Compression Ratio Fundamentals

Compression ratio is a fundamental engine specification that defines the ratio between the volume of the cylinder and combustion chamber when the piston is at bottom dead center (BDC) and the volume when the piston is at top dead center (TDC). This value dictates how much the air-fuel mixture is compressed during the compression stroke.

## Types of Compression Measurements

Engineers and tuners categorize compression into several distinct types to better understand engine behavior under different operating conditions:

*   **Static Compression Ratio (SCR):** The geometric ratio calculated based on the physical dimensions of the combustion chamber, cylinder bore, stroke, and piston dish/dome volume. It does not account for valve timing events.
*   **Dynamic Compression Ratio (DCR):** A more accurate representation of actual cylinder pressure that accounts for the intake valve closing point. Because the intake valve remains open for a portion of the compression stroke, the effective compression stroke is shorter than the physical stroke.
*   **Cylinder Pressure (Compression Test):** A measurement of the actual pressure generated within the cylinder during cranking, typically measured in PSI or bar. This is influenced by the compression ratio, camshaft profile, and the mechanical sealing integrity of the rings and valves.

> [!NOTE]
> Increasing the static compression ratio generally improves thermal efficiency and power output but significantly increases the risk of engine knock (detonation), requiring higher octane fuel or advanced ignition timing management.

## Calculation Variables

To calculate the compression ratio, the following physical volumes must be accounted for:

| Component | Description |
| :--- | :--- |
| **Cylinder Volume** | The swept volume of the piston moving from BDC to TDC. |
| **Combustion Chamber Volume** | The volume of the head cavity at TDC. |
| **Piston Dish/Dome Volume** | The volume added or subtracted by the piston crown shape. |
| **Head Gasket Volume** | The volume created by the compressed thickness of the head gasket. |
| **Deck Clearance** | The volume created by the distance between the piston crown and the block deck at TDC. |

> [!TIP]
> When modifying an engine for higher compression, always verify the deck height and combustion chamber volume through physical measurement (buretting) rather than relying solely on manufacturer specifications, as machining and wear can alter these values.
