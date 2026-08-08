---
summary: 'Design a coil-on-plug conversion for Honda H- and F-series engines covering triggers, coil drivers, dwell, and validation.'
tags: [coil-on-plug, h-series, f-series, ignition, microcontroller]
applies_to:
  models: [accord, prelude]
  engines: [f20, f22, f23, h22, h23]
complexity: advanced
sources:
  - name: Icelord
    title: 'CoilOnPlug for H- and F-series engines'
    url: 'https://home.icelord.net/wordpress/?p=16940'
    license: 'All rights reserved'
    license_url: 'https://home.icelord.net/wordpress/?p=16940'
    adapted: true
  - name: Icelord
    title: 'Coil-on-plug development part 16941'
    url: 'https://home.icelord.net/wordpress/?p=16941'
    license: 'All rights reserved'
    license_url: 'https://home.icelord.net/wordpress/?p=16941'
    adapted: true
  - name: Icelord
    title: 'Coil-on-plug development part 16942'
    url: 'https://home.icelord.net/wordpress/?p=16942'
    license: 'All rights reserved'
    license_url: 'https://home.icelord.net/wordpress/?p=16942'
    adapted: true
  - name: Icelord
    title: 'Coil-on-plug development part 16950'
    url: 'https://home.icelord.net/wordpress/?p=16950'
    license: 'All rights reserved'
    license_url: 'https://home.icelord.net/wordpress/?p=16950'
    adapted: true
  - name: Icelord
    title: 'Coil-on-plug development part 16951'
    url: 'https://home.icelord.net/wordpress/?p=16951'
    license: 'All rights reserved'
    license_url: 'https://home.icelord.net/wordpress/?p=16951'
    adapted: true
  - name: Icelord
    title: 'Coil-on-plug development part 16952'
    url: 'https://home.icelord.net/wordpress/?p=16952'
    license: 'All rights reserved'
    license_url: 'https://home.icelord.net/wordpress/?p=16952'
    adapted: true
  - name: Icelord
    title: 'Coil-on-plug development part 16980'
    url: 'https://home.icelord.net/wordpress/?p=16980'
    license: 'All rights reserved'
    license_url: 'https://home.icelord.net/wordpress/?p=16980'
    adapted: true
  - name: Icelord
    title: 'Coil-on-plug development part 16989'
    url: 'https://home.icelord.net/wordpress/?p=16989'
    license: 'All rights reserved'
    license_url: 'https://home.icelord.net/wordpress/?p=16989'
    adapted: true
  - name: Icelord
    title: 'Coil-on-plug development part 16991'
    url: 'https://home.icelord.net/wordpress/?p=16991'
    license: 'All rights reserved'
    license_url: 'https://home.icelord.net/wordpress/?p=16991'
    adapted: true
  - name: Icelord
    title: 'Coil-on-plug development part 17013'
    url: 'https://home.icelord.net/wordpress/?p=17013'
    license: 'All rights reserved'
    license_url: 'https://home.icelord.net/wordpress/?p=17013'
    adapted: true
  - name: Icelord
    title: 'Coil-on-plug development part 17015'
    url: 'https://home.icelord.net/wordpress/?p=17015'
    license: 'All rights reserved'
    license_url: 'https://home.icelord.net/wordpress/?p=17015'
    adapted: true
  - name: Icelord
    title: 'Coil-on-plug development part 17041'
    url: 'https://home.icelord.net/wordpress/?p=17041'
    license: 'All rights reserved'
    license_url: 'https://home.icelord.net/wordpress/?p=17041'
    adapted: true
  - name: Icelord
    title: 'Coil-on-plug development part 17051'
    url: 'https://home.icelord.net/wordpress/?p=17051'
    license: 'All rights reserved'
    license_url: 'https://home.icelord.net/wordpress/?p=17051'
    adapted: true
  - name: Icelord
    title: 'Coil-on-plug development part 17204'
    url: 'https://home.icelord.net/wordpress/?p=17204'
    license: 'All rights reserved'
    license_url: 'https://home.icelord.net/wordpress/?p=17204'
    adapted: true
---

# Distributorless Coil-on-Plug Conversion for Honda H- and F-Series Engines

A coil-on-plug (COP) conversion removes the distributor cap and rotor high-voltage path on H- and F-series engines. It is a custom ignition system: firing order, dwell, and sync must be engineered, not guessed.

