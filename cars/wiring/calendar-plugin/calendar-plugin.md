---
summary: 'Technical overview of the Calendar Plugin functionality for wiki page management.'
tags: [wiki-administration, plugins, tools]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
---

# Calendar Plugin

The Calendar Plugin is a tool designed to generate a monthly calendar within a wiki page. It is useful for organizing date-linked entries.

---

## Usage

The calendar generates links for individual dates, which point to specific "day pages." By default, the name of these pages is created by appending the date to the parent page name where the calendar is displayed.

## Plugin Arguments

### Calendar Selection
*   **year:** Specify the calendar year (default: current year).
*   **month:** Specify the calendar month (default: current month).
*   **month_offset:** Value added to the month parameter. Useful for displaying multiple consecutive months on a single page.

### Day Page Naming
*   **date_format:** Strftime-style format string used to generate page names for day-specific links (default: `%Y-%m-%d`).
*   **prefix:** String prepended to the formatted date to generate day-page names (default: `[pagename:`).

### Appearance Settings
*   **month_format:** Strftime-style format string used for the calendar title (default: `%B, %Y`).
*   **wday_format:** Strftime-style format string for day-of-week headers.
*   **start_wday:** Defines the starting day of the week (0 for Sunday, 6 for Saturday).
