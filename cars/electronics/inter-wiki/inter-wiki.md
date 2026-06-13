---
summary: 'This wiki supports Inter Wiki links in a style copied from Use Mod: wiki. Links to pages in other wikis can be made without having to know or type the...'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - tuning
  - rom
  - sensors
  - reference
---

# Inter Wiki

This wiki supports [Inter Wiki](/cars/electronics/inter-wiki) links in a style copied from Use Mod: wiki. Links to pages in other wikis can be made without having to know or type the full URLs, for example: Meat Ball:InterWiki will link to the page named "~InterWiki" at Meatball wiki. The ~InterWiki map is taken from the the  block in [Inter Wiki Map](/cars/electronics/inter-wiki-map), but that page must be locked for it to work. This denies a potential hacker the ability to nefariously change every ~InterWiki link to point to some evil URL. If no map is found in [Inter Wiki Map](/cars/electronics/inter-wiki-map) (or the page is not locked), [Php Wiki](/cars/electronics/php-wiki) will fall back to using the file lib/interwiki.map in your phpwiki distribution. The ~InterWiki map file in use at [Php Wiki](/cars/electronics/php-wiki): can be viewed at [http://phpwiki.sf.net/interwiki.map](http://phpwiki.sf.net/interwiki.map). The map file is manually updated. It is based upon and periodically synchronized with [UseMod's InterMap](http://usemod.com/intermap.txt) but it is not quite identical. One notable difference from Use Mod: is that [Php Wiki](/cars/electronics/php-wiki) supports '%s' within the URLs in the map--see the entry for RFC for an example of how this works. Not all of the entries in the [Inter Wiki Map](/cars/electronics/inter-wiki-map) are actual wikis. For example, these are just regular web sites: Dictionary:fungible, Jargon File:Alderson loop, IMDB:Roman Holiday, RFC:2822, and ISBN:020171499X. The "Category" moniker is a special entry which allows one to link a wiki page to a Category page without creating a back-reference. Thus Category:Category links to the Category Category page, yet this page won't show up in the back-links listing of Category Category. The term "InterWiki" also refers to a broader concept. See [Php Wiki](/cars/electronics/php-wiki):InterWikiSearch for more links. ---

[Php Wiki Documentation](/cars/electronics/php-wiki-documentation)
