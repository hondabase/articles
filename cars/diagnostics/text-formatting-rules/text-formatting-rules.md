---
summary: "Synopsis Text Formatting RulesEmphasis: '' for ''italics'', '''' for bold, '''''' for ''both'' Lists: for bullet lists, for numbered lists, \"; term : definition\"..."
tags: [tuning, rom, sensors, reference, diagnostics, ecu]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Text Formatting Rules'
    url: /pgmfi/wiki/library/text-formatting-rules
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Text Formatting Rules

###  Synopsis 

[Text Formatting Rules](/cars/diagnostics/text-formatting-rules)***Emphasis:*** '____' for ''italics'', *''''* for ***bold***, '____'_''''_ for ''__both__'' ***Lists:*** * for bullet lists, # for numbered lists, "; term : definition" for definition lists ***References:*** !JoinCapitalizedWords or use square brackets for a [page link or URL [!http://cool.wiki.int/. ***Footnotes:*** Use [1,[2,[3,... ***Preventing linking*** Prefix with "!": !!DoNotHyperlink, name links like [text  (double up on the "[") ***Misc*** "!", "!!", "!!!" make headings, "%%''''%" makes a linebreak, "-''''-''''-''''-" makes a horizontal rule ---

###  Paragraphs 

- Don't indent paragraphs
- Words wrap and fill as needed
- Use blank lines as separators
- Four or more minus signs make a horizontal rule
- %%''''% makes a linebreak (in headings and lists too)

###  Lists 

- asterisk for first level
- * asterisk-asterisk for second level, etc.
- Use * for bullet lists, # for numbered lists (mix at will)
- semicolon-term-colon-definition for definition lists:

;term here:definition here, as in the  list - One line for each item
- Other leading whitespace signals preformatted text, changes font.

###  Headings 

- '!' at the start of a line makes a small heading
- '!!' at the start of a line makes a medium heading
- '!!!' at the start of a line makes a large heading

###  Fonts 

- Indent with one or more spaces to use a monospace font:

 This is in monospace This is not ###  Indented Paragraphs 

- semicolon-colon -- works like >

;: this is an indented block of text ###  Emphasis 

- Use doubled single-quotes ('____') for emphasis (usually ''italics'')
- Use doubled underscores (*''''*) for strong emphasis (usually ***bold***)
- Mix them at will: ***''bold italics''***
- ''Emphasis'' can be used ''multiple'' times within a line, but ''cannot'' cross line boundaries:

''this will not work'' ###  References 

- Hyperlinks to other pages within the Wiki are made by placing the page name in square brackets: this is a page link or Using Wiki Words (preferred)
- Hyperlinks to external pages are done like this: [http://www.wcsb.org/](http://www.wcsb.org/)
- You can name the links by providing a name, a bar (|) and then the hyperlink or pagename: [PhpWiki home page ](http://web.archive.org/web/20200322071116/http://phpwiki.sourceforge.net/) - the front page
- You can suppress linking to old-style references and URIs by preceding the word with a '!', e.g. !NotLinkedAsWikiName, !http://not.linked.to/
- You can create footnotes by using [1, [2, [3, ... like this here 1. See footnote for counterpart. (If the [ is in the first column, it is a footnote ''definition'' rather than a footnote ''reference'' [1.)
- Also, the old way of linking URL's is still supported: precede URLs with "http:", "ftp:" or "mailto:" to create links automatically as in: [http://c2.com/](http://c2.com/)
- URLs ending with .png, .gif, or .jpg are inlined if in square brackets, by themselves: [http://web.archive.org/web/20200322071116/http://phpwiki.sourceforge.net/alpha/themes/default/images/png.png](http://web.archive.org/web/20200322071116/http://phpwiki.sourceforge.net/alpha/themes/default/images/png.png)

###  Tables 

- Simple tables are available. A table row is introduced by a ***|*** in the first column. It is best described by example: || *''''_Name_''''* |v *''''_Cost_''''* |v *''''_Notes_''''* | *''''_First_''''* | *''''_Last_''''* |> Jeff |< Dairiki |^ Cheap |< Not worth it |> Marco |< Polo | Cheaper |< Not available

;: will generate || ***Name*** |v ***Cost*** |v ***Notes***| ***First*** | ***Last***|> Jeff |< Dairiki |^ Cheap |< Not worth it |> Marco |< Polo | Cheaper |< Not available ;: Note that multiple ***|__'s lead to spanned columns, and __v__'s can be used to span rows. A __>*** generates a right justified column, ***<*** a left justified column and ***^*** a centered column (which is the default.) ###  HTML Mark-Up Language 

- Don't bother
- < and > are themselves
- The & characters will not work
- If you really must use HTML, your system administrator can enable this feature. Start `each` line with a bar (|). Note that this feature is disabled by default.

###  More detail than you want to know 

See [Magic Php Wiki URLs](/cars/wiring/magic-php-wiki-ur-ls) for gory details on how to write various kind of wiki maintainance links. ---

Footnotes: 1 By using [1 a second time (in the first column) the footnote itself is ''defined''. You may refer to a footnote as many times as you want, but you may only define it once on the page. Note the the [1 in the footnote links back to the first reference, if there are multiple references there will be +'s after the [1 which will link to the other references. (References which come ''after'' the footnote ''definition'' will not be linked to.) ---

[Php Wiki Documentation](/cars/reference/php-wiki-documentation)
