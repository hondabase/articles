---
summary: 'New lists: asterisks, hash marks, and ";text:def" (wrong...) bullet l1 l2 l2 l3 one two three Term1: definition1.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - ecu
  - reference
---

# New Markup Test Page

New lists: asterisks, hash marks, and ";text:def" (wrong...)

- bullet
- l1 * l2 * l2 * l3 # one #two #three

Term1: definition1.1 defintion1.2 Term2 : defintion2 Term3: defintion3 Term4: definition4 defintion4.2 Term5 : defintion5 Mixed - * ul1 # ul1-ol1 # ul1-ol2 * ul1-ol2-ul1 * ul1-ol2-ul2 * ul1-ol2-ul2-ul1 * ul1-ol2-ul2-ul2 - l1

 ```

      preformatted text
   
```

 * l2 ---

 old lists, oddly enough, work fine - level 1
- l1 *l2 *l2 *l3 *l3 *l4 *l3 *l5 *l3

#  one 

#  two 

 #one #two *l1 #three #four *l1 *l2 # one # two ```

 preformatted text
 some more text
```

 *l1 *l2 #  number 

#  number 

this is a plain paragraph - bullet

this is a plain paragraph again #  number 

---

***Link tests***\# normal: Home Page\# in brackets: Home Page -- named: the front page\# Link in brackets: [http://phpwiki.sourceforge.net/](http://phpwiki.sourceforge.net/)\# Link outside brackets: [http://phpwiki.sourceforge.net/](http://phpwiki.sourceforge.net/)\# Link with Wiki word: [http://phpwiki.sourceforge.net/phpwiki/index.php?HomePage](http://phpwiki.sourceforge.net/phpwiki/index.php?HomePage)\# Two consecutive links: [http://phpwiki.sourceforge.net/](http://phpwiki.sourceforge.net/) [http://phpwiki.sourceforge.net/phpwiki/](http://phpwiki.sourceforge.net/phpwiki/)\# [PhpWiki on Sourceforge ](http://phpwiki.sourceforge.net/)\# [URL with a WikiWord ](http://phpwiki.sourceforge.net/phpwiki/index.php?RecentChanges)\# Javascript: boo!  (is now: named internal link) # A [Link produces a Link\# A Link looks like this: [Link\# This is a [[]] line break link # Also this page is [not linked to, and this one is !NotLinkedTo and this one neither !http://not.linked.to/. * Wiki Name - Wiki Name Same Stem -- !!WikiName - !!WikiNameSameStem * !!WikiName - !!WikiNameSameStem -- Wiki Name - Wiki Name Same Stem * Wiki Name Same Stem - Wiki Name -- !!WikiNameSameStem - !!WikiName * !!WikiNameSameStem - !!WikiName -- Wiki Name Same Stem - Wiki Name---

Markup tests: ***underscores for bold***'''quotes for bold''' ''quotes for italic'' ***''underscores bold italic''***'''''five quotes bold italic''''' ''''''six quotes'''''' '''''Bold italic''' and italic'' (buggy) '''Bold and ''bold-italic''''' (also buggy) #  h1 

##  h2 

###  h3 

this is plain text with 
a line break look at the [markup language](http://phpwiki.sourceforge.net/)you cannot use &, < or > ---

Usage in preformatted text: ```

 __underscores for bold__
 '''quotes for bold'''
 ''quotes for italic''
 __''underscores bold italic''__
 '''''five quotes bold italic'''''
 ''''''six quotes''''''
 !!! h1
 !! h2
 ! h3
 this is plain text with <br></br>

 a line break
 look at the <a href="http://phpwiki.sourceforge.net/" rel="nofollow noopener">markup language</a>
 you cannot use &, < or >
```
