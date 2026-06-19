---
summary: 'Tabelas de lógica técnica, mapeamento de linhas de endereço e reduções de portas booleanas para construção de hardware personalizado de emulação de ROM em Tempo Real (RTP).'
tags: [hardware, afinação]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Rtp Truth Table'
    url: /pgmfi/wiki/library/rtp-truth-table
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Mapeamento Lógico e Tabelas de Verdade para Emulação de EPROM (RTP)

A Programação em Tempo Real (RTP - Real-Time Programming) permite aos afinadores modificar as tabelas de combustível e ignição em tempo real com o motor em funcionamento. Isto é conseguido substituindo a EPROM padrão de apenas leitura (`27C256`) por uma SRAM Não Volátil (tal como a Dallas DS1230AB 32Kx8 NVSRAM).

Como a NVSRAM suporta tanto operações de leitura (pela ECU) como operações de escrita (a partir da interface do emulador), as portas lógicas devem encaminhar os sinais de controlo para evitar conflitos no barramento de dados.

---

## 1. Sinais de Entrada/Saída

Uma placa RTP personalizada fica posicionada entre o encaixe (socket) da placa principal da ECU e o chip NVSRAM. Os circuitos lógicos avaliam os seguintes pinos:

### Entradas (A partir do Encaixe da ECU / MCU)

* **A15:** Linha de Endereço 15 (divide o mapa de memória em segmentos inferior e superior).

* **/WR (/WE):** Linha de permissão de escrita (Write Enable) vinda do MCU.

* **/OE:** Permissão de Saída (Output Enable) (Pino 22 do encaixe EPROM 27C256 padrão).

* **/CS:** Seleção de Chip (Chip Select) (Pino 20 do encaixe EPROM 27C256 padrão).

### Saídas (Para NVSRAM / Placa Principal)

* **/IOWE:** Saída para as linhas de permissão de escrita dos outros periféricos de E/S na placa principal da ECU.

* **/WE:** Pino de permissão de escrita (Write Enable) na NVSRAM DS1230.

* **/OE:** Pino de permissão de saída (Output Enable) na NVSRAM DS1230.

* **/CE:** Pino de permissão de chip (Chip Enable) na NVSRAM DS1230.

---

## 2. Tabela de Verdade Lógica Completa

A seguinte tabela de verdade descreve o comportamento necessário para garantir a compatibilidade com placas principais OBD0 e OBD1:

| A15 | /WR | /OE | /CS | /IOWE | /WE (NVSRAM) | /OE (NVSRAM) | /CE (NVSRAM) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **0** | $a$ | $b$ | $c$ | $a$ | **1** | $b$ | $c$ |
| **1** | $a$ | $X$ | $X$ | **1** | $a$ | **1** | **0** |

*Aqui, $a$, $b$ e $c$ representam estados lógicos de sinal ativos (alto ou baixo), enquanto $X$ representa um estado de indiferença ("don't care").*

---

## 3. Redução Simplificada de Portas NAND

Como as placas principais OBD0 e OBD1 gerem a permissão de saída (`/OE`) nativamente conforme mostrado acima, o pino de permissão de chip (`/CE`) na NVSRAM pode ser simplesmente ligado à massa (permanentemente ativo).

Isto simplifica a tabela de verdade para o encaminhamento da linha de endereço **A15** e de permissão de escrita **`/WE`**:

| A15 | /WE (Entrada) | /IOWE (Saída) | /WE (Saída NVSRAM) | /CE (Saída NVSRAM) |
| :---: | :---: | :---: | :---: | :---: |
| **0** | $a$ | $a$ | **1** | **0** |
| **1** | $a$ | **1** | $a$ | **0** |

Esta lógica simplificada pode ser construída utilizando um único circuito integrado de quatro portas NAND de 2 entradas (como o 74HC00):

$$\text{/IOWE} = \text{/WE} \text{ NAND } \text{!A15}$$

$$\text{/WE}_{\text{NVSRAM}} = \text{/WE} \text{ NAND } \text{A15}$$

$$\text{!/WE} = \text{/WE} \text{ NAND } \text{/WE}$$

$$\text{!A15} = \text{A15} \text{ NAND } \text{A15}$$

### Isolamento para Programadores

Em designs profissionais de placas de emulação, são colocados um díodo e um transístor nas linhas de permissão de escrita. Isto isola as portas lógicas quando todo o conjunto do emulador é ligado a um programador de EPROM padrão, protegendo os chips lógicos das elevadas tensões de programação (Vpp) aplicadas durante a configuração inicial.
