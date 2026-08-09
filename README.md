# Hondabase Articles

Content repository for the articles published on https://hondabase.com. The website
indexes this repo directly — the database is fully derived from these files and can be
rebuilt at any time with `php artisan hondabase:reindex` from the site checkout.

See [CONTRIBUTING.md](CONTRIBUTING.md) for writing guidelines.

## Structure

An article is a folder containing a Markdown file of the same name, with its images and
attachments beside it:

```
<type>/<category-path>/<slug>/<slug>.md
```

For example:

```
cars/sensors/a143-transistor/a143-transistor.md
cars/honda/civic/ef/tuning/some-article/some-article.md
pt/cars/tuning/some-article/some-article.md          (Portuguese locale)
```

- **`<type>`** is one of `cars`, `motorcycles`, `engines`, `aircraft`, `common`
  (defined in the site's `config/hondabase.php`). Only `cars` has content today;
  create the other folders when the first article for them lands.
- **`<category-path>`** is any depth of `[a-z0-9-]` folder segments. The folder path
  *is* the category — never put `category:` in frontmatter. Segments that match a
  taxonomy node (make/model/generation, e.g. `honda/civic/ef`) are recognized as such
  by the indexer; everything else is treated as a subject category.
- **`_partials/`** holds reusable Markdown fragments included by articles.

## Subject categories

These are the subject categories in live use under `cars/`, matching the site's
canonical subject vocabulary (managed at `/admin/taxonomy`):

| Folder | Subject |
|---|---|
| `ecu` | ECU & Engine Management (includes ROM/tuning-map material, tagged `rom`) |
| `sensors` | Sensors & Solenoids |
| `wiring` | Wiring & Conversions |
| `tuning` | Tuning |
| `diagnostics` | Diagnostics & Troubleshooting |
| `reference` | Reference & General |
| `fueling` | Fueling & Injectors |
| `ignition` | Ignition |
| `transmissions` | Transmission |
| `electronics` | Electronics |
| `engines` | Engine & Drivetrain (engine-family reference, e.g. `engines/k-series`) |

Other subjects exist in the vocabulary (`brakes`, `suspension`, `chassis`,
`forced-induction`, `maintenance`) but have no articles yet — use them when content
warrants; do not pre-create empty folders.

Pick the narrowest existing category that fits. Chassis-specific articles nest under the
make/model/generation path instead (e.g. `cars/honda/civic/ef/tuning/`).

## Frontmatter

The linter (`php artisan app:lint-articles` in the site checkout) enforces the schema.
Allowed top-level keys — anything else is an error:

```yaml
---
title: 'Optional — defaults to the article''s first H1'
summary: 'One or two sentences shown in listings and search results.'
tags: [ecu, electronics, components]        # free-form, lowercase; reuse existing tags
applies_to:
  make: [honda]                             # allowed keys: make, models/model,
  models: [civic, integra]                  #   chassis, trims/trim, engines,
  chassis: [ef, eg, ek]                     #   years, scope
complexity: intermediate                    # beginner | intermediate | advanced
sources:                                    # optional; for ported/adapted material
  - name: pgmfi.org
    url: https://...
---
```

Not allowed: `category` (derived from the folder path), `date`/`last_updated` (derived
from git history), and `applies_to.ecus`/`applies_to.obd` (use `tags` instead —
e.g. `obd1`, `p28`).