```carousel
![H f series coil on plug conversion image 12b8cees 960](swm-001-001-h-f-series-coil-on-plug-conversion-image-12b.jpg)
<!-- slide -->
![H f series coil on plug conversion image d8472ees 960](swm-002-001-h-f-series-coil-on-plug-conversion-image-d84.jpg)
<!-- slide -->
![H f series coil on plug conversion image eb172ees 960](swm-003-002-h-f-series-coil-on-plug-conversion-image-eb1.jpg)
<!-- slide -->
![H f series coil on plug conversion image d9c13ees 960](swm-004-001-h-f-series-coil-on-plug-conversion-image-d9c.jpg)
<!-- slide -->
![H f series coil on plug conversion image 85c13ees 960](swm-005-002-h-f-series-coil-on-plug-conversion-image-85c.jpg)
<!-- slide -->
![H f series coil on plug conversion image 9df2c81s 960](swm-006-001-h-f-series-coil-on-plug-conversion-image-9df.jpg)
<!-- slide -->
![H f series coil on plug conversion image a3f2c81s 960](swm-007-002-h-f-series-coil-on-plug-conversion-image-a3f.jpg)
<!-- slide -->
![H f series coil on plug conversion image 8c3ff41s 960](swm-008-001-h-f-series-coil-on-plug-conversion-image-8c3.jpg)

```

```carousel
![H f series coil on plug conversion image 9c3ff41s 960](swm-009-002-h-f-series-coil-on-plug-conversion-image-9c3.jpg)
<!-- slide -->
![H f series coil on plug conversion image db354c1s 960](swm-010-001-h-f-series-coil-on-plug-conversion-image-db3.jpg)
<!-- slide -->
![H f series coil on plug conversion image fb354c1s 960](swm-011-002-h-f-series-coil-on-plug-conversion-image-fb3.jpg)
<!-- slide -->
![H f series coil on plug conversion image 57354c1s 960](swm-012-003-h-f-series-coil-on-plug-conversion-image-573.jpg)
<!-- slide -->
![H f series coil on plug conversion image 6871ac1s 960](swm-013-004-h-f-series-coil-on-plug-conversion-image-687.jpg)
<!-- slide -->
![H f series coil on plug conversion image 7315999s 960](swm-014-001-h-f-series-coil-on-plug-conversion-image-731.jpg)
<!-- slide -->
![H f series coil on plug conversion image 3274cb9s 960](swm-015-001-h-f-series-coil-on-plug-conversion-image-327.jpg)
<!-- slide -->
![H f series coil on plug conversion image a474cb9s 960](swm-016-002-h-f-series-coil-on-plug-conversion-image-a47.jpg)

```

```carousel
![H f series coil on plug conversion image 7474cb9s 960](swm-017-003-h-f-series-coil-on-plug-conversion-image-747.jpg)
<!-- slide -->
![H f series coil on plug conversion image 5c74cb9s 960](swm-018-004-h-f-series-coil-on-plug-conversion-image-5c7.jpg)
<!-- slide -->
![H f series coil on plug conversion image c274cb9s 960](swm-019-005-h-f-series-coil-on-plug-conversion-image-c27.jpg)
<!-- slide -->
![H f series coil on plug conversion image 6274cb9s 960](swm-020-006-h-f-series-coil-on-plug-conversion-image-627.jpg)
<!-- slide -->
![1g1b9s 960](swm-021-001-1g1b9s-960.jpg)
<!-- slide -->
![H f series coil on plug conversion image 2678215s 960](swm-022-001-h-f-series-coil-on-plug-conversion-image-267.jpg)
<!-- slide -->
![H f series coil on plug conversion image d338215s 960](swm-023-002-h-f-series-coil-on-plug-conversion-image-d33.jpg)
<!-- slide -->
![H f series coil on plug conversion image 2678215s 1920](swm-024-003-h-f-series-coil-on-plug-conversion-image-267.jpg)

```

