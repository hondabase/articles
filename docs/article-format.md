# Hondabase Article Format and Style

How articles on hondabase.com are written and structured. Aimed at a Honda owner or DIY
mechanic, often on a phone in the garage. Write for that reader: clear, scannable,
accurate. Adapt legacy/wiki content to this format rather than preserving its quirks.

## 1. Where an article lives

```
<type>/<category>/<slug>/<slug>.md      + co-located image assets
```

- **type**: `cars`, `motorcycles`, `aircraft`, or `common`.
- **category**: a folder from the list in [README.md](../README.md). The folder IS the
  category; never put the category in frontmatter.
- **slug**: lowercase-kebab. The Markdown file matches the folder name. Images sit beside it.

## 2. Frontmatter (optional, additive)

Articles need no frontmatter; the title falls back to the first `# H1` and the category
to the folder. Add frontmatter only to enrich search, filtering, and the explorer:

```yaml
---
title: ECU Trouble Codes
summary: Read and interpret OBD1 ECU diagnostic trouble codes on 1992-2000 Hondas.
tags: [ecu, obd1, diagnostics]
applies_to:
  brand: [honda, acura]        # Honda and/or Acura
  models: [civic, integra]     # model names
  chassis: [EG, EK, DC2]       # chassis codes
  engines: [B-Series, B18C]    # whole families (B-Series, K-Series) and/or specific codes (B18C, K20A)
  ecus: [P28, P30, PM6]        # ECU part numbers, where relevant
  obd: [0, 1]                  # OBD generation(s): 0, 1, 2
  years: 1992-2000             # or use scope: all-honda-cars
complexity: beginner           # beginner | intermediate | advanced
---
```

`applies_to` is **flexible and open-ended**. Hondabase covers the whole Honda and Acura
catalog, not just Honda cars (motorcycles, aircraft, power equipment, marine), so do not
assume a car. Every field is optional, and **any field you add renders in the panel** with a
humanized label, for example `displacement: 1000cc` on a motorcycle or `systems: [avionics]`
on a HondaJet article. A few fields get special styling (OBD generations as badges, engine
families like `B-Series` as badges); everything else shows as labelled chips. So a reader
instantly sees that, for example, the P30 is an OBD1 ECU.

`last_updated` is derived from git; never hand-write it.

## 3. Structure

Open with a short **lead paragraph** (no heading) that says what the thing is and when it
matters. Then use only the sections that fit:

```
<lead paragraph>

## Overview          background / how it works
## Symptoms          what you observe; codes; affected years (diagnostic topics)
## Procedure         numbered steps, one action per step
## Specifications    tables: torque, voltages, gaps, part numbers
## Notes and gotchas common mistakes, warnings, TSBs
## Related           links to related Hondabase articles
```

A pure reference (for example a list of trouble codes) can be a single list under the lead.
One `# H1` only (the title). Headings are sentence case, with acronyms left uppercase
("Counting the flashes", "OBD1 ECU pinout").

## 4. Writing conventions

- **Terminology casing.** Keep acronyms uppercase: ECU, ECM, OBD0/OBD1/OBD2, VTEC, VTC,
  TPS, MAP, MAF, IAT, ECT, CKP, CYP, TDC, IAC (EACV), EGR, ELD, LAF, O2, CEL/MIL, SCS, TCU.
  Engine and chassis codes uppercase: B16, B18C, D16, K20, H22, EK, EG, DC2, CL9, CM6.
  Brands: Honda, Acura.
- **Links.** Link to related Hondabase articles with site-relative paths, for example
  `[knock sensor](/cars/electronics/knock-sensor)`. Do NOT auto-link every technical term
  (no wiki-style link soup). Use external links sparingly and only to authoritative or
  manufacturer sources; do not link dead forum threads, name the source instead.
- **Images.** Co-locate in the bundle and reference by filename, with real alt text:
  `![SCS connector under the glovebox](servicejumper.jpg)`. Add an italic caption under it
  when helpful: `*The SCS connector lives behind the glovebox kick panel.*`
- **Units.** Metric first, imperial in parentheses where useful: `30 Nm (22 ft-lb)`.
- **Specifications** go in tables, not prose.
- **Callouts** use a blockquote with a bold label:
  `> **Warning:** disconnect the battery first.` Also `> **Tip:**` and `> **Note:**`.
- **Widgets** (interactive components, where available) embed on their own line:
  `::: widget error-codes obd="1" :::` (rolling out; use this syntax when documented).
- **No raw HTML** in articles; it is escaped on render. Use Markdown (tables, code, lists).

## 5. Adapting legacy / wiki content (checklist)

- [ ] Strip TWiki auto-links; keep only meaningful links and repoint them to Hondabase
      articles, or remove them.
- [ ] Add a lead paragraph; restructure the body into the section template.
- [ ] Normalize terminology casing per section 4.
- [ ] Replace or remove dead external/forum links; turn "see this thread" into a named
      reference.
- [ ] Move specs into tables; turn warnings into callouts.
- [ ] Co-locate images, write real alt text, add captions.
- [ ] Keep the slug; let the title be a clean H1 (or a `title:` frontmatter).

See also: [markdown-cheat-sheet.md](../markdown-cheat-sheet.md).
