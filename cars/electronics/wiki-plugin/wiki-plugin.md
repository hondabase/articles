---
summary: 'The latest hacks include support for !WikiPlugins. Wiki Plugins allow one to easily add new types of dynamic content (as well as other functionality) to wiki pages within Php Wiki.'
applies_to:
  obd: [0, 1, 2]
  brand: Acura
complexity: advanced
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - wiring
  - conversion
  - diagnostics
---

# Wiki Plugin

The latest hacks include support for !WikiPlugins.

###  [Wiki Plugins](/cars/electronics/wiki-plugin) allow one to easily add new types of dynamic content (as well as other functionality) to wiki pages within [Php Wiki](/cars/electronics/php-wiki). In this very wiki, the [Recent Changes](/cars/electronics/recent-changes), [Back Links](/cars/electronics/back-links), [Like Pages](/cars/electronics/like-pages) and [Debug Info](/cars/electronics/debug-info) pages are all implemented using plugins. 

I expect that the search result pages, as well as much [Php Wiki Administration](/cars/electronics/php-wiki-administration) will soon be implemented via plugins as well. (I think the oh-so-ugly [Magic Php Wiki URLs](/cars/electronics/magic-php-wiki-ur-ls) can be replaced by plugins, too.) ###  Example 

Currently, one invokes a plugin by putting something like: ''''plugin !BackLinks?> into a regular wiki-page. That particular example produces as list of pages which link to the current page. Here it is: Back Links?> (This is great for Category and Topic pages. You can use this to get an automatic in-line listing of pages in the Category or Topic.) ###  Details 

(This is all subject to change.) Plugins can take certain named arguments (most do). The values of these arguments can be determined four different ways. In order of precedence: # The plugin invocation can specify the value for an argument, like so: ;;: ''''plugin !BackLinks page=!OtherPage ?> # The argument can be specified via an HTTP query argument. This doesn't happen (is not allowed) unless the argument is mentioned in the plugin invocation: ;;: ''''plugin !BackLinks page ?> # Default values specified in the plugin invocation: ;;: ''''plugin !BackLinks page||=!OtherPage ?> # The plugin must supply default values for `each` argument it uses. (The [Back Links](/cars/electronics/back-links) plugin uses the current page as the default value for the ''page'' argument. ###  Existing Plugins 

- [Back Links](/cars/electronics/back-links)
- [Calendar Plugin](/cars/electronics/calendar-plugin)
- [Debug Info](/cars/electronics/debug-info)
- [Full Text Search](/cars/electronics/full-text-search)
- Include Page
- [Like Pages](/cars/electronics/like-pages)
- [Most Popular](/cars/electronics/most-popular)
- [Page History](/cars/electronics/page-history)
- [Recent Changes](/cars/electronics/recent-changes)
- text2png
- [Title Search](/cars/electronics/title-search)
- View Source
- walkabout

###  More Ideas for Plugins 

- Integrate Search form with individual [Inter Wiki](/cars/electronics/inter-wiki) map entries

 e.g. Search Php Website for:[[]] (Search) - Wanted Pages, [Orphaned Pages](/cars/electronics/orphaned-pages), other various indexing schemes.
- Diff, [Page History](/cars/electronics/page-history)
- Redirect plugin -- ''''plugin Redirect target=!OtherPage ?>
- Insert XML/RSS/RDF news content from location=xxx where location is a parameter to the plugin, maybe include some formatting control of the output generated.

---

Pages in this category: Back Links page=pagename noheader=1?> - [Full Text Search](/cars/electronics/full-text-search): [Find Page](/cars/electronics/find-page)
- [Title Search](/cars/electronics/title-search): [Like Pages](/cars/electronics/like-pages) (match_head, match_tail).

---

[Php Wiki Documentation](/cars/electronics/php-wiki-documentation)
