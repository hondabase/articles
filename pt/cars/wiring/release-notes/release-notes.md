---
summary: 'Hacks de Jeff. Nova API de base de dados. Consulta lib/WikiDB.php e lib/WikiDB/backend.php para a maior parte da documentação sobre isto.'
applies_to:
  obd: [0, 1, 2]
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
    title: 'Release Notes'
    url: /pgmfi/wiki/library/release-notes
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Release Notes

Hacks de Jeff.

- Nova base de dados [API](/cars/diagnostics/api). Consulta lib/WikiDB.php e lib/WikiDB/backend.php para a maior parte da documentação sobre isto. A nova base de dados pode guardar várias versões arquivadas de `cada` página. Está também em vigor um mecanismo para expurgar revisões arquivadas. Consulta a configuração $!ExpireParams no index.php e lib/!ArchiveCleaner.php para mais detalhes. Neste momento, os backends DBA, MySQL e Postgres estão funcionais. O backend DBA beneficiaria de alguma otimização de desempenho. Toda a [API](/cars/diagnostics/api) ainda está sujeita a algumas alterações à medida que descubro uma forma limpa de fornecer uma variedade de métodos (nem todos previstos) de indexação e pesquisa na wiki.
- Nova arquitetura de [Wiki Plugin](/cars/wiring/wiki-plugin).
- Novo motor de templates. Isto precisa de ser mais documentado, mas, por agora, consulta lib/Template.php. Pensando melhor, não o faças (lib/Template.php ainda precisa desesperadamente de refatoração). O avanço básico é que as funções ob_*() do PHP4 podem ser usadas para capturar a saída de código PHP processado por eval(). Isto permite que os templates sejam código PHP...
- Botão de pré-visualização de edição na página de edição. Agora podes ver como ficam as tuas edições antes de as submeteres.
- Folhas de estilo reformuladas. Ainda preciso de limpar isto um pouco mais. Agradecia comentários e relatórios de bugs sobre as mesmas. Até agora apenas testei as novas folhas de estilo com o Netscape 4.77 e o Mozilla 0.9.3 (ambos a correr em Linux).
- Sintaxe expandida para pesquisa de texto, agora pesquisas como "wiki ou web -page" (ou "(wiki ou web) e não page") farão mais ou menos aquilo que parece que farão.
- Questões de Segurança: A [Php Wiki](/cars/sensors/php-wiki) agora funcionará com o register_globals do PHP desativado.

Ramo de desenvolvimento [Php Wiki](/cars/sensors/php-wiki) 1.3.x. - Nomes de páginas em PATH_INFO.
- Envio de ficheiros (Uploads): consulta [Php Wiki Administration](/cars/diagnostics/php-wiki-administration).
- [User Preferences](/cars/reference/user-preferences) (Preferências do Utilizador).
- [Magic Php Wiki URLs](/cars/wiring/magic-php-wiki-ur-ls) feios para links administrativos.

A [Php Wiki](/cars/sensors/php-wiki) 1.2 é um enorme avanço em relação à versão 1.0: - O suporte de base de dados para MySQL, PostgreSQL, mSQL, flat file (ficheiro de texto plano) e a nova biblioteca dba_ no PHP4 está incluído.
- Internacionalização: suporte para diferentes idiomas, até ao nível do código-fonte, está incluído. Alemão, espanhol, sueco e holandês são atualmente distribuídos com a [Php Wiki](/cars/sensors/php-wiki). Existe uma arquitetura implementada para adicionar facilmente mais idiomas.
- Novos esquemas de ligação usando parênteses retos em adição ao antigo estilo !BumpyText.
- As funcionalidades de administração incluem bloqueio de páginas, exportação da Wiki para um ficheiro zip, e eliminação de páginas.
- Uma página [Most Popular](/cars/reference/most-popular) (Mais Populares) que mostra as páginas com mais acessos.
- Conformidade total com HTML.
- Links no fundo das páginas descrevendo relações como links de entrada de outras páginas e os seus acessos, links de saída e os seus acessos, e as páginas mais populares nas proximidades.
- Diferenças (diffs) de página coloridas entre a versão atual e a anterior.
- Uma página de informações para ver os metadados da página.
- Muito mais capacidade de personalização para o administrador.
- Um sistema de templates para separar o HTML da página do código PHP.
- Novas construções de marcação para **, *, , e mais.***
- Marcação sem tabelas para substituir a marcação mais antiga (ambas continuam a ser suportadas).

