---
summary: 'Converta ECUs OBD1 Honda de Civic/Integra USDM e JDM entre as configurações automática e manual alterando os valores de resistências na placa.'
applies_to:
  obd: [1]
complexity: advanced
tags:
  - ecu
  - obd1
  - hardware
  - conversion
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1 Civic Integra Auto Manual'
    url: /pgmfi/wiki/library/obd1-civic-integra-auto-manual
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Conversão de Automático para Manual de Civic/Integra OBD1

As ECUs Honda OBD1 USDM e JDM (como as P28, P30, P72 e P06) partilham placas de hardware quase idênticas para carros com transmissão automática e manual. Pode converter estas ECUs entre as configurações automática e manual modificando algumas resistências de montagem em superfície (RP17 e RP18).

## Visão Geral

A ECU verifica a resistência elétrica nas posições **RP17** e **RP18** para determinar se deve procurar por um sistema de controlo de transmissão automática ou funcionar como uma ECU manual.
*   Se estiver configurada como uma ECU automática num carro manual, a ECU irá apresentar o **Código 19** (Solenoide de Controlo de Bloqueio da Transmissão Automática) e poderá manter um ralenti ligeiramente irregular.
*   A conversão da placa para manual indica ao MCU para ignorar os solenoides da transmissão automática.

![Localizações dos jumpers de automático vs manual na placa OBD1](OBD1auto_manual.jpg)
*Layout da placa da ECU OBD1. A configuração dos jumpers está localizada no canto inferior direito, ao lado dos circuitos dos transístores de transmissão.*

## Especificações

### Valores de Resistências USDM (RP17 e RP18)

| Posição do Jumper/Resistência | Automático | Manual |
| :--- | :--- | :--- |
| **RP17** | 4,7k Ohm | *Aberto* (Removido) |
| **RP18** | 2,7k Ohm | *Com ponte* (fio de 0 Ohm) |

### Valores de Resistências JDM (Apenas RP18)

| Posição do Jumper/Resistência | Automático | Manual |
| :--- | :--- | :--- |
| **RP18** | 2,4k Ohm | 1,4k Ohm |

## Procedimento

### Conversão de Automático para Manual USDM
Para converter uma ECU Automática USDM (ex: P28-A51, P06-A52) para Manual:
1.  Localize as resistências **RP17** e **RP18** no canto inferior direito da placa de circuito da ECU.
2.  Dessolde e remova ambas as resistências **RP17** e **RP18**.
3.  Instale um fio de ponte simples (ou uma resistência de 0 ohm) no lugar de **RP18**. Deixe a posição **RP17** aberta (vazia).

![Conjunto de resistências RP antes da conversão](RPOnBoard1.JPG)
*Configuração de resistências automática de fábrica mostrando RP17 e RP18 povoados.*

![Conjunto de resistências RP após a conversão para manual](RPOnBoard2.JPG)
*Configuração manual convertida mostrando RP17 vazio e RP18 com ponte efetuada por um fio.*

### Conversão de Automático para Manual JDM
As ECUs JDM (normalmente as JDM P30, P72 ou PR3 de caixa grande ou pequena) não utilizam a configuração RP17/RP18 USDM. Em vez disso, utilizam uma única resistência em **RP18** localizada no lado de trás da placa, perto do canto.
1.  Localize a resistência **RP18** no lado de trás da placa da ECU.
2.  Dessolde a resistência de fábrica de 2,4k Ohm.
3.  Substitua-a por uma resistência de **1,4k Ohm**.

### Conversão de Manual para Automático USDM
Se precisar de colocar um carro automático a funcionar com uma ECU originalmente manual:
1.  Remova o fio de ponte em **RP18**.
2.  Instale uma resistência de **2,7k Ohm** em **RP18**.
3.  Instale uma resistência de **4,7k Ohm** em **RP17**.
4.  Adicione o chip controlador dos solenoides de transmissão/conjunto de transístores na posição **`IC16`** (normalmente um chip `5050S` ou equivalente), caso este esteja em falta na placa manual.

## Relacionado

*   [Introdução à Instalação de Chips em ECUs (ECU Chipping)](/cars/rom/introduction-to-ecu-chipping)
*   [Hardware da ECU](/cars/ecu/ecu-hardware)
*   [Resolução de Problemas da ECU](/cars/diagnostics/ecu-troubleshooting)
