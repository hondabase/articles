---
summary: 'Referência para a API JavaScript legada do editor de ROM Crome, utilizada por scripts, manipuladores de ROM (ROM handlers) e plug-ins.'
tags: [tuning, rom, software]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Crome Script'
    url: /pgmfi/wiki/library/crome-script
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# API de scripting JavaScript do Crome

O Crome expõe uma API JavaScript para estender o editor de ROM OBD1 legado com scripts, manipuladores de ROM (ROM handlers) e plug-ins. Esta referência preserva a API documentada pela comunidade original do Crome.

> [!WARNING]
> Trabalhe numa cópia da ROM e verifique todos os resultados antes de a instalar numa ECU. O comportamento da API pode diferir entre versões do Crome, e um script incorreto pode corromper tabelas, escalares ou checksums.

## Aceder aos objetos da API

Dentro de um script Crome, os membros do objeto padrão `window` podem ser chamados diretamente ou através de `window`:

```javascript
refresh();
window.refresh();
rom.byteAt(0x7FFF);
window.rom.byteAt(0x7FFF);
```

Um plug-in do Crome baseado em HTML acede aos mesmos objetos através de `window.external`:

```javascript
window.external.refresh();
window.external.rom.byteAt(0x7FFF);
```

A documentação arquivada descreve três objetos principais:

| Objeto | Finalidade |
| :--- | :--- |
| `window` | Diálogos, registo de plug-ins, comandos externos e atualização do ecrã |
| `window.rom` / `rom` | Ler e modificar a ROM ativa, tabelas, escalares e flags de funcionalidades |
| `window.files` / `files` | Abrir, guardar, ler e gravar ficheiros |

## Funções da janela (Window)

| Função | Finalidade documentada |
| :--- | :--- |
| `addRomHandler(romtype, author, jscmd)` | Registar um manipulador para um tipo de ROM |
| `addPlugin(author, mnucaption, jscmd, category)` | Adicionar uma entrada ao menu de plug-ins do Crome |
| `alert(msg)` | Exibir uma mensagem com um botão OK |
| `confirm(msg)` | Exibir uma confirmação de Sim/Não; devolve false ou true |
| `DecToHex(dec)` | Converter um valor decimal numa string hexadecimal |
| `exal(cipherstring)` | Avaliar uma string JavaScript codificada |
| `GetFilePath(filename)` | Devolver a parte do caminho de um nome de ficheiro |
| `GetFileName(filename)` | Devolver a parte do nome de um nome de ficheiro |
| `HiByte(w)` | Devolver o byte alto (high byte) de uma word |
| `LoByte(w)` | Devolver o byte baixo (low byte) de uma word |
| `input(msg, options, values)` | Exibir um diálogo de seleção de entrada |
| `include(filename)` | Incluir outro ficheiro de script |
| `prompt(caption, msg, default)` | Solicitar uma resposta do utilizador |
| `select(prompt, selection)` | Devolver o índice do item selecionado, ou `-1` quando cancelado |
| `shell(filename, params, windowstate)` | Iniciar uma aplicação externa |
| `shelld(doscmd)` | Executar um comando DOS e devolver o seu resultado |
| `shellw(filename, params, windowstate)` | Iniciar uma aplicação e aguardar que ela feche |
| `showBrowser(url, width, height)` | Abrir o navegador integrado do Crome |
| `refresh()` | Atualizar o editor após um script alterar a ROM ativa |

> [!NOTE]
> A assinatura arquivada declara `prompt()` como devolvendo um booleano, enquanto a sua descrição diz que devolve a resposta do utilizador ou uma string vazia. Verifique o comportamento na versão do Crome que está a usar como alvo.

Exemplos da API arquivada:

```javascript
addRomHandler(rtP30, 'Author', '_handle_p30_rom()');
addPlugin('Author', 'Test Plugin', '_run_test_plugin()', 0);
shell('notepad.exe', 'C:\\autoexec.bat', 0);
showBrowser('my_html_plugin.html', 400, 250);
```

Uma referência rápida mais antiga também lista `_rom_write(start, values, count)` e `_rom_fill(fromAddr, toAddr, byteFill)`, além de uma propriedade `rom.type` com exemplos como `rp30`, `rp72`, `rp28` e `rpCustom`. A sua disponibilidade depende da versão.

