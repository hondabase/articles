---
summary: "Sinopse das Regras de Formatação de Texto. Ênfase: '' para ''itálico'', '''' para negrito, '''''' para ''ambos''. Listas: * para listas de marcas, # para listas numeradas, \"; termo : definição\"..."
applies_to:
  obd: [0, 1, 2]
complexity: advanced
tags:
  - tuning
  - rom
  - sensors
  - reference
  - diagnostics
  - ecu
sources:
  - name: 'pgmfi.org wiki'
    title: 'Text Formatting Rules'
    url: /pgmfi/wiki/library/text-formatting-rules
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Regras de Formatação de Texto

### Sinopse

[Regras de Formatação de Texto](/cars/diagnostics/text-formatting-rules)***Ênfase:*** '____' para ''itálico'', *''''* para ***negrito***, '____'_''''_ para ''__ambos__'' ***Listas:*** * para listas com marcas, # para listas numeradas, "; termo : definição" para listas de definições ***Referências:*** !JuntarPalavrasComMaiúsculas ou utilizar parênteses retos para uma [ligação de página ou URL [!http://cool.wiki.int/. ***Notas de rodapé:*** Utilize [1,[2,[3,... ***Evitar ligações:*** Prefixo com "!": !!NaoCriarHiperligacao, nomeie ligações como [texto (duplicar o "[") ***Diversos*** "!", "!!", "!!!" criam títulos, "%%''''%" cria uma quebra de linha, "-''''-''''-''''-" cria uma linha horizontal ---

### Parágrafos

- Não avance (indent) parágrafos
- As palavras quebram e preenchem conforme necessário
- Utilize linhas em branco como separadores
- Quatro ou mais sinais de menos criam uma linha horizontal
- %%''''% cria uma quebra de linha (também em títulos e listas)

### Listas

- asterisco para o primeiro nível
- * asterisco-asterisco para o segundo nível, etc.
- Utilize * para listas com marcas, # para listas numeradas (misture à vontade)
- ponto e vírgula-termo-dois pontos-definição para listas de definições:

;termo aqui:definição aqui, como na lista - Uma linha para cada item
- Outros espaços em branco iniciais sinalizam texto pré-formatado, alterando a fonte.

### Títulos

- '!' no início de uma linha cria um título pequeno
- '!!' no início de uma linha cria um título médio
- '!!!' no início de uma linha cria um título grande

### Fontes

- Avançar (indenter) com um ou mais espaços para utilizar uma fonte monoespaçada:

 Monospace aqui Isto não está ### Parágrafos com Avanço

- ponto e vírgula-dois pontos -- funciona como >

;: este é um bloco de texto com avanço ### Ênfase

- Utilize aspas simples duplas ('____') para ênfase (geralmente ''itálico'')
- Utilize sublinhados duplos (*''''*) para ênfase forte (geralmente ***negrito***)
- Misture-os à vontade: ***''itálico em negrito''***
- A ''ênfase'' pode ser utilizada ''múltiplas'' vezes numa linha, mas ''não pode'' ultrapassar os limites da linha:

''isto não irá funcionar'' ### Referências

- As hiperligações para outras páginas dentro da Wiki são feitas colocando o nome da página entre parênteses retos: esta é uma ligação de página ou Utilizando Palavras Wiki (preferido)
- As hiperligações para páginas externas são feitas assim: [http://www.wcsb.org/](http://www.wcsb.org/)
- Pode nomear as ligações fornecendo um nome, uma barra (|) e depois a hiperligação ou nome da página: [Página inicial do PhpWiki ](http://web.archive.org/web/20200322071116/http://phpwiki.sourceforge.net/) - a página principal
- Pode suprimir a criação de ligações para referências antigas e URIs precedendo a palavra com um '!', por exemplo, !NotLinkedAsWikiName, !http://not.linked.to/
- Pode criar notas de rodapé utilizando [1, [2, [3, ... como aqui 1. Veja a nota de rodapé correspondente. (Se o [ estiver na primeira coluna, trata-se de uma definição de nota de rodapé em vez de uma referência de nota de rodapé [1.)
- Além disso, a forma antiga de ligar URLs ainda é suportada: preceda as URLs com "http:", "ftp:" ou "mailto:" para criar ligações automaticamente, como em: [http://c2.com/](http://c2.com/)
- URLs que terminam em .png, .gif ou .jpg são incorporadas se estiverem entre parênteses retos, sozinhas: [http://web.archive.org/web/20200322071116/http://phpwiki.sourceforge.net/alpha/themes/default/images/png.png](http://web.archive.org/web/20200322071116/http://phpwiki.sourceforge.net/alpha/themes/default/images/png.png)

### Tabelas

- Tabelas simples estão disponíveis. Uma linha de tabela é introduzida por um ***|*** na primeira coluna. É melhor descrito por exemplo: || *''''_Nome_''''* |v *''''_Custo_''''* |v *''''_Notas_''''* | *''''_Primeiro_''''* | *''''_Último_''''* |> Jeff |< Dairiki |^ Barato |< Não vale a pena |> Marco |< Polo | Mais barato |< Não disponível

;: irá gerar || ***Nome*** |v ***Custo*** |v ***Notas***| ***Primeiro*** | ***Último***|> Jeff |< Dairiki |^ Barato |< Não vale a pena |> Marco |< Polo | Mais barato |< Não disponível ;: Note que múltiplos ***|__'s levam a colunas expandidas (spanned), e __v__'s podem ser utilizados para expandir linhas. Um __>*** gera uma coluna alinhada à direita, ***<*** uma coluna alinhada à esquerda e ***^*** uma coluna centrada (que é o padrão.) ### Linguagem de Marcação HTML

- Não se preocupe
- < e > mantêm-se iguais
- Os caracteres & não irão funcionar
- Se precisar mesmo de utilizar HTML, o administrador do sistema pode ativar esta funcionalidade. Comece cada linha com uma barra (|). Note que esta funcionalidade está desativada por definição.

### Mais detalhes do que deseja saber

Consulte [URLs Mágicos da Php Wiki](/cars/wiring/magic-php-wiki-ur-ls) para obter detalhes pormenorizados sobre como escrever vários tipos de ligações de manutenção da wiki. ---

Notas de rodapé: 1 Ao utilizar [1 uma segunda vez (na primeira coluna), a própria nota de rodapé é ''definida''. Pode referir-se a uma nota de rodapé as vezes que quiser, mas só pode defini-la uma vez na página. Note que o [1 na nota de rodapé aponta de volta para a primeira referência; se existirem múltiplas referências, haverá +'s após o [1 que ligarão para as outras referências. (As referências que surgirem ''depois'' da ''definição'' da nota de rodapé não serão ligadas.) ---

[Documentação do Php Wiki](/cars/reference/php-wiki-documentation)
