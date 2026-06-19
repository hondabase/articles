---
summary: 'O Calendar Plugin pode ser utilizado para gerar um calendário mensal numa página de wiki. É útil para Wikis Pessoais.'
tags: [ecu, reference, sensors, wiring, conversion, diagnostics]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Calendar Plugin'
    url: /pgmfi/wiki/library/calendar-plugin
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Calendar Plugin

O [Calendar Plugin](/cars/wiring/calendar-plugin) pode ser utilizado para gerar um calendário mensal numa página de wiki. É útil para Wikis Pessoais. Datas individuais no calendário hiperligam para páginas de wiki com nomes específicos. Os nomes para as "páginas de dias" são, por predefinição, formados acrescentando a data ao nome da página onde o calendário aparece. ''Esta funcionalidade foi inspirada pelo [Manila](http://manila.userland.com/) e implementada pela primeira vez por Gary Benson. Mais tarde, foi implementada como um [Wiki Plugin](/cars/wiring/wiki-plugin) por Jeff Dairiki.''

## Utilização:

produzirá: ---

## Argumentos do Plugin

### Seleção do Mês

;__year__: Especifica o ano para o calendário. (Predefinição: ano atual.) ;__month__: Especifica o mês para o calendário. (Predefinição: mês atual.) ;__month_offset__: Adicionado ao ''month''. Pode ser utilizado para incluir calendários de vários meses numa única página de wiki.

### Nomes das "Páginas de Dias"

;__date_format__: String de formatação ao estilo Strftime utilizada para gerar os nomes das "páginas de dias." O valor predefinido é '%Y-%m-%d'. ;__prefix__: Preposto à data (formatada de acordo com ''date_format'') para gerar os nomes das "páginas de dias." O valor predefinido é '[pagename:'.

### Aspeto

;__month_format__: String de formatação ao estilo Strftime utilizada para gerar o título do calendário. (Predefinição: '%B, %Y'.) ;__wday_format__: String de formatação ao estilo Strftime utilizada para gerar os nomes dos dias da semana no topo do calendário. ;__start_wday__: Em que dia da semana começa o calendário. Deve ser especificado como um número inteiro no intervalo de zero (domingo) a seis (sábado), inclusive. ---

### Patch para 1.2

Gary Benson escreveu a primeira implementação de calendário para o [Php Wiki](/cars/sensors/php-wiki) 1.2. (Como a versão 1.2 não suporta plugins, utiliza um token ###CALENDAR

### como trigger.) Gary disponibiliza uma captura de ecrã em ![calender.png](http://inauspicious.org/files/screenshots/calender.png), un [patch](http://inauspicious.org/files/phpwiki/phpwiki-1.2.0-calendar.patch) (para a versão 1.2.0), e [calendar.php](http://inauspicious.org/files/phpwiki/calendar.php) (que renderiza uma visualização do ano.) ---

[Documentação do Php Wiki](/cars/reference/php-wiki-documentation)
