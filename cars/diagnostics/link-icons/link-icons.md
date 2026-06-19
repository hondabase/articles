---
summary: 'Link Icons provide visual indicators for different URL types within the documentation system to improve navigation and link identification.'
tags: [reference, documentation, navigation]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Link Icons for Documentation

Link Icons are an optional feature that displays specific icons in front of URLs to indicate the link type.

## Icon Reference

The following icons are used to categorize link types:

| Icon | Link Type |
| :--- | :--- |
| ![HTTP](http://phpwiki.sourceforge.net/alpha/themes/default/images/http.png) | HTTP link |
| ![Generic](http://phpwiki.sourceforge.net/alpha/themes/default/images/url.png) | Generic internet link |
| ![InterWiki](http://phpwiki.sourceforge.net/alpha/themes/default/images/interwiki.png) | InterWiki link |
| ![HTTPS](http://phpwiki.sourceforge.net/alpha/themes/default/images/https.png) | HTTPS link |
| ![Mailto](http://phpwiki.sourceforge.net/alpha/themes/default/images/mailto.png) | Mailto link |
| ![FTP](http://phpwiki.sourceforge.net/alpha/themes/default/images/ftp.png) | FTP link |

> [!NOTE]
> Some default icons utilize the PNG alpha channel for smooth rendering on various backgrounds. Older browsers may not support this feature, which can result in rendering artifacts.

## Implementation Examples

Link icons appear automatically when the feature is enabled by the administrator.

### InterWiki Links
*   [InterWiki](/cars/rom/inter-wiki) link to [PhpWiki](/cars/sensors/php-wiki):InterWiki
*   Named [InterWiki](/cars/rom/inter-wiki) link: [Why Wiki Works](http://c2.com/cgi/wiki?WhyWikiWorks)

### Standard URLs
*   **Email:** [PhpWiki-talk mailing list](mailto:phpwiki-talk@lists.sourceforge.net)
*   **HTTP:** [PhpWiki Home Page](http://phpwiki.sourceforge.net/phpwiki/)
*   **HTTPS:** [PhpWiki Home Page](https://phpwiki.sourceforge.net/phpwiki/)
*   **FTP:** [SourceForge FTP](ftp://ftp.sourceforge.net/)

> [!TIP]
> A generic icon is displayed for less common link types, such as `news://` or `gopher://` protocols.

## Protocol Restrictions
Link icons and automatic link generation only function for protocols explicitly permitted by the system configuration. Links using unsupported protocols (e.g., `bogus://` or `bolo://`) will not display icons or generate clickable links unless specifically added to the allowed protocol list by an administrator.
