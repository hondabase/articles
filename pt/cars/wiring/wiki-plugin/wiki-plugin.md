---
summary: 'As modificações mais recentes incluem suporte para !WikiPlugins. Os Wiki Plugins permitem adicionar facilmente novos tipos de conteúdo dinâmico (assim como outras funcionalidades) a páginas wiki dentro da Php Wiki.'
applies_to:
  obd: [0, 1, 2]
  brand: Acura
complexity: advanced
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
    title: 'Wiki Plugin'
    url: /pgmfi/wiki/library/wiki-plugin
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Wiki Plugin

As modificações mais recentes incluem suporte para !WikiPlugins.

### Os [Wiki Plugins](/cars/wiring/wiki-plugin) permitem adicionar facilmente novos tipos de conteúdo dinâmico (assim como outras funcionalidades) a páginas wiki dentro da [Php Wiki](/cars/sensors/php-wiki). Nesta própria wiki, as páginas de [Alterações Recentes](/cars/rom/recent-changes), [Retro-ligações (Back Links)](/cars/sensors/back-links), [Páginas Semelhantes](/cars/sensors/like-pages) e [Informação de Depuração (Debug Info)](/cars/electronics/debug-info) são todas implementadas usando plugins.

Espero que as páginas de resultados de pesquisa, bem como grande parte da [Administração da Php Wiki](/cars/diagnostics/php-wiki-administration), também sejam implementadas através de plugins em breve. (Acho que os horríveis [URLs Mágicos da Php Wiki](/cars/wiring/magic-php-wiki-ur-ls) também podem ser substituídos por plugins.) ### Exemplo

Atualmente, invoca-se um plugin colocando algo como: ''''plugin !BackLinks?> numa página wiki normal. Esse exemplo em particular produz uma lista de páginas que apontam para a página atual. Aqui está: Back Links?> (Isto é excelente para páginas de Categoria e de Tópico. Pode usar isto para obter uma listagem automática em linha das páginas na Categoria ou Tópico.) ### Detalhes

(Tudo isto está sujeito a alterações.) Os plugins podem receber certos argumentos nomeados (a maioria recebe). Os valores destes argumentos podem ser determinados de quatro formas diferentes. Por ordem de precedência: # A invocação do plugin pode especificar o valor para um argumento, da seguinte forma: ;;: ''''plugin !BackLinks page=!OtherPage ?> # O argumento pode ser especificado através de um argumento de consulta (query argument) HTTP. Isto não acontece (não é permitido) a menos que o argumento seja mencionado na invocação do plugin: ;;: ''''plugin !BackLinks page ?> # Valores por omissão (default) especificados na invocação do plugin: ;;: ''''plugin !BackLinks page||=!OtherPage ?> # O plugin deve fornecer valores por omissão para `cada` argumento que utiliza. (O plugin [Retro-ligações (Back Links)](/cars/sensors/back-links) utiliza a página atual como o valor por omissão para o argumento ''page''). ### Plugins Existentes

- [Retro-ligações (Back Links)](/cars/sensors/back-links)
- [Plugin de Calendário (Calendar Plugin)](/cars/wiring/calendar-plugin)
- [Informação de Depuração (Debug Info)](/cars/electronics/debug-info)
- [Pesquisa de Texto Integral (Full Text Search)](/cars/electronics/full-text-search)
- Include Page
- [Páginas Semelhantes (Like Pages)](/cars/sensors/like-pages)
- [Mais Populares (Most Popular)](/cars/reference/most-popular)
- [Histórico da Página (Page History)](/cars/electronics/page-history)
- [Alterações Recentes (Recent Changes)](/cars/rom/recent-changes)
- text2png
- [Pesquisa por Título (Title Search)](/cars/electronics/title-search)
- View Source
- walkabout

### Mais Ideias para Plugins

- Integrar formulário de Pesquisa com entradas de mapa individuais da [Inter Wiki](/cars/rom/inter-wiki)

 ex. Pesquisar no Website da Php por:[[]] (Pesquisar) - Páginas Desejadas, [Páginas Órfãs (Orphaned Pages)](/cars/sensors/orphaned-pages), outros esquemas variados de indexação.
- Diff, [Histórico da Página (Page History)](/cars/electronics/page-history)
- Plugin de redirecionamento -- ''''plugin Redirect target=!OtherPage ?>
- Inserir conteúdo de notícias XML/RSS/RDF de location=xxx onde location é um parâmetro para o plugin, talvez incluindo algum controlo de formatação do resultado gerado.

---

Páginas nesta categoria: Back Links page=pagename noheader=1?> - [Pesquisa de Texto Integral (Full Text Search)](/cars/electronics/full-text-search): [Encontrar Página (Find Page)](/cars/diagnostics/find-page)
- [Pesquisa por Título (Title Search)](/cars/electronics/title-search): [Páginas Semelhantes (Like Pages)](/cars/sensors/like-pages) (match_head, match_tail).

---

[Documentação da Php Wiki (Php Wiki Documentation)](/cars/reference/php-wiki-documentation)
