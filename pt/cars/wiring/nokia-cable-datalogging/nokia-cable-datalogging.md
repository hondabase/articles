---
summary: 'Guia técnico para converter um cabo de telemóvel serial Nokia FBUS antigo num adaptador serial USB-para-TTL de baixo custo para datalogging de ECUs Honda OBD1.'
tags: [datalogging, hardware, wiring]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Nokia Cable Datalogging'
    url: /pgmfi/wiki/library/nokia-cable-datalogging
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Cabo de Datalogging DIY via Modificação de Nokia FBUS

O datalogging a partir de uma ECU Honda OBD1 requer a conversão do sinal serial de lógica transistor-transistor (TTL) de 5V da ficha `CN2` da ECU num sinal USB padrão que um portátil possa ler.

Um método clássico e altamente económico para o conseguir é modificar um cabo de dados de telemóvel antigo Nokia FBUS (originalmente vendido para telemóveis das séries Nokia 3200, 5100 e 6100). Estes cabos contêm um chip transcetor serial **USB-para-TTL Prolific PL-2303** embutido dentro da ficha USB, que fornece uma ligação de alta velocidade e sem interferências (jitter-free) para programas de afinação.

---

## 1. Esquema de Pinos da Ficha CN2 e Aviso de Segurança

A ECU Honda OBD1 envia e recebe dados seriais na ficha **CN2** (localizada no lado direito da placa da ECU).

> [!CAUTION]
> O Pino 5 na ficha CN2 transporta tensão direta de 12V da bateria. Nunca ligue este pino ao seu adaptador USB ou portátil. Fazê-lo irá destruir instantaneamente o chip do adaptador serial, a porta USB do seu portátil e, potencialmente, o próprio portátil.

| Pino CN2 | Função | Ligação |
| :---: | :--- | :--- |
| **Pino 1** | Massa (GND) | Ligar à Massa do Cabo |
| **Pino 2** | Transmissão da ECU (TX) | Ligar à Receção do Cabo (RX) |
| **Pino 3** | Alimentação Lógica +5V | *Desligado

* (a porta USB fornece energia) |
| **Pino 4** | Receção da ECU (RX) | Ligar à Transmissão do Cabo (TX) |
| **Pino 5** | Alimentação +12V | **NÃO LIGAR** |

---

## 2. Mapeamento de Cablagem

Para modificar o cabo, corte a ficha proprietária do telemóvel Nokia e exponha os fios internos. Como os fabricantes utilizavam diferentes configurações de fios, deve identificar o seu tipo de cabo.

### Opção A: Cabo USB RadioShack (Peça #170-0787)

Este cabo utiliza uma placa de circuito interno mais complexa, mas fornece uma comunicação altamente estável:

* **Fio Castanho:** Massa. Ligue à malha de blindagem do cabo e solde ao **Pino 1 (GND)** no conector CN2.

* **Fio Laranja:** RX do Cabo. Solde ao **Pino 2 (ECU TX)** no conector CN2.

* **Fio Vermelho:** TX do Cabo. Solde ao **Pino 4 (ECU RX)** no conector CN2.

| Layout da Placa RadioShack |
| :---: |
| ![Vista Superior da PCB do Cabo RadioShack](RadioShackUSBCabletopview.jpg) |
| *Vista superior da PCB do cabo RadioShack com a caixa removida.

* |
| ![Vista Inferior da PCB do Cabo RadioShack](RadioShackUSBCablebottomview.jpg) |
| *Vista inferior da PCB do cabo RadioShack mostrando as pistas dos pinos.

* |

---

### Opção B: Cabo USB Nokia Genérico / eBay

Estes cabos genéricos possuem uma PCB mais pequena e simples dentro da ficha USB:

* **Fio Preto:** Massa. Ligue à malha de blindagem do cabo e solde ao **Pino 1 (GND)** no conector CN2.

* **Fio Branco:** RX do Cabo. Solde ao **Pino 2 (ECU TX)** no conector CN2.

* **Fio Azul:** TX do Cabo. Solde ao **Pino 4 (ECU RX)** no conector CN2.

| Layout da Placa Genérica do eBay |
| :---: |
| ![Vista Superior da Placa do Cabo Genérico do eBay](eBayUSBCabletopview.jpg) |
| *Vista superior da placa do adaptador serial USB-para-TTL genérico.

* |
| ![Vista Inferior da Placa do Cabo Genérico do eBay](eBayUSBCablebottomview.jpg) |
| *Vista inferior mostrando os pontos de solda dos fios na placa genérica.

* |

---

## 3. Configuração do Software

1. **Remover a Ponte `J12`:** Para permitir a comunicação serial full-duplex na ECU OBD1, deve dessoldar e remover a ponte **`J12`** na placa principal da ECU.
2. **Instalação de Controladores (Drivers):** Não instale o software de telemóvel da Nokia. Em vez disso, descarregue e instale o controlador genérico **Prolific PL-2303 USB-to-Serial** diretamente do website oficial da Prolific ou de arquivos de suporte.
3. **Configuração da Porta COM:** Ligue o cabo, identifique o número da porta COM atribuída no Gestor de Dispositivos do Windows e configure o seu software de afinação (ex: Crome, Hondata, TurboEdit) para utilizar essa porta COM a **38400 baud** (ou a velocidade exigida pela base de código da sua ROM específica).
