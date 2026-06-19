---
summary: 'An overview of the Back Links functionality used to identify pages that link to or reference the current technical article.'
tags: [reference, site-navigation]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Back Links Functionality

The Back Links function performs a comprehensive search across the documentation database to identify all pages that contain a hyperlink to the current article. 

## Purpose
This tool serves two primary diagnostic functions for site navigation and content auditing:
* **Link Discovery:** Identifies all pages that link directly to the current document.
* **Reference Tracking:** Answers the query: "Which pages contain the title of this page?" to identify implicit references or mentions within the documentation.

> [!NOTE]
> The Back Links tool is an automated utility. If a page is renamed, ensure that internal links are updated to maintain accurate back-link reporting.

## Usage
The function is invoked via the system's internal query parameters. The following table outlines the available configuration options for the Back Links module:

| Parameter | Description | Default |
| :--- | :--- | :--- |
| `exclude` | Specifies pages to omit from the results. | Null |
| `include_self` | Determines if the current page is listed in the results. | 1 (True) |
| `noheader` | Toggles the display of the results header. | 0 (False) |
| `page` | Defines the specific target page for the search. | Current Page |
| `info` | Displays additional metadata regarding the link source. | Null |
