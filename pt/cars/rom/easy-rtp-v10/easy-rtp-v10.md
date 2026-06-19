---
summary: 'Guia de montagem arquivado e notas parciais de instalação de OBD0/OBD1 para a placa DIY Easy-RTP v1.0.'
tags: [hardware, rom, chipping]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Easy Rtp V10'
    url: /pgmfi/wiki/library/easy-rtp-v10
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Guia de montagem e instalação DIY Easy-RTP v1.0

A **Programação em Tempo Real (RTP - Real-Time Programming)** permite aos afinadores (tuners) editar os mapas de combustível e ignição de uma ECU em tempo real enquanto o motor está a funcionar, eliminando a necessidade de desligar o motor, gravar um novo chip EPROM e trocá-lo a cada iteração de afinação.

A **Easy-RTP v1.0** é uma placa emuladora de EPROM clássica em estilo DIY (Faça Você Mesmo). É uma placa de circuito impresso (PCB) de face única concebida para alojar um chip NVSRAM (Non-Volatile SRAM) de 28 pinos (como o Dallas `DS1230Y`), fazendo a interface direta com uma ECU Honda OBD1 padrão já modificada com suporte (socketed).

> [!WARNING]
> Este projeto arquivado requer soldadura ao nível da placa e alterações de memória na ECU em tempo real. Desligue a alimentação durante a cablagem e verifique todos os cortes e pontes (jumpers) com um multímetro antes de ligar a alimentação.

![Easy RTP Board Eagle Layout Diagram](boardlayout.png)
*Diagrama de layout de pistas em Eagle CAD para a PCB Easy-RTP v1.0.*

---

## Lista de peças

Para montar a placa Easy-RTP, precisará dos seguintes componentes eletrónicos:

### Componentes principais

* **IC NVSRAM**: Dallas/Maxim **DS1230Y** (ou NVSRAM DIP de 28 pinos e 600 mil de 32KB compatível da TI, ST, Simtek ou ZMD).

* **IC de Portas Lógicas**: **74HC00** (Porta NAND de 4 entradas e 2 saídas - Quad 2-input NAND gate) num invólucro DIP padrão.

