---
summary: 'Sobre phpwiki: URLs Um tipo especial de URL está disponível para a criação de links para realizar funções administrativas e outras funções especiais no Php Wiki.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - wiring
  - conversion
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: 'Magic Php Wiki UR Ls'
    url: /pgmfi/wiki/library/magic-php-wiki-ur-ls
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# URLs Mágicas do Php Wiki

# Sobre phpwiki: URLs

Um tipo especial de URL está disponível para a criação de links para realizar funções administrativas e outras funções especiais no [Php Wiki](/cars/sensors/php-wiki). Aqui está uma breve descrição de como funcionam. A sintaxe básica de uma URL phpwiki: é ***phpwiki:__''nome_da_pagina''***?__''argumentos_de_consulta'' Se o ''nome_da_pagina'' for omitido, o padrão será a página atual. Os ''argumentos_de_consulta'' devem ser um conjunto de parâmetros no formato padrão HTTP GET. O parâmetro "action=''x''" quase sempre deve ser fornecido. Pode ser um de ***browse***, ***info***, ***diff***, ***search***, ***edit***, ***zip***, ***dumpserial***, ***loadserial***, ***remove***, ***lock***, ***unlock***, ***login***, ***logout***, ***setprefs*** ou ***save***. A ação padrão é ***browse***. Algumas das ações aceitam outros parâmetros. ;__info__: Aceita ***showpagesource***. ;__search__: Aceita ***searchterm*** e ***searchtype***. ;__edit__: Aceita ***version***. ;__remove__: Aceita ***verify***. ;__save__: Aceita ***editversion***, ***minor_edit*** e ***content***. ;__setprefs__: Aceita ***edit_area_width***, ***edit_area_height***. ## Escrever Links Mágicos em Páginas Wiki

Um link mágico parece-se com: ***[*** ''texto'' O "''texto'' __|__" é opcional, mas geralmente recomendado. Se fornecido, definirá o rótulo do link. A ''phpwiki-url'' é uma URL ***phpwiki:*** conforme descrito acima. ### Alguns exemplos

 [ Edit the !Sand Box irá gerar um link que o levará diretamente para a edição do [Sand Box](/cars/rom/sand-box), da seguinte forma: Edit the Sand Box . Outras possibilidades: - Diff the Sand Box ,
- Lock the Home Page ,
- Get a Full Zip Dump ,
- Títulos de páginas contendo 'wiki' ,

## Escrever Formulários Mágicos em Páginas Wiki

Formulários mágicos já não são suportados. Foram substituídos por <''''?plugin-form?>s (para pesquisas de texto) e pelo Wiki Form Plugin (para envio de ficheiros, etc.) ---

[Documentação do Php Wiki](/cars/reference/php-wiki-documentation)
