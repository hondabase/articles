---
summary: 'About phpwiki: URLs A special type of URL is available for making links to perform administrative and other special functions in Php Wiki.'
tags: [ecu, reference, tuning, rom, sensors, wiring, conversion, diagnostics]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Magic Php Wiki UR Ls'
    url: /pgmfi/wiki/library/magic-php-wiki-ur-ls
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Magic Php Wiki UR Ls

#  About phpwiki: URLs 

A special type of URL is available for making links to perform administrative and other special functions in [Php Wiki](/cars/sensors/php-wiki). Here is a brief description of how they work. The basic syntax of a phpwiki: URL is ***phpwiki:__''pagename''***?__''query-args'' If ''pagename'' is omitted it defaults to the current page. ''Query-args'' should be a set of parameters in standard HTTP GET format. The "action=''x''" parameter should almost always be given. It can be one of ***browse***, ***info***, ***diff***, ***search***, ***edit***, ***zip***, ***dumpserial***, ***loadserial***, ***remove***, ***lock***, ***unlock***, ***login***, ***logout***, ***setprefs*** or ***save***. The default action is ***browse***. Some of the actions accept other parameters. ;__info__: Accepts ***showpagesource***. ;__search__: Accepts ***searchterm***, and ***searchtype***. ;__edit__: Accepts ***version***. ;__remove__: Accepts ***verify***. ;__save__: Accepts ***editversion***, ***minor_edit***, and ***content***. ;__setprefs__: Accepts ***edit_area_width***, ***edit_area_height***. ##  Writing Magic Links in Wiki Pages 

A magic link looks like: ***[*** ''text'' The "''text'' __|__" is optional but usually recommended. If given it will provide the label for the link. The ''phpwiki-url'' is a ***phpwiki:*** URL as described above. ###  Some examples 

 [ Edit the !Sand Box will generate a link which will take you directly to editing the [Sand Box](/cars/rom/sand-box), like so: Edit the Sand Box . Other possibilites: - Diff the Sand Box ,
- Lock the Home Page ,
- Get a Full Zip Dump ,
- Page titles containing 'wiki' ,

##  Writing Magic Forms in Wiki Pages 

Magic forms are no longer supported. They have been superceded by <''''?plugin-form?>s (for text searches) and by the Wiki Form Plugin(for files uploads, etc.) ---

[Php Wiki Documentation](/cars/reference/php-wiki-documentation)