* **Condensadores**: Dois condensadores cerâmicos de **0.1 uF**.
* **Resistências**: Duas resistências de **10 kohm**.
* **Pinos de Interface da ECU**: Dois **conectores de pinos 1x14** (passo de 0.1", recomendam-se pinos torneados/machine pins para fiabilidade do suporte).

* **Suporte de ROM**: Um **Suporte DIP de 28 pinos** (para alojar o chip NVSRAM).

### Componentes opcionais para emulação de 27C256

A fonte original refere que estas peças são necessárias quando a emulação de 27C256 é precisa para um programador que não consegue programar nativamente a NVSRAM selecionada. Relata que a definição de 28C256 de um programador frequentemente funcionava, com a verificação de apagamento (blank-check) desativada num programador testado.

* **Resistências**: Uma resistência de **10 kohm** e uma de **100 kohm**.
* **Transístor NPN**: Um transístor de comutação NPN genérico (**2N4401** ou equivalente).

* **Díodo**: Um díodo de comutação (**1N4148** ou equivalente).

---

## Procedimento de montagem

Para montar a placa, oriente a PCB com as pistas voltadas para cima (vista inferior) para instalar os pinos de interface e, em seguida, vire a placa (pistas na parte inferior) para instalar os restantes componentes.

1. **Instalar os Pinos de Interface**: Solde os dois conectores de pinos 1x14 a partir da parte inferior (lado das pistas). Estes pinos serão conectados diretamente no suporte de ROM de 28 pinos da ECU.
2. **Instalar o Suporte da NVSRAM**: Vire a placa. Solde o suporte DIP de 28 pinos no conjunto de furos superior. Certifique-se de que a ranhura de alinhamento do chip está virada para a **Esquerda**.
3. **Instalar o Jumper `J1`**: Solde um conector macho de 3 pinos ou uma ponte de 3 fios na localização do jumper **`J1`**.
4. **Soldar os condensadores**: Instale os dois condensadores de 0.1 uF em **`C1`** e **`C2`**.
5. **Soldar as resistências principais**: Solde as resistências de 10 kohm em **`R1`** (esquerda) e **`R2`** (centro).
6. **Configurar o modo de emulação**:
 * **Sem emulação `27C256`**: Solde uma ponte de fio sólido ou uma resistência de 0 ohms em **D1**. Salte para o passo final.
 * **Com emulação `27C256`**: Solde o díodo **1N4148** em **D1**, o transístor NPN em **`Q1`**, a resistência de 10 kohm em **`R3`** (topo) e a resistência de 100 kohm em **`R4`** (fundo).
7. **Instalar o IC lógico e a NVSRAM**: Solde o IC **74HC00** no lugar. Insira a NVSRAM **`DS1230Y`** no seu suporte.

### Fotos da montagem

![Top of raw Easy-RTP PCB](IM000496.JPG)
*Parte superior da PCB virgem.*

![ECU Pins Inserted from Bottom](IM000497.JPG)
*Pinos de interface da ECU inseridos a partir da parte inferior.*

![Soldering Pins on Trace Side](IM000498.JPG)
*Pinos de interface soldados no lado das pistas.*

![NVSRAM Socket Solder Front](IM000499.JPG)
*Suporte da NVSRAM visto do lado dos componentes.*

![NVSRAM Socket Solder Back](IM000500.JPG)
*Pontos de soldadura do suporte da NVSRAM.*

![J1 Jumper Installed](IM000501.JPG)
*Conector `J1` instalado.*

![C1/C2 Capacitors Soldered](IM000503.JPG)
*`C1` e `C2` instalados.*

![R1/R2 Resistors Soldered](IM000505.JPG)
*`R1` e `R2` instalados.*

![74HC00 Logic Chip Soldered](IM000507.JPG)
*IC lógico 74HC00 instalado.*

![Completed Board with DS1230Y Installed](IM000509.JPG)
*Placa concluída com o `DS1230Y` instalado.*

---

## Referência de instalação em OBD1

A página arquivada inclui duas imagens que documentam uma instalação OBD1 original e o local onde o seu criador cortou a linha de ativação de escrita (write-enable). Não disponibiliza um procedimento de instalação em texto completo pino a pino. Verifique o circuito em relação aos ficheiros de design da Easy-RTP e à ECU de destino antes de reproduzir a modificação.

![Original RTP Design Installed in ECU](doc_RTP_OBD1.jpg)
*Módulo Easy-RTP concluído instalado em ponte (piggyback) numa ECU OBD1 USDM.*

![Where to Cut the WE Line on the ECU Board](doc_RTP_OBD1_Cut_here.jpg)
*Destacando a localização exata para cortar a pista na parte inferior da placa OBD1 para isolar o pino de escrita.*

---

## Modificação para OBD0

Para correr a placa Easy-RTP v1.0 numa ECU OBD0, tem de modificar os sinais de seleção de chip (chip-select) e de controlo de escrita porque as placas OBD0 gerem o endereçamento de ROM de forma diferente.

### Componentes adicionais

* Um IC **74LS86N** (Quad 2-input XOR gate).

* Uma resistência de **10 kohm**.
* Fio fino isolado para pontes (jumper wire).

### Passos de modificação

> [!WARNING]
> As instruções arquivadas para OBD0 dependem de três imagens anotadas alojadas externamente que não estão presentes no arquivo. Também referem o IC de base como um `74LS00`, enquanto a lista de peças principal da Easy-RTP especifica um `74HC00`. Verifique o circuito antes de tentar este procedimento incompleto.

1. **Cortar Pistas da Placa**: Corte as pistas de controlo marcadas a vermelho no layout da PCB.
2. **Preparar a porta XOR**: Corte ou remova todos os pinos do 74LS86N, exceto os Pinos 4, 5, 6, 7 e 14.
3. **Montar a porta XOR em ponte (piggyback)**: Monte o IC **74LS86N** sobre o IC NAND de base. Solde apenas os Pinos 4, 7 e 14 aos pinos correspondentes por baixo.
4. **Ligar as portas de sinal**: Dobre os Pinos 5 e 6 para cima e faça as ligações mostradas nas imagens de origem em falta.
5. **Isolar o Pino 16 da ECU**: Corte a ligação ao Pino 16 da ECU em ambos os lados da placa e, em seguida, volte a ligar o circuito original interrompido para que apenas o pino da ECU permaneça isolado.
6. **Ligar a placa RTP**: Ligue um fio da RTP a partir da sua entrada ao Pino 16 isolado da ECU, e ligue o outro fio da RTP ao Pino 21 da SRAM `M5128` de 24 pinos da ECU.

---

## Ficheiros de design

* [Ficheiros Eagle CAD da Easy-RTP v1.0 (ZIP)](easyrtpv1-eagle.zip)

* [PDF do Esquema da Placa Easy-RTP v1.0](rtp_EasyRtpV10-v1.pdf)