```carousel
![H f series coil on plug conversion image d338215s 1920](swm-025-004-h-f-series-coil-on-plug-conversion-image-d33.jpg)
<!-- slide -->
![H f series coil on plug conversion image f630895s 960](swm-026-001-h-f-series-coil-on-plug-conversion-image-f63.jpg)
<!-- slide -->
![H f series coil on plug conversion image ee30895s 960](swm-027-002-h-f-series-coil-on-plug-conversion-image-ee3.jpg)
<!-- slide -->
![H f series coil on plug conversion image c930895s 960](swm-028-003-h-f-series-coil-on-plug-conversion-image-c93.jpg)
<!-- slide -->
![H f series coil on plug conversion image d3dad6ds 960](swm-029-001-h-f-series-coil-on-plug-conversion-image-d3d.jpg)
<!-- slide -->
![H f series coil on plug conversion image d34ed6ds 960](swm-030-002-h-f-series-coil-on-plug-conversion-image-d34.jpg)
<!-- slide -->
![H f series coil on plug conversion image d3dad6ds 1920](swm-031-003-h-f-series-coil-on-plug-conversion-image-d3d.jpg)
<!-- slide -->
![H f series coil on plug conversion image d34ed6ds 1920](swm-032-004-h-f-series-coil-on-plug-conversion-image-d34.jpg)

```

```carousel
![6f8ea804la4 960](swm-033-001-6f8ea804la4-960.jpg)
<!-- slide -->
![6f8ea804k407 960](swm-034-002-6f8ea804k407-960.jpg)
<!-- slide -->
![6f8ea804la4 1920](swm-035-003-6f8ea804la4-1920.jpg)
<!-- slide -->
![6f8ea804k407 1920](swm-036-004-6f8ea804k407-1920.jpg)
<!-- slide -->
![H f series coil on plug conversion image fhiuivok89nyxybusimypits](swm-037-001-h-f-series-coil-on-plug-conversion-image-fhi.jpg)
<!-- slide -->
![H f series coil on plug conversion image 5 tppvep5sahdyv4r4iwyypf](swm-038-002-h-f-series-coil-on-plug-conversion-image-5-t.jpg)
<!-- slide -->
![H f series coil on plug conversion image chuj4dvurwyq020y34lad9q5](swm-039-003-h-f-series-coil-on-plug-conversion-image-chu.jpg)
<!-- slide -->
![H f series coil on plug conversion image 1rfa1qi cmabrsabsntzgc50](swm-040-004-h-f-series-coil-on-plug-conversion-image-1rf.jpg)

```

```carousel
![H f series coil on plug conversion image fhiuivok89nyxybusimypits](swm-041-005-h-f-series-coil-on-plug-conversion-image-fhi.jpg)
<!-- slide -->
![H f series coil on plug conversion image 5 tppvep5sahdyv4r4iwyypf](swm-042-006-h-f-series-coil-on-plug-conversion-image-5-t.jpg)
<!-- slide -->
![H f series coil on plug conversion image chuj4dvurwyq020y34lad9q5](swm-043-007-h-f-series-coil-on-plug-conversion-image-chu.jpg)
<!-- slide -->
![H f series coil on plug conversion image 1rfa1qi cmabrsabsntzgc50](swm-044-008-h-f-series-coil-on-plug-conversion-image-1rf.jpg)

```

## Goals

- Stable spark energy at high RPM / high cylinder pressure
- Fewer moisture-related misfires
- Cleaner packaging than long plug wires near headers

## Architecture

| Piece | Notes |
| :--- | :--- |
| Trigger | Stock distributor pickups or dedicated crank/cam sensors |
| Control | Standalone ECU ignition channels or an intermediate COP controller |
| Coils | Logic coils vs dumb coils + igniters - match the driver |
| Power | Relay-fed coil B+ with correct fuse and grounds |
| Mechanical | Brackets clearing the valve cover, intake, and chassis |

## Design Rules

1. Map outputs to firing order **1-3-4-2** explicitly.
2. Set dwell to the coil manufacturer’s guidance; over-dwell cooks coils.
3. Keep crank/cam signals away from coil primary wiring.
4. Preserve tach or cam-sync functions you remove with the distributor.
5. Strain-relieve every branch; ignition heat and vibration break weak crimps.

## Validation

- [ ] Timing light or scope confirms correct sync
- [ ] No sustained misfire under load
- [ ] Coils and drivers remain within temperature limits after a heat soak
- [ ] No chafing after full steering/engine movement

> [!WARNING]
> Ignition voltages are dangerous. Incorrect timing under load can destroy pistons. If the OEM distributor system is healthy and the engine is stock, repair it before converting.

## When COP Makes Sense

Motorsport, boost, repeated cap/rotor failures, or packaging constraints - not appearance alone.
