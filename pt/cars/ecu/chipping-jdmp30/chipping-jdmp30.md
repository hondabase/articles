---
summary: 'Guia de modificação de hardware para colocação de suporte (socketing), modificação (chipping) e conversão de ECUs OBD1 P30 JDM de caixa quadrada para transmissão manual.'
tags: [ecu, chipping, hardware]
applies_to:
  brand: Honda
  ecus: [P30]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Chipping JDMP30'
    url: /pgmfi/wiki/library/chipping-jdmp30
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Modificação (Chipping) da ECU OBD1 P30 JDM

A ECU OBD1 P30 DOHC VTEC do mercado doméstico japonês (JDM) está alojada numa caixa metálica compacta e quadrada, que difere da caixa retangular maior utilizada para as ECUs do mercado norte-americano (USDM). 

Devido ao layout compacto da placa, a modificação (chipping) de uma P30 JDM requer trabalhar com dispositivos de montagem em superfície (SMD) em vez de componentes de furo passante (through-hole). O trinco de memória (latch `74HC373`) tem de ser soldado diretamente aos pads SMT na placa.

---

## 1. Componentes Necessários

Para fazer o chipping de uma ECU P30 JDM, adquira os seguintes componentes:

| Localização do Componente | Descrição / Valor | Fabricante / Número de Peça |
| :--- | :--- | :--- |
| **Latch (IC)** | `74HC373` SMD Latch (encapsulamento SOP-20) | SN74HC373NSR (Digi-Key: `296-8310-1-ND`) |
| **Suporte de ROM** | Suporte DIP de 28 pinos de perfil baixo | Largura padrão de 0.6" DIP-28 |
| **EPROM** | EPROM Reprogramável | SST `27SF256` ou `29C256` |
| **`C49` & `C50`** | Condensador cerâmico SMD de `0.004 uF` | Digi-Key: `399-1230-1-ND` |
| **`C91` & `C92`** | Condensador cerâmico SMD de `0.0001 uF` (100 pF) | Digi-Key: `399-1192-1-ND` |

> [!WARNING]
> As imagens de referência originais que mostram a localização exata dos condensadores e dos jumpers na parte inferior da placa não foram recuperadas dos arquivos antigos. Certifique-se de verificar as etiquetas dos pads impressas na serigrafia da sua PCB antes de soldar.

---

## 2. Procedimento de Chipping Passo a Passo

1. **Instalar o Latch SMD:** 
 Localize a pegada para o latch 74HC373 na placa. Aplique fluxo de solda nos pads SMT, alinhe os pinos do chip (garantindo que o entalhe do pino 1 coincide com o layout da placa) e solde o chip SOP-20 no lugar. Verifique se existem pontes de solda entre os pinos.
2. **Soldar o Suporte de ROM:** 
 Limpe a solda de fábrica dos furos passantes do DIP-28 na placa. Insira o suporte de 28 pinos a partir do lado superior e solde os 28 pinos a partir do lado inferior.
3. **Adicionar Condensadores de Filtragem:** 
 

* Solde **`C49`** e **`C50`** nos respetivos pads na parte inferior da placa.
 

* Solde **`C92`** nos respetivos pads na parte inferior.
 

* Solde **`C91`** nos respetivos pads no lado superior da placa, perto do latch.
4. **Fazer Ponte no Jumper J1:** 
 Faça uma ponte nos pads do jumper **`J1`** na parte inferior da placa com uma gota de solda ou um pequeno fio. Isto indica ao microcontrolador interno para ignorar a sua ROM interna e ler a partir da EPROM recém-instalada.
5. **Inserir a EPROM:** 
 Insira uma EPROM SST 27SF256 programada no suporte DIP-28. Certifique-se de que o entalhe no chip coincide com o entalhe no suporte.

---

## 3. Registo de Dados (Datalogging) e Programação em Tempo Real (RTP)

Se planeia utilizar um emulador em tempo real (como o Moates Ostrich) ou fazer datalog através da porta de série usando o Crome:

* **Remover `J4`:** Localize e dessolde a resistência de jumper de 0 ohms na posição **`J4`** no lado superior da placa. A remoção do `J4` desliga as rotinas de depuração de fábrica e ativa a transmissão de dados em série em modo full-duplex.

* **Instalar Pinos `CN2`:** Solde um conetor de pinos macho de 4 pinos (espaçamento de 0.1") no local da porta **`CN2`** para ligar o seu cabo de datalogging USB para TTL.

---

## 4. Conversão de Transmissão Automática para Manual

Para converter uma ECU P30 JDM automática para uma configuração manual e evitar as luzes de aviso de motor (CEL) do solenoide de bloqueio automático:

1. Localize a matriz de resistências na secção inferior direita na parte inferior da placa.
2. Dessolde e remova a resistência **`RP18`** (marcada com "472" / 4.7k ohms) e substitua-a por um fio de ponte sólido (0 ohms).
3. Dessolde e remova a resistência **`RP17`** por completo, deixando os pads abertos.
