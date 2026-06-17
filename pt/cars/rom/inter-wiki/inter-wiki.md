---
summary: 'Esta wiki suporta links Inter Wiki num estilo copiado do Use Mod: wiki. Links para páginas noutras wikis podem ser feitos sem ter de saber ou digitar o...'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - tuning
  - rom
  - sensors
  - reference
sources:
  - name: 'pgmfi.org wiki'
    title: 'Inter Wiki'
    url: /pgmfi/wiki/library/inter-wiki
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Inter Wiki

Esta wiki suporta links [Inter Wiki](/cars/rom/inter-wiki) num estilo copiado do Use Mod: wiki. Links para páginas noutras wikis podem ser feitos sem ter de saber ou digitar os URLs completos, por exemplo: Meat Ball:InterWiki ligará para a página chamada "~InterWiki" na Meatball wiki. O mapa ~InterWiki é retirado do bloco no [Inter Wiki Map](/cars/wiring/inter-wiki-map), mas essa página deve estar bloqueada para que funcione. Isto nega a um potencial hacker a capacidade de alterar maliciosamente cada link ~InterWiki para apontar para algum URL malicioso. Se nenhum mapa for encontrado no [Inter Wiki Map](/cars/wiring/inter-wiki-map) (ou se a página não estiver bloqueada), a [Php Wiki](/cars/sensors/php-wiki) recorrerá ao uso do ficheiro lib/interwiki.map na sua distribuição phpwiki. O ficheiro de mapa ~InterWiki em uso na [Php Wiki](/cars/sensors/php-wiki): pode ser visualizado em [http://web.archive.org/web/20080516074939/http://web.archive.org/web/20080516074939/http://phpwiki.sf.net/interwiki.map](http://web.archive.org/web/20080516074939/http://web.archive.org/web/20080516074939/http://phpwiki.sf.net/interwiki.map). O ficheiro de mapa é atualizado manualmente. Baseia-se e é periodicamente sincronizado com o [UseMod's InterMap](http://web.archive.org/web/20260125023728/http://usemod.com/intermap.txt) mas não é totalmente idêntico. Uma diferença notável em relação ao Use Mod: é que a [Php Wiki](/cars/sensors/php-wiki) suporta '%s' nos URLs do mapa — veja a entrada de RFC para um exemplo de como isto funciona. Nem todas as entradas no [Inter Wiki Map](/cars/wiring/inter-wiki-map) são wikis reais. Por exemplo, estes são apenas websites normais: Dictionary:fungible, Jargon File:Alderson loop, IMDB:Roman Holiday, RFC:2822, e ISBN:020171499X. O monónimo "Category" é uma entrada especial que permite ligar uma página wiki a uma página de Categoria sem criar uma referência reversa. Assim, Category:Category liga à página Categoria Categoria, mas esta página não aparecerá na listagem de links reversos da Categoria Categoria. O termo "InterWiki" também se refere a um conceito mais amplo. Veja [Php Wiki](/cars/sensors/php-wiki):InterWikiSearch para mais links. ---

[Php Wiki Documentation](/cars/reference/php-wiki-documentation)
