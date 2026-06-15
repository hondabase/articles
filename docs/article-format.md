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
sources:
  - name: pgmfi.org wiki
    title: ECU Trouble Codes
    url: /pgmfi/wiki/library/ecu-trouble-codes
    license: CC BY-NC-SA 1.0
    license_url: https://creativecommons.org/licenses/by-nc-sa/1.0/
    adapted: true
---
```

Use `sources` for adapted or imported material. Every port from the PGMFI wiki must retain
its PGMFI source entry. Do not put author names in frontmatter: original and HondaBase
authors are durable database records and render together on the article page.

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
  `[knock sensor](/cars/ignition/knock-sensor)`. Do NOT auto-link every technical term
  (no wiki-style link soup). Use external links sparingly and only to authoritative or
  manufacturer sources; do not link dead forum threads, name the source instead.
- **Images.** Co-locate in the bundle and reference by filename, with real alt text:
  `![SCS connector under the glovebox](servicejumper.jpg)`. Add an italic caption under it
  when helpful: `*The SCS connector lives behind the glovebox kick panel.*`
- **Image carousels.** Use a fenced `carousel` block for a sequence of two or more
  co-located images. Separate slides with `<!-- slide -->`. Every slide needs alt text and
  may have one italic plain-text caption:

  ````markdown
  ```carousel
  ![Front of the ECU board](board-front.jpg)
  *Front view before modification.*
  <!-- slide -->
  ![Rear of the ECU board](board-rear.jpg)
  ```
  ````

  Carousels do not support remote images, arbitrary prose, nested widgets, or raw HTML.
- **Searchable wirelists.** Use a fenced `wirelist` block for large ECU pin/trace datasets
  that need filtering on a phone. The structured editor manages ECU variants, component
  groups, and rows; do not hand-edit the JSON unless you validate it with
  `php artisan app:lint-articles`.
- **Attachments and downloads.** Recover every available source attachment that the
  article retains, co-locate it in the article bundle, and link it by filename:
  `[Download the archived schematic](schematic.pdf)`. Verify both the local file and the
  rendered download URL. If an attachment was not recovered, do not leave a broken link;
  explicitly say that the source referenced a missing file when that fact matters.
- **Units.** Metric first, imperial in parentheses where useful: `30 Nm (22 ft-lb)`.
- **Specifications** go in tables, not prose.
- **Callouts** may use GitHub alert syntax on separate blockquote lines:
  `> [!CAUTION]` followed by `> Disconnect the battery first.` Supported labels are
  `NOTE`, `TIP`, `IMPORTANT`, `WARNING`, and `CAUTION`. A simple labelled blockquote such
  as `> **Warning:** disconnect the battery first.` is also supported.
- **Widgets** (interactive components, where available) embed on their own line:
  `::: widget error-codes obd="1" :::` (rolling out; use this syntax when documented).
- **No raw HTML** in articles; it is escaped on render. Use Markdown (tables, code, lists).

## 5. Source-faithful legacy ports

A wiki port is an editorial adaptation of the archived source, not an opportunity to
invent a cleaner technical story. Rewrite and restructure the material for Hondabase,
but preserve what the source actually establishes, including its uncertainty.

- **Use the archived page and its assets as primary evidence.** Compare the finished
  article against the raw source after conversion; a generated draft or passing lint is
  not proof that the content survived correctly.
- **Inventory attachments before rewriting.** Compare the archive's attachment records
  with the files copied into the article bundle. Preserve useful downloads as well as
  displayed images, and verify that every retained image or download URL resolves through
  the article asset route.
- **Do not invent technical meaning.** Never add component functions, compatibility
  claims, procedures, recommendations, units, or safety claims merely because they seem
  plausible. Add outside facts only when they come from an authoritative source and are
  clearly distinguished from the archived material.
- **Preserve uncertainty and oddities.** Keep qualifiers such as "possibly," "unverified,"
  and "unknown." When a source contains a suspicious value or contradiction, transcribe
  it faithfully and add a note explaining the issue instead of silently correcting it.
- **Treat tables as data.** Verify every row, column, label, unit, address, and pin against
  the source. Do not infer missing headings or convert values unless the conversion is
  explicit and checked.
- **Label historical guidance.** Old supplier part numbers, software behavior, tuning
  defaults, and community procedures must be described as archived or historical. Do not
  turn a legacy example into a current recommendation.
- **Do not overstate safety.** Words such as "safe," "required," "will," and "works with"
  need direct support. Legacy tuning values and hardware modifications should be framed as
  source examples and paired with appropriate verification warnings.
- **Source-faithful does not mean verbatim.** Remove personalities, forum chatter, and
  boilerplate; rewrite in clear prose while keeping the technical claims and limitations
  intact.
- **Use renderer-supported Markdown.** GitHub alert callouts, standard blockquotes, and
  image carousels are supported; do not use raw HTML. Only use widgets documented for
  Hondabase.

## 6. SEO Best Practices

To ensure articles rank well on search engines and attract readers, follow these SEO rules:

- **Descriptive Titles:** Use a clean, descriptive H1 title (e.g., `# OBD1 Civic/Integra Auto to Manual Conversion` instead of `# OBD1 Civic Integra Auto Manual`).
- **Compelling Meta Description:** Always provide a `summary` in the frontmatter. Keep it under 160 characters, and make it a compelling summary of what the reader will learn. The web renderer uses this as the page's HTML `<meta name="description">` tag.
- **Heading Hierarchy:** Use exactly one H1 per article (the title). Use `##` for main sections, and `###` for sub-sections. Never skip levels (e.g., do not go from H1 to H3). All headings must be clean, readable sentence-cased text.
- **Keyword Integration & Search Intent:** Proactively use natural, search-friendly terms in the lead paragraph and throughout the article (e.g., "how to socket a Honda ECU", "diagnostic trouble codes", "EF Civic VTEC swap"). Do not stuff keywords.
- **Alt Text for Images:** Always provide descriptive alt text for images to improve image search indexing (e.g., `![OBD1 ECU board layout showing RP17 and RP18 locations](OBD1auto_manual.jpg)` instead of `![OBD1auto_manual](OBD1auto_manual.jpg)`).
- **SEO-Friendly Anchor Text:** Never use "click here" or raw URLs as link text. Instead, write descriptive, natural anchor text that describes the target page (e.g., `read the [OBD1 ECU pinout guide](/cars/electronics/obd1-pinout)`).
- **Remove Noise and Boilerplate:** Strip trailing wiki/forum boilerplate (e.g., "Page moved from...", edit dates, signatures like `-=dave`, attachment listings, or "Click edit below"). These dilute keyword density and look unprofessional.

