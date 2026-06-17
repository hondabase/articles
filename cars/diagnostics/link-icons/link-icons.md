---
summary: 'Link Icons are an optional new feature of Php Wiki. When activated, icons will be displayed in front of URLs to indicate the type of link.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Link Icons'
    url: /pgmfi/wiki/library/link-icons
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Link Icons

[Link Icons](/cars/diagnostics/link-icons) are an optional new feature of [Php Wiki](/cars/sensors/php-wiki). When activated, icons will be displayed in front of URLs to indicate the type of link. - [http://phpwiki.sourceforge.net/alpha/themes/default/images/http.png](http://phpwiki.sourceforge.net/alpha/themes/default/images/http.png) http link
- [http://phpwiki.sourceforge.net/alpha/themes/default/images/url.png](http://phpwiki.sourceforge.net/alpha/themes/default/images/url.png) generic internet link
- [http://phpwiki.sourceforge.net/alpha/themes/default/images/interwiki.png](http://phpwiki.sourceforge.net/alpha/themes/default/images/interwiki.png) [Inter Wiki](/cars/rom/inter-wiki) link
- [http://phpwiki.sourceforge.net/alpha/themes/default/images/https.png](http://phpwiki.sourceforge.net/alpha/themes/default/images/https.png) https link
- [http://phpwiki.sourceforge.net/alpha/themes/default/images/mailto.png](http://phpwiki.sourceforge.net/alpha/themes/default/images/mailto.png) mailto link
- [http://phpwiki.sourceforge.net/alpha/themes/default/images/ftp.png](http://phpwiki.sourceforge.net/alpha/themes/default/images/ftp.png) ftp link

;__Note__: Some of the default icons use the alpha channel feature of the [PNG](http://www.libpng.org/pub/png/png-sitemap.html) image format for smooth rendering on any page color or textured background. Older browsers may not display all the images properly.

# Examples 

The following examples will display with the above link icons only if the administrator has enabled this feature.

## [Inter Wiki](/cars/rom/inter-wiki) links 

- [Inter Wiki](/cars/rom/inter-wiki) link [Php Wiki](/cars/sensors/php-wiki):InterWiki

- A named [Inter Wiki](/cars/rom/inter-wiki) read Why Wiki Works at c2.

## URLs 

- Email address PhpWiki-talk mailing list

- Normal http link [PhpWiki's Home Page](http://phpwiki.sourceforge.net/phpwiki/)

- Secure http link [PhpWiki's Home Page](https://phpwiki.sourceforge.net/phpwiki/)

- File transfer [ftp://ftp.sourceforge.net/]()

''A generic icon is shown for other less common link types.'' - [news://nntp.news.com](news://nntp.news.com)

- [gopher://gopher.caltech.cmu.edu](gopher://gopher.caltech.cmu.edu)

[Link Icons](/cars/diagnostics/link-icons) will only display when the URL protocol is one which [Php Wiki](/cars/sensors/php-wiki) is allowed to link to. The following examples won't show any icons and [Php Wiki](/cars/sensors/php-wiki) won't automatically provide double-clickable links either, unless the administrator adds them: - bogus://oedipus.nostradamus.com

- bolo://lgm.cheshire.org

---

[Php Wiki Documentation](/cars/reference/php-wiki-documentation)
