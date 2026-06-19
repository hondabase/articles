---
summary: 'Guia de modificação de hardware para criar uma configuração de dual-ROM utilizando uma EPROM 27C512 e um interruptor para selecionar entre dois mapas de motor.'
tags: [ecu, hardware, tuning]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Dual Roms'
    url: /pgmfi/wiki/library/dual-roms
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Configuração DIY de Dual-ROM (Interruptor de Jumper 27C512)

Uma calibração de ROM padrão de uma ECU OBD0 ou OBD1 da Honda tem 32 KB (256 kilobits) e cabe num chip `27C256` padrão. Ao utilizar uma EPROM **`27C512`** de dupla capacidade (64 KB / 512 kilobits), pode armazenar duas calibrações de ROM completas e independentes num único chip físico e alternar entre elas utilizando um interruptor simples no painel.

---

## 1. Preparação do Ficheiro da ROM

Para criar um binário dual-ROM:
1. Abra o seu software de edição de ROM (como o Crome ou o TurboEdit) e guarde os seus dois ficheiros BIN afinados de 32 KB separados (por exemplo, `Tune_A.bin` e `Tune_B.bin`).
2. Utilize uma ferramenta de junção de ficheiros ou um editor hexadecimal para combinar os dois ficheiros num único binário de 64 KB:
 

* **Lower Bank (Offset `0x0000` a `0x7FFF`):** Coloque o `Tune_A.bin` aqui.
 

* **Upper Bank (Offset `0x8000` a `0xFFFF`):** Coloque o `Tune_B.bin` aqui.
3. Programe o ficheiro de 64 KB fundido numa EPROM `27C512` ou num chip Flash SST `27SF512`.

---

## 2. Modificação de Hardware e Cablagem

Para alternar entre os dois bancos de memória, deve controlar o estado da linha de endereço mais alta no chip 27C512: **Pino 1 (A15)**.

* Quando o **Pino 1 é ligado à massa (0V)**, as linhas de endereço acedem ao banco inferior de 32 KB (`A15 = 0`).
* Quando o **Pino 1 recebe +5V (VCC)**, as linhas de endereço acedem ao banco superior de 32 KB (`A15 = 1`).

```text
 27C512 EPROM Chip
 +------()------+
 [Switch] <---|1 (A15) 28| VCC (+5V Power)
 |2 27| 
 |3 26|......
 |14 (GND) 15| 
 +--------------+
```

### Cablagem Passo a Passo:

1. **Isolar o Pino 1:** Dobre o **Pino 1 (A15)** no seu chip EPROM `27C512` para fora num ângulo de 90 graus, de modo a que não seja inserido no suporte da ECU.
 
 > [!CAUTION]
 > O Pino 1 de um suporte de ECU padrão para `27C256` transporta uma linha constante de +5V (que serve como pino de tensão de programação `VPP` em chips mais antigos). Se não dobrar o Pino 1 para fora e ligar o interruptor à massa, criará um curto-circuito direto na linha de alimentação de +5V da ECU, desligando instantaneamente o motor e danificando potencialmente o regulador de tensão da ECU.

2. **Soldar a Resistência Jumper:** Solde uma resistência pull-up de 10k $\Omega$ entre o Pino 1 dobrado e o Pino 28 (VCC, alimentação de +5V) do chip. Isto mantém o pino em estado lógico alto (+5V) por defeito quando o interruptor está aberto.
3. **Cablagem do Interruptor:** Ligue um fio do Pino 1 dobrado a um interruptor basculante unipolar de uma via (SPST) no seu painel. Ligue o outro lado do interruptor a um ponto de massa do chassis (ou ao Pino 14 da placa da ECU).
 

* **Interruptor Aberto:** O Pino 1 é mantido a +5V (executando o mapa `Tune_B`).
 

* **Interruptor Fechado:** O Pino 1 é ligado à massa (executando o mapa `Tune_A`).

---

## 3. Melhores Práticas para Mapas Duplos

* **Desativar Checksums:** Certifique-se de que a validação de checksum está desativada em ambos os ficheiros de ROM antes de os gravar, para evitar que a ECU ative uma luz de aviso do motor (Check Engine Light) fixa (modo de segurança / limp mode) durante a comutação.

* **Manter as Codebases Idênticas:** Se planeia alternar os mapas em tempo real (por exemplo, ativar um mapa de óxido nitroso quando um solenoide é acionado), certifique-se de que ambos os ficheiros de ROM utilizam exatamente a mesma versão da base de código (codebase). As únicas diferenças devem ser os valores de combustível e ignição nas tabelas de consulta. Alternar entre diferentes estruturas de base de código com o motor em funcionamento irá bloquear o microcontrolador (MCU).
