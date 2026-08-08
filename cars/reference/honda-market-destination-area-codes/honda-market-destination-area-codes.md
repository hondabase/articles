---
summary: 'Decode Honda vehicle destination (area) codes such as KA, KL, and KG used for market, steering, and speedometer identification.'
tags: [market-code, area-code, vehicle-identification, reference]
applies_to:
  models: [accord, civic, crx, del-sol, integra, prelude]
complexity: beginner
sources:
  - name: Icelord
    title: 'Honda area codes'
    url: 'https://icelord.net/honda/area/'
    license: 'All rights reserved'
    license_url: 'https://icelord.net/honda/area/'
    adapted: true
---

# Honda Market Destination Area Codes

Honda and Acura vehicles carry a short **destination / area code** that identifies the intended market. The code drives steering hand, speedometer units, lighting, emissions packages, and which parts catalogs apply.

*Image placeholder - replace with a publication-cleared photo.*

## Where to Find the Code

Common locations (vary by era and model):

- Certification / tire placard in the door jamb
- Body data plate or firewall tag
- Build plate in the engine bay
- Sometimes encoded in documentation or options lists

Treat the physical plate on the vehicle as authoritative when catalogs disagree.

## How to Read the Table

| Field | Meaning |
| :--- | :--- |
| **Area code** | Two-letter market destination |
| **Market / region** | Intended sales region or country group |
| **Steering** | LHD or RHD |
| **Speedometer** | Miles (M) or kilometers (Km) |

## Common Destination Codes

| Code | Market / notes | Steering | Speedo |
| :--- | :--- | :--- | :--- |
| **KA** | USA | LHD | M |
| **KB** | Belgium, Netherlands, Luxembourg | LHD | Km |
| **KC** | Canada | LHD | Km |
| **KD** | Other countries (examples historically include Panama, Bahamas, Liberia; older notes mention Okinawa for 1968) | LHD | M |
| **KE** | England, Ireland | RHD | M |
| **KF** | France (also associated with Italy/Portugal in some lists; older assignments differ) | LHD | Km |
| **KG** | Germany (historical Swiss assignment in early lists) | LHD | Km |
| **KH** | China / South America (and related destinations depending on era) | LHD | varies |
| **KJ** | Common JDM / Japan destination marker on many lists | RHD | Km |
| **KK** | Various export assignments by era | varies | varies |
| **KL** | Often Australia / New Zealand on enthusiast lists - **verify on the vehicle plate** | RHD | Km |
| **KQ** / **KR** / others | Additional export splits appear on later models | varies | varies |

> [!NOTE]
> Letter assignments have been reallocated across decades. Always confirm against the plate on the car and a period-correct parts catalog. Do not assume a code from a forum list without checking the vehicle.

## Why the Code Matters

- **Steering racks and column switches** differ LHD vs RHD
- **Clusters and gearing** differ miles vs kilometers
- **Lighting and reflectors** follow regional rules
- **ECU/emissions** packages track market, not only chassis code
- **Parts supersession** (mirrors, harnesses, bumpers) often keys off destination

## Identification Workflow

1. Read the destination code from the vehicle plate.
2. Note chassis code, engine code, and transmission.
3. Cross-check the parts catalog for that destination.
4. When importing or swapping, list every system that is market-specific (cluster, harness, ECU, lighting, evaporative system).

## Related Identification

Pair destination codes with:

- Chassis codes (EG, EK, BB, etc.)
- Engine stamps and head castings
- ECU part numbers (for example 37820-xxx-xxx)

Destination alone does not define the engine or ECU, but it narrows the correct catalog branch.
