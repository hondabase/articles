---
summary: 'Php Wiki is written in the serverside scripting language PHP, available from http://www.php.net/. PHP resembles C and Perl in its syntax, and functions much like ASP, !EmbPerl or JSP.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - tuning
  - rom
  - sensors
  - reference
---

# More About Mechanics

[Php Wiki](/cars/electronics/php-wiki) is written in the server-side scripting language PHP, available from [http://www.php.net/](http://www.php.net/). PHP resembles C and Perl in its syntax, and functions much like ASP, !EmbPerl or JSP. [Php Wiki](/cars/electronics/php-wiki) consists of a dozen or so files of mixed PHP and HTML. The web pages that make up a [Wiki Wiki Web](/cars/electronics/wiki-wiki-web) based on PHP live in a DBM file with backup copies of previous versions of pages stored in a second DBM file. Every time a user hits the site the page requested is pulled from the DBM and rendered on the fly. The user only ever requests the file index.php, which then decides which other php files to include. Links to pages in the wiki are automatically linked: [Php Wiki](/cars/electronics/php-wiki). This might be the single most compelling aspect of a wiki, the ability to add pages simply by linking to them. The next most compelling thing is how easily external URL's link like this: # [http://www.wcsb.org/](http://www.wcsb.org/)\# [ftp://ftp.redhat.com/](ftp://ftp.redhat.com/)\# [news://news.mozilla.org/](news://news.mozilla.org/)\# [http://www.slashdot.com/](http://www.slashdot.com/)\# [http://theregister.co.uk/](http://theregister.co.uk/)Combined with one namespace and a simple markup, a Wiki exhibits many of the characteristics of [Wabi Sabi](/cars/electronics/wabi-sabi). [Php Wiki](/cars/electronics/php-wiki) is licensed under the Gnu General Public license, which you should be able to see here: [http://www.gnu.org/copyleft/gpl.txt](http://www.gnu.org/copyleft/gpl.txt). ---

[Php Wiki Documentation](/cars/electronics/php-wiki-documentation)
