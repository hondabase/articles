---
summary: 'Um guia educativo que explica a arquitetura de hardware, o mapeamento de memória, o expansor de I/O OKI 82C55 e o código assembly 66k das ECUs Honda OBD1.'
tags: [ecu, hardware, education]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Doc ECU School'
    url: /pgmfi/wiki/library/doc-ecu-school
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Arquitetura e Mapeamento de Memória da ECU Honda OBD1

A plataforma de ECU Honda OBD1 (como a P28, P30 e P72) é baseada no microcontrolador OKI `66207` (conjunto de instruções 66k). Para gerir as diversas entradas e saídas necessárias para controlar um motor, o MCU utiliza uma combinação de pinos diretos, multiplexadores analógicos e um expansor de I/O 82C55 personalizado.

Compreender como o software da ECU interage com estes elementos de hardware é essencial para o desenvolvimento de ROMs personalizadas e engenharia reversa.

---

## 1. Arquitetura de I/O de Hardware

A ECU classifica os sinais com base na sua prioridade de temporização e tipo de sinal (analógico vs. digital):

* **I/O Direto do MCU:** Sinais de alta prioridade ou altamente sensíveis ao tempo estão ligados diretamente ao MCU. Estes incluem os sensores de velocidade de rotação do motor (RPM) (CYP, CKP, TDC), o sensor de velocidade do veículo (VSS) e os circuitos de controlo do excitador (driver) dos injetores.

* **Entradas Analógicas:** As tensões dos sensores (MAP, TPS, IAT, ECT, sonda Lambda/sensor de Oxigénio) são encaminhadas diretamente para o conversor analógico-digital (ADC) interno do MCU através de circuitos integrados (IC) multiplexadores.

* **Expansor de I/O 82C55:** A maioria dos interruptores digitais (interruptor da embraiagem, pedido de A/C) e saídas de solenoide de baixa prioridade (solenoide de VTEC, relé da embraiagem do A/C, purga do EVAP) são geridos por um chip expansor de I/O de 44 pinos personalizado compatível com Intel 82C55.

* **Trinco de Entrada (Input Latch):** Um IC tipo latch lógico de 20 pinos localizado perto da EPROM funciona como um buffer de entrada digital adicional de 8 bits para interruptores do chassis e da transmissão.

---

## 2. Registos Mapeados em Memória e Buffers de RAM

Como o 82C55 está mapeado como um dispositivo periférico no espaço de memória da ECU, ele não possui endereços diretos de RAM. Em vez disso, o software utiliza localizações de RAM específicas como buffers intermédios de entrada/saída. Durante a execução, a ECU sincroniza continuamente estes buffers de RAM com os registos de hardware físicos (que estão espelhados nos espaços de memória como `0x0F00`, `0x1F00` e `0x2F00`).

### Endereços Comuns de Buffers de I/O (Codebases P30 / P28)

* **Endereço de RAM `0x10` e `0x11` (Bytes de Entrada Digital):** Os bits nestes bytes representam entradas de interruptores.
 

* `11.2`: Interruptor de Pedido de A/C
 * `10.5`: Retorno do Interruptor de Pressão de VTEC (VTS)

* **Endereço de RAM `0x20`, `0x22` e `0x24` (Bytes de Saída Digital):** Modificar bits nestes bytes de RAM altera os estados de saída.
 

* `20.0`: Solenoide do Relé da Embraiagem do A/C
 * `22.0`: Saída do Solenoide de VTEC

* **Endereço de RAM `0x14` (Byte de Flag de Erro):** Usado para armazenar flags de falha de diagnóstico.
 

* `14.4`: Erro de circuito aberto/curto-circuito do solenoide de VTEC

---

## 3. Análise de Código Assembly (OKI 66k)

A análise do código assembly da ECU JDM OBD1 P30 (versão de ROM original `P30_203`) demonstra como a ECU processa estes buffers de RAM.

### Exemplo A: Lógica de Controlo da Embraiagem de A/C

Esta rotina verifica o estado do botão de A/C do habitáculo e controla a saída do relé da embraiagem do compressor:

```assembly
4306- DA 11 17 : JBR off 11.2, 4320 ; Salta para 4320 se o interruptor de A/C (11.2) estiver desligado (Reset)
4309- C4 26 1C : SB off 26.4 ; Ativa bit 26.4
430C- F4 E2 : LB A, off E2
430E- CE 1B : JNE 432B
4310- C4 E3 98 32 : MOVB off E3, #32
4314- C4 1B 18 : SB off 1B.0
4317- 95 : RC
4318- CB 15 : SJ 432F
431A- C4 B8 15 : CLRB off B8
431D- C4 E3 15 : CLRB off E3

4320- C4 26 0C : RB off 26.4 ; Desativa bit 26.4
4323- F4 E3 : LB A, off E3
4325- CE ED : JNE 4314
4327- C4 E2 98 32 : MOVB off E2, #32
432B- C4 1B 08 : RB off 1B.0
432E- 85 : SC
432F- C5 20 38 : MB 20.0, C ; Envia o estado para o solenoide da embraiagem do A/C (20.0) com base no Carry
```

### Exemplo B: Verificação de Retorno do Interruptor de Pressão de VTEC (VTS)

Para evitar a ativação do VTEC se a pressão do óleo for insuficiente, a ECU compara o estado da saída do solenoide de VTEC com a entrada do sensor VTS. Se estes não coincidirem, a ECU ativa a Luz de Check Engine (Código 21):

```assembly
3D06- DC 16 1B : JBR off 16.4, 3D24 ; Salta se o VTEC estiver desativado por software
3D09- EC 14 18 : JBS off 14.4, 3D24 ; Salta para 3D24 se a flag de erro do VTS (14.4) já estiver ativa
3D0C- DA 1F 0C : JBR off 1F.2, 3D1B ; Salta para 3D1B se a saída do solenoide de VTEC não estiver ativa
3D0F- C4 C0 98 14 : MOVB off C0, #14
3D13- F4 BF : LB A, off BF
3D15- ED 10 0C : JBS off 10.5, 3D24 ; Salta se o Interruptor de Pressão de VTEC (10.5) estiver ativo (Massa/Fechado)
3D18- 85 : SC
3D19- CB 09 : SJ 3D24
3D1B- C4 BF 98 14 : MOVB off BF, #14
3D1F- F4 C0 : LB A, off C0
3D21- ED 10 F4 : JBS off 10.5, 3D18
3D24- C5 9A 38 : MB 9A.0, C ; Em caso de divergência, ativa o bit 9A.0 para acionar o Código 21 (Interruptor VTEC)
```

Ao alterar esta rotina (como eliminar a verificação do bit `10.5`), os preparadores (tuners) podem ativar o VTEC em motores que carecem do interruptor físico de pressão de óleo do VTEC, o que é comum em conversões de cabeças de motor (swaps) JDM.

---

## 4. Jumpers de Hardware (RP17, RP18)

Os jumpers de configuração da ECU (RP17 e RP18) estão ligados diretamente a entradas analógicas multiplexadas. Como estes jumpers funcionam como divisores de resistência pull-up ou pull-down, o conversor analógico-digital lê a sua tensão para determinar qual a configuração de chassis, mercado regional ou tipo de transmissão (automática vs. manual) que o software da ECU deve assumir.
