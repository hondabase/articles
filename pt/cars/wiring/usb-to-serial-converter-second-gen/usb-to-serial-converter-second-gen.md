---
summary: 'Guia técnico para ligação, configuração e teste de loopback de adaptadores de série USB-para-TTL baseados em FTDI para datalogging de ECUs Honda.'
applies_to:
  obd: [0, 1]
complexity: intermediate
tags:
  - datalogging
  - hardware
  - cablagem
sources:
  - name: 'pgmfi.org wiki'
    title: 'Usb To Serial Converter Second Gen'
    url: /pgmfi/wiki/library/usb-to-serial-converter-second-gen
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Adaptadores de Série USB-para-TTL (`FTDI` / USBMOD3)

Os portáteis modernos não possuem as portas de série COM RS-232 legadas historicamente utilizadas para ligar a hardware de afinação automóvel. Para estabelecer uma ligação de datalogging em tempo real com uma ECU Honda, deve utilizar um conversor de série USB-para-TTL. 

Uma solução altamente fiável é o **Elexol USBMOD3**, um módulo de interface alimentado por um chip emissor-recetor `FTDI` de alta velocidade que traduz os sinais de série TTL de 5V da ECU em pacotes de dados compatíveis com USB.

---

## 1. Configuração do Módulo e Mapa de Pinos

Para configurar o módulo USBMOD3 para funcionamento alimentado pelo barramento (alimentado por USB) e contornar os controlos de handshake de hardware, faça as seguintes ligações de pinos na interface do módulo:

| Pino de Origem | Pino de Destino | Finalidade |
| :---: | :---: | :--- |
| **Pino 4 (Vcc)** | **Pino 8 (Reset In)** | Puxa a linha de reset para nível lógico alto (evita resets acidentais). |
| **Pino 9 (Enum Power)** | **Pino 10 (Reset Out)** | Configura o módulo para funcionamento alimentado pelo barramento. |
| **Pino 18 (Power Control)** | **Ground (GND)** | Puxa o controlo de energia para nível lógico baixo para ativar o modo de alimentação pelo barramento. |
| **Pino 12 (VIO)** | **Pino 13 (V+)** | Alimenta os pinos de E/S do UART com a tensão interna correta. |
| **Pino 23 (DSR)** | **Pino 24 (DTR)** | Liga o Data Set Ready ao Data Terminal Ready para contornar os controlos de handshake do modem de hardware. |
| **Pino 25 (CTS)** | **Pino 26 (RTS)** | Liga o Clear To Send ao Request To Send para contornar o controlo de fluxo de hardware. |

---

## 2. Teste de Diagnóstico de Loopback

Antes de soldar o módulo à cablagem da sua ECU, realize um teste de loopback para verificar se o chip conversor USB e os drivers do PC estão a funcionar corretamente:

1. **Ligar Linhas de Série:** Ligue temporariamente um fio de ponte (jumper) entre o **Pino 27 (RXD)** e o **Pino 28 (TXD)** na placa do USBMOD3.
2. **Ligar ao PC:** Ligue o cabo USB do módulo ao seu portátil. Transfira e instale os drivers padrão de Porta COM Virtual (VCP) da FTDI a partir do website oficial da FTDI.
3. **Identificar Porta COM:** Abra o **Gestor de Dispositivos** do Windows e expanda a secção **Portas (COM e LPT)**. Anote o número da porta COM atribuído à Porta de Série USB (ex.: `COM3`).
4. **Abrir Consola de Terminal:** Inicie uma aplicação de terminal de série (como o PuTTY ou Tera Term) e ligue-se à porta COM identificada a **38400 baud**.
5. **Teste de Digitação:** Digite vários caracteres na janela do terminal.
 

* **Sucesso:** Se vir os caracteres aparecerem no ecrã (eco), o chip FTDI está a transmitir e a receber dados com sucesso.
 

* **Falha:** Se não aparecer nada, verifique os seus drivers, as pontes nos pinos e o cabo USB.

---

## 3. Ligação à Porta `CN2` da ECU

Assim que o teste de loopback passar, remova a ponte temporária entre os pinos 27 e 28, e ligue o módulo ao conector `CN2` da ECU:

1. Ligue o **Pino 27 (RXD no módulo)** ao **Pino 2 (ECU TX)** no conector `CN2`.
2. Ligue o **Pino 28 (TXD no módulo)** ao **Pino 4 (ECU RX)** no conector `CN2`.
3. Ligue o **Ground (GND no módulo)** ao **Pino 1 (ECU GND)** no conector `CN2`.

> [!WARNING]
> Nunca ligue o Pino 5 (12V) do conector `CN2` da ECU à placa do USBMOD3. Isto destruirá instantaneamente o módulo emissor-recetor e danificará a porta USB do seu portátil.