## 7. Adapting legacy / wiki content (checklist)

- [ ] Strip TWiki auto-links; keep only meaningful links and repoint them to Hondabase articles (e.g., `/cars/electronics/slug`), or remove them.
- [ ] Add a lead paragraph; restructure the body into the section template.
- [ ] Normalize terminology casing per section 4.
- [ ] Replace or remove dead external/forum links; turn "see this thread" into a named reference.
- [ ] Move specs into tables; turn warnings into callouts.
- [ ] Co-locate images, write real alt text, add captions.
- [ ] Keep the slug; let the title be a clean H1 (or a `title:` frontmatter).
- [ ] Ensure frontmatter contains a compelling SEO `summary` (meta description) under 160 characters.
- [ ] Clean up broken markdown tables and format column structures properly.
- [ ] Ensure heading hierarchy is strictly sequential (no skipped levels, e.g., H2 -> H3, no H4/H5 without H3).

- [ ] Compare the completed article against the raw archived page and every retained asset.
- [ ] Confirm every available source attachment was copied or intentionally omitted; test
      every retained image and download URL through the rendered article.
- [ ] Verify tables, pinouts, formulas, addresses, values, units, and filenames against the source.
- [ ] Preserve uncertainty; flag suspicious or contradictory source values instead of silently fixing them.
- [ ] Label legacy software settings, supplier numbers, and tuning advice as historical examples.
- [ ] Normalize callouts and image carousels to supported syntax and confirm they render as intended.

See also: [markdown-cheat-sheet.md](../markdown-cheat-sheet.md).