## Objeto ROM

### Acesso a bytes, words e tabelas

| Membro | Acesso | Finalidade documentada |
| :--- | :---: | :--- |
| `byteAt(addr)` | Leitura/Gravação | Obter ou definir um byte num endereço da ROM |
| `wordAt(addr)` | Leitura/Gravação | Obter ou definir uma word little-endian num endereço da ROM |
| `working_table` | Leitura/Gravação | Selecionar a tabela de combustível ou ignição ativa |
| `tableByte(col, row)` | Leitura/Gravação | Obter ou definir um byte bruto na tabela ativa |
| `tableValue(col, row)` | Leitura/Gravação | Obter ou definir o valor interpretado da tabela |
| `tableWidth` | Apenas leitura | Largura da tabela ativa |
| `tableHeight` | Apenas leitura | Altura da tabela ativa |
| `mapScalar(table, col)` | Leitura/Gravação | Obter ou definir um escalar de MAP em milibares |
| `revScalar(table, row)` | Leitura/Gravação | Obter ou definir um escalar de RPM |

`working_table` utiliza estes valores documentados:

| Valor | Tabela |
| :---: | :--- |
| `0` | Combustível baixo (Low fuel) |
| `1` | Combustível alto (High fuel) |
| `2` | Ignição baixa (Low ignition) |
| `3` | Ignição alta (High ignition) |

```javascript
rom.working_table = 2;
var ignitionByte = rom.tableByte(0, 5);

var lastByte = rom.byteAt(0x7FFF);
rom.byteAt(0x7FFF) = 0xFF;
```

`wordAt()` tem em conta o armazenamento little-endian. A fonte indica que os bytes armazenados como `[0xAB][0xCD]` são devolvidos como `0xCDAB`.

### Metadados da ROM e flags de funcionalidades

| Membro | Acesso | Significado documentado |
| :--- | :---: | :--- |
| `addressOf(name)` | Leitura/Gravação | Endereço armazenado num registo especial nomeado |
| `addressIn(index)` | Leitura/Gravação | Endereço armazenado no índice do registo especial de 0 a 63 |
| `base` | Leitura/Gravação | ROM base utilizada para localizações de endereços padrão |
| `title` | Leitura/Gravação | Texto exibido na barra de estado do Crome |
| `filename` | Apenas leitura | Nome completo do ficheiro da ROM ativa |
| `OBDMode` | Leitura/Gravação | Modo de fórmula: 0 OBD0, 1 OBD1, 2 OBD2, 3 desconhecido |
| `notes` | Leitura/Gravação | Notas anexadas à ROM ativa |
| `gup()` | Função | Criar um ponto de anulação de grupo (group undo point) em torno de uma operação de múltiplas alterações |

As flags de funcionalidades estão documentadas como propriedades de byte de leitura/gravação:

| Propriedade | Valores |
| :--- | :--- |
| `hasLaunchControl` | `0` desligado, `1` ligado |
| `hasFullThrottleShift` | `0` desligado, `1` ligado |
| `hasBoost` | `0` nenhum, `1` boost com MAP original (stock), `2` boost com 3-bar, `3` personalizado |
| `hasFinalMultiplier` | `0` desligado, `1` ligado |
| `hasShiftLight` | `0` desligado, `1` ligado |
| `hasIAB` | `0` desligado, `1` ligado |

Utilize `gup()` antes e depois de um grupo de alterações para que o Crome possa anulá-las como uma única ação:

```javascript
rom.gup();
for (var i = 0; i <= 0x7FFF; i++) {
 rom.byteAt(i) = LoByte(i);
}
rom.gup();
refresh();
```

## Objeto Files

| Membro | Finalidade documentada |
| :--- | :--- |
| `showSave(filter, filterindex)` | Mostrar um diálogo de gravação e devolver o nome do ficheiro selecionado |
| `showOpen(filter, filterindex)` | Mostrar um diálogo de abertura e devolver o nome do ficheiro selecionado |
| `exists(filename)` | Devolver true quando um ficheiro existe |
| `getFile(filename)` | Ler um ficheiro de texto |
| `putFile(filename, data)` | Gravar dados num ficheiro |
| `browseFolder` | Mostrar um explorador de pastas e devolver o caminho selecionado |

Os diálogos de abertura, gravação e de pasta cancelados estão documentados como devolvendo uma string vazia.

