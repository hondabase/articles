---
summary: "Nota: A maioria das ações nesta página requer privilégios administrativos. Não funcionarão a menos que tenha definido um nome de utilizador e palavra-passe de administrador no ficheiro de configuração do Php Wiki."
applies_to:
  obd: [0, 1, 2]
  brand: Honda
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
    title: 'Php Wiki Administration'
    url: /pgmfi/wiki/library/php-wiki-administration
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Administração do Php Wiki

***Nota***: A maioria das ações nesta página requer privilégios administrativos. Não funcionarão a menos que tenha definido um nome de utilizador e palavra-passe de administrador no ficheiro de configuração do [Php Wiki](/cars/sensors/php-wiki). ---

## Limpeza

Uma Wiki [Sand Box](/cars/rom/sand-box) é muito fácil de limpar. Aqui pode restaurá-la para o estado original carregando o padrão do pgsrc: Rake the Sand Box. ---

## Criar Instantâneos ou Cópias de Segurança (Backups)

### Ficheiros ZIP da base de dados

Estes links levam a ficheiros zip, gerados no momento (on the fly), que contêm todas as páginas da sua Wiki. O ficheiro zip será descarregado para o seu computador local. Este ***Instantâneo ZIP (ZIP Snapshot)*** contém apenas as versões mais recentes de cada página, enquanto este ***Dump ZIP*** contém todas as versões arquivadas. (Se o [Php Wiki](/cars/sensors/php-wiki) estiver configurado para o permitir,) qualquer pessoa pode descarregar um ficheiro zip. Se o seu php tiver suporte ''zlib'', os ficheiros no arquivo serão comprimidos; caso contrário, serão apenas armazenados. ### Dump para diretório

Aqui pode exportar (dump) páginas da sua Wiki para um diretório à sua escolha. Wiki Form action=dumpserial?> A versão mais recente de cada página será gravada no diretório, uma página por ficheiro. O seu servidor tem de ter permissões de escrita no diretório! ---

## Restaurar

Se exportou um conjunto de páginas do [Php Wiki](/cars/sensors/php-wiki), pode recarregá-las aqui. Note que as páginas na sua base de dados serão substituídas; assim, se exportou a sua Página Inicial (Home Page), ao carregá-la a partir deste formulário, ela irá substituir a que está atualmente na sua base de dados. Se quiser ser seletivo, basta apagar do diretório (ou do ficheiro zip) as páginas que não deseja carregar. ### Carregar Ficheiro (Upload File)

Aqui pode carregar (upload) arquivos ZIP ou ficheiros individuais a partir da sua máquina (cliente). Wiki Form action=upload?> ### Carregar Ficheiro (Load File)

Aqui pode carregar arquivos ZIP, ficheiros individuais ou diretórios inteiros. O ficheiro ou diretório tem de ser local no servidor http. Também pode usar este formulário para carregar a partir de um URL http: ou ftp:. Wiki Form action=loadfile?> ---

## Formato dos ficheiros

Atualmente as páginas são armazenadas, uma por ficheiro, como mensagens de e-mail MIME (RFC:2045) (RFC:822). O content-type ''application/x-phpwiki'' é utilizado, e os metadados da página são codificados nos parâmetros do content-type. (Se o ficheiro contiver várias versões de uma página, terá o tipo ''multipart/mixed'' e conterá várias subpartes, cada uma com o tipo ''application/x-phpwiki''.) O corpo da mensagem contém o texto da página. ### Formatos Antigos

***Ficheiros Serializados (Serialized Files)***O comando de exportação para diretório costumava exportar as páginas como strings php ''serialized()''. Para os humanos, isto tornava os ficheiros muito difíceis de ler e quase impossíveis de editar. ***Ficheiros de Texto Simples (Plain Files)***Antes disso, o texto da página era simplesmente exportado para um ficheiro — o que significa que todos os metadados da página eram perdidos. Note que, ao carregar ''plain files'' (ficheiros simples), o nome da página é deduzido a partir do nome do ficheiro. As funções de envio (upload) e carregamento reconhecerão automaticamente cada um destes três tipos de ficheiros e tratarão os mesmos em conformidade. ---

## Exportar páginas como XHTML

Wiki Form action=dumphtml?> Isto irá gerar um diretório de páginas estáticas adequadas para distribuição em disco onde não esteja disponível um servidor web. ---

[Documentação do Php Wiki](/cars/reference/php-wiki-documentation)
