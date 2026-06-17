---
summary: "A technical overview of orphaned pages within the Hondabase documentation system, including identification and maintenance procedures."
tags: [maintenance, documentation, reference]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Orphaned Pages Documentation

Orphaned pages are defined as documentation entries that contain no inbound hyperlinks from other pages within the Hondabase ecosystem. These pages are often difficult to discover through standard navigation and may indicate incomplete documentation or deprecated content.

## Identification
To identify orphaned pages, the system tracks the following metadata:

| Metric | Description |
| :--- | :--- |
| **Hits** | Total number of unique page views. |
| **Pagename** | The unique identifier/URL slug of the page. |
| **Mtime** | The last modified timestamp of the document. |

> [!NOTE]
> Regularly auditing orphaned pages is essential for maintaining site structure and ensuring that technical information remains accessible to users.

## Maintenance Procedures
If a page is identified as orphaned, follow these steps to integrate it into the documentation structure:

1. **Review Content:** Determine if the information is still accurate and relevant to the current technical scope.
2. **Cross-Reference:** Identify existing articles where a link to this page would provide additional technical context.
3. **Update Navigation:** Add the link to the relevant parent or category page to ensure it is discoverable via the site hierarchy.
4. **Deprecation:** If the content is obsolete, mark the page for archival or deletion.