## Nomes dos registos especiais

Utilize estes nomes com `rom.addressOf('NAME')` ou o seu índice numérico com `rom.addressIn(index)`.

| Nome | Índice | Finalidade documentada |
| :--- | :---: | :--- |
| `CHECKSUM` | 0 | Endereço de correção do checksum |
| `LOW_MAP_SCALAR` | 1 | Endereço do escalar de MAP baixo |
| `HIGH_MAP_SCALAR` | 2 | Endereço do escalar de MAP alto |
| `LOW_REV_SCALAR` | 3 | Endereço do escalar de RPM baixo |
| `HIGH_REV_SCALAR` | 4 | Endereço do escalar de RPM alto |
| `LOW_FUEL` | 5 | Endereço da tabela de combustível baixa |
| `HIGH_FUEL` | 6 | Endereço da tabela de combustível alta |
| `LOW_IGNITION` | 7 | Endereço da tabela de ignição baixa |
| `HIGH_IGNITION` | 8 | Endereço da tabela de ignição alta |
| `NFO_LOW_TABLE` | 9 | Dimensões da tabela baixa; o byte alto é a altura, o byte baixo é a largura |
| `NFO_HIGH_TABLE` | 10 | Dimensões da tabela alta; o byte alto é a altura, o byte baixo é a largura |
| `REVCUT1` | 11 | Endereço do valor do primeiro corte de rotação (rev-cut) |
| `REVRES1` | 12 | Endereço do valor de retoma do primeiro corte de rotação (rev-resume) |
| `REVCUT2` | 13 | Endereço do valor do segundo corte de rotação (rev-cut) |
| `REVRES2` | 14 | Endereço do valor de retoma do segundo corte de rotação (rev-resume) |
| `VTEC_TABLE` | 15 | Endereço da tabela VTEC |
| `NFO_VTEC_TABLE` | 16 | Informações da tabela VTEC |
| `VTEC` | 17 | Endereço do byte de configuração do VTEC |
| `IDLE` | 25 | Endereço do valor de ralenti (idle) |
| `KNOCK` | 26 | Endereço do byte de configuração de detonação (knock) |
| `ELD` | 27 | Endereço do byte de configuração do ELD |
| `BARO` | 29 | Endereço do byte de configuração da pressão barométrica |
| `VTECVSS` | 30 | Endereço do byte de configuração da verificação de VSS do VTEC |
| `VTECCOOL` | 31 | Endereço do byte de configuração da verificação de temperatura da água do VTEC |
| `DEBUGMODE` | 32 | Endereço do byte de configuração do modo de depuração (debug) |
| `OXYHEAT` | 33 | Endereço do byte de configuração da verificação da resistência da sonda lambda (O2 heater) |
| `LAUNCH_CUT` | 40 | Endereço do valor de corte do launch control |
| `LAUNCH_RES` | 41 | Endereço do valor de retoma do launch control |
| `SHIFT_CUT` | 42 | Endereço do valor de corte do full-throttle-shift |
| `SHIFT_RES` | 43 | Endereço do valor de retoma do full-throttle-shift |
| `SPEED_LIMIT` | 44 | Endereço do valor do limitador de velocidade |
| `NFO_MAP_MIN` | 45 | Informações de MAP mínimo; sem descrição na fonte |
| `NFO_MAP_MAX` | 46 | Informações de MAP máximo; sem descrição na fonte |
| `MTX1` | 50 | Endereço do multiplicador final de combustível |
| `MTX2` | 51 | Sem descrição na fonte |
| `MTX3` | 52 | Endereço do multiplicador de combustível no arranque (cranking) |
| `MTX4` | 53 | Sem descrição na fonte |
| `MTX5` | 54 | Endereço do multiplicador de combustível de aceleração rápida (tip-in) |
| `MTX6` | 55 | Sem descrição na fonte |
| `SL_BYTE` | 56 | Endereço do byte de configuração da shift-light |
| `SL_RPM` | 57 | Endereço das RPM da shift-light |

A documentação arquivada indica que um manipulador de ROM deve definir as propriedades `hasLaunchControl`, `hasFullThrottleShift`, `hasFinalMultiplier`, `hasShiftLight` e `hasIAB` correspondentes para `1` para que os editores de opções integrados do Crome as utilizem.
