---
summary: 'Aprende como as ECUs Honda OBD1 comunicam com computadores portáteis de afinação através de sinais de série TTL (conector CN2), incluindo esquemas de pinagem, configurações e avisos de cablagem.'
applies_to:
  obd: [1]
  complexity: advanced
  tags:
    - ecu
    - datalogging
    - serial
sources:
  - name: 'pgmfi.org wiki'
    title: 'Comunicação de Série'
    url: /pgmfi/wiki/library/serial-communication
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Datalogging de Série da ECU Honda (Conector TTL `CN2`)

A comunicação de série é o mecanismo primário utilizado para transmitir diagnósticos em tempo real (leituras de sensores, rotação do motor e códigos de erro) de uma ECU Honda para um computador portátil a executar software de afinação (como o Crome, Hondata ou Neptune).

Nas ECUs Honda OBD1 (como a [P28](/cars/sensors/p28) ou a [P30](/cars/sensors/p30)), esta comunicação é gerida através de um conector de pinos macho físico de 4 ou 5 pinos designado como **`CN2`**, localizado no lado direito da placa de circuito principal.

---

## 1. Aviso Crítico de Tensão: TTL vs. RS-232

> [!CAUTION]
> A porta de série da ECU Honda utiliza níveis **TTL (Transistor-Transistor Logic)**. Os sinais TTL funcionam estritamente a tensões baixas: **0V (nível lógico baixo)** e **5V (nível lógico alto)**.
>
> As portas de série padrão dos computadores e os cabos DB9 baratos utilizam **níveis de tensão RS-232**, que variam de **-12V (nível lógico baixo)** a **+12V (nível lógico alto)**. Ligar um cabo RS-232 padrão diretamente ao conector CN2 da ECU destruirá imediatamente o microcontrolador interno OKI da ECU.
>
> Utiliza sempre uma interface conversora TTL para USB dedicada (como um cabo Moates Extreme OBD1 ou uma placa USB para TTL padrão FTDI/CP2102) para fazer a ligação.

---

## 2. Pinagem do Conector `CN2`

Nas placas principais USDM OBD1, a porta `CN2` é composta por 5 pinos. No entanto, apenas 4 pinos são utilizados para datalogging de série. Nota que o Pino 1 está normalmente marcado na placa por um ponto de solda quadrado ou pela impressão de um pequeno número "1":

| Número do Pino | Nome do Sinal | Descrição |
| :--- | :--- | :--- |
| **Pino 1** | **TX** | Transmitir (dados enviados *da* ECU *para* o computador) |
| **Pino 2** | **RX** | Receber (dados enviados *do* computador *para* a ECU) |
| **Pino 3** | **VCC** (+5V) | Saída de alimentação de 5V da ECU (normalmente deixada **desligada** ao utilizar adaptadores USB com alimentação própria) |
| **Pino 4** | **GND** | Massa de Sinal / Terra (deve ser ligada ao pino de massa do adaptador USB para estabelecer uma referência comum) |
| **Pino 5** | **NC** | Não Ligado (frequentemente ausente ou em branco) |

---

## 3. Parâmetros de Comunicação de Série

Para estabelecer uma ligação bem-sucedida entre a ECU e o teu software de datalogging, os controladores da porta COM virtual e o software de afinação devem ser configurados para corresponder aos parâmetros de comunicação da ECU:

- **Baud Rate:** **38,400 bps** (Padrão para protocolos OBD1 personalizados como o Crome Pro e Hondata; alguns diagnósticos de fábrica antigos funcionam a **9,600 bps**)
- **Data Bits:** **8**
- **Paridade:** **Nenhuma**
- **Stop Bits:** **1**
- **Controlo de Fluxo:** **Nenhum**

![Estrutura típica de bytes de uma trama de dados de série](sercom.jpg)
*Uma trama típica de comunicação de série de 11 bits, mostrando os bits de início (start), dados (data), paridade (parity) e paragem (stop).*

---

## 4. Configuração do Adaptador USB para TTL

Para ligar a porta `CN2` a um computador portátil moderno:
1. Solda um conector de 4 pinos na localização `CN2` da placa da tua ECU.
2. Liga o pino **GND** do teu adaptador USB para TTL ao pino **GND** da ECU (Pino 4).
3. Liga o pino **RX** do adaptador ao pino **TX** da ECU (Pino 1) - *ligação cruzada*.
4. Liga o pino **TX** do adaptador ao pino **RX** da ECU (Pino 2) - *ligação cruzada*.
5. Deixa a linha de 5V **desligada** para evitar loops de terra (ground loops), uma vez que o adaptador USB é alimentado pelo computador portátil.
6. Instala os controladores `FTDI` ou Silicon Labs CP210x no teu computador portátil e seleciona a porta COM correspondente no teu programa de afinação.

Para detalhes sobre como selecionar e resolver problemas com o hardware de ligação, consulta o [guia de hardware do conversor USB para série](/cars/tuning/second-gen-usb-to-serial-converter). Para plugins de software, consulta o [guia de configuração do Crome](/cars/rom/crome-faq).
