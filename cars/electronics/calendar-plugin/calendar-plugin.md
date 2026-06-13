---
summary: "The Calendar Plugin can be used to generate a monthly calendar in a wiki page. It's handy for Personal Wikis."
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - ecu
  - reference
  - sensors
  - wiring
  - conversion
  - diagnostics
---

# Calendar Plugin

The [Calendar Plugin](/cars/electronics/calendar-plugin) can be used to generate a monthly calendar in a wiki page. It's handy for Personal Wikis. Individual dates in the calendar link to specially named wiki pages. The names for the "day pages" are by default formed by appending the date to the pagename on which the calendar appears. ''This feature was inspired by [Manila](http://manila.userland.com/), and first implemented by Gary Benson. It was later implemented as a [Wiki Plugin](/cars/electronics/wiki-plugin) by Jeff Dairiki.''

##  Usage: 

 wil get you: ---

##  Plugin Arguments 

###  Selection of Month 

;__year__: Specify the year for the calendar. (Default: current year.) ;__month__: Specify the month for the calendar. (Default: current month.) ;__month_offset__: Added to ''month''. Can be used to include several months worth of calendars on a single wiki page. ###  "Day Page" Names 

;__date_format__:Strftime style format string used to generate page names for the "day pages." The default value is '%Y-%m-%d'. ;__prefix__: Prepended to the date (formatted per ''date_format'') to generate the "day page" names. The default value is '[pagename:'. ###  Appearance 

;__month_format__: Strftime style format string used to generate the title of the calendar. (Default: '%B, %Y'.) ;__wday_format__: Strftime style format string used to generate the day-of-week names at the top of the calendar. ;__start_wday__: What day of the week does the calendar start on. This should be specified as an integer in the range zero (Sunday) through six (Saturday), inclusive. ---

###  Patch for 1.2 

Gary Benson wrote the first calendar implementation for [Php Wiki](/cars/electronics/php-wiki) 1.2. (Since 1.2 doesn't support plugins, it uses a ###CALENDAR### token as a trigger.) Gary provides a screenshot at ![calender.png](http://inauspicious.org/files/screenshots/calender.png), a [patch ](http://inauspicious.org/files/phpwiki/phpwiki-1.2.0-calendar.patch) (on 1.2.0), and [calendar.php ](http://inauspicious.org/files/phpwiki/calendar.php) (which renders a view of the year.) ---

[Php Wiki Documentation](/cars/electronics/php-wiki-documentation)