---

A [Php Wiki](/cars/sensors/php-wiki) 1.1.9 inclui páginas em espanhol, uma implementação completa para PostgreSQL, inúmeras correções de bugs e muito mais. Consulta o ficheiro HISTORY para mais informações: [http://web.archive.org/web/20080516035040/http://web.archive.org/web/20080516035040/http://phpwiki.sourceforge.net/phpwiki/HISTORY](http://web.archive.org/web/20080516035040/http://web.archive.org/web/20080516035040/http://phpwiki.sourceforge.net/phpwiki/HISTORY)---

A [Php Wiki](/cars/sensors/php-wiki) 1.1.6 é uma revisão importante da [Php Wiki](/cars/sensors/php-wiki). A capacidade de ter temas (através de um sistema de templates fácil de editar) foi adicionada; o esquema para MySQL foi completamente remodelado, dividindo os detalhes da página em colunas (por uma questão de eficiência, concordámos em não colocar referências numa tabela separada, pelo que não está completamente normalizado. "Não deixes que o ótimo seja inimigo do bom"). O suporte para PostgreSQL foi adicionado e a linguagem de marcação está a evoluir, permitindo agora tags # ##  

## ###  

### ####  

e ***uma nova forma de colocar texto a negrito***, e claro, o novo esquema de links. Existe uma nova funcionalidade em todas as páginas chamada ''more info'' que te dá uma vista detalhada de baixo nível de uma página, o que é provavelmente mais útil para depuração do que para qualquer outra coisa. À medida que avançamos para um lançamento 1.2, adicionaremos registo de logs, as dez páginas mais ativas e outras novas funcionalidades com o novo esquema de base de dados (e sim, estas funcionalidades também farão parte da versão DBM). Também quero adicionar suporte para mSQL e testá-lo sob Zend, o novo PHP4. Abaixo estão as notas de lançamento para a versão 1.03, o último lançamento da série 1.0 da [Php Wiki](/cars/sensors/php-wiki). --Steve Wainstead, [email protected]---

A [Php Wiki](/cars/sensors/php-wiki) foi escrita porque tenho muito interesse em [Wiki Wiki Webs](/cars/rom/wiki-wiki-web), e não usava PHP desde a versão 2.0. Queria ver como tinha evoluído. A versão 1.0 é um clone quase perfeito do Portland Pattern Repository, [http://c2.com/cgi-bin/wiki?WikiWikiWeb](http://c2.com/cgi-bin/wiki?WikiWikiWeb). Na verdade, estava a usar o script Wiki que se pode descarregar de lá como modelo; essa Wiki carece de várias funcionalidades que o PPR tem, como Edit Copy. Portanto, na verdade a [Php Wiki](/cars/sensors/php-wiki) é uma espécie de híbrido do PPR e da Wiki genérica que se pode obter a partir de lá (que é escrita em Perl). A única ressalva da [Php Wiki](/cars/sensors/php-wiki) é a permissão de HTML se a linha for precedida por uma barra vertical (ou pipe, como costumo dizer). (Isso é um '|'). Foi muito simples de adicionar, e a ideia surgiu de uma publicação algures no PPR sobre como a AT&T tinha um clone interno de Wiki e usava a mesma técnica. A capacidade de incorporar HTML está desativada por padrão por razões de segurança. A versão 1.01 inclui um patch que corrige um pequeno erro com a renderização de linhas ---

 de linhas. Obrigado a Gerry Barksdale. Consulta o ficheiro HISTORY para um resumo de todo o processo de desenvolvimento, se esse tipo de coisa realmente te interessar :-) --SteveWainstead ---

[Php Wiki Documentation](/cars/reference/php-wiki-documentation)
