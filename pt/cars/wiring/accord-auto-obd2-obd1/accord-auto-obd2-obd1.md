---
summary: 'Guia de conversão de cablagem e tabelas de tradução de pinagem para correr um Accord OBD2a automático utilizando uma ECU OBD1 automática de Integra e uma TCU separada.'
applies_to:
  obd: [1, 2]
complexity: advanced
tags:
  - conversão
  - cablagem
  - hardware
sources:
  - name: 'pgmfi.org wiki'
    title: 'Accord Auto OBD2-OBD1'
    url: /pgmfi/wiki/library/accord-auto-obd2-obd1
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Conversão de ECU e TCU de Accord Automático OBD2 para OBD1

Ao contrário dos Honda Civic da mesma época, que integram os controlos de lockup da transmissão diretamente dentro da ECU, os Honda Accord automáticos utilizam uma **Unidade de Controlo de Transmissão (TCU)** ou computador de transmissão independente.

Ao converter um Accord automático USDM de 5ª geração (1996–1997) de OBD2a para OBD1 para fins de afinação (ex.: adicionar sobrealimentação), as cablagens de ponte (jumper harnesses) padrão de OBD2 para OBD1 para transmissões manuais não irão funcionar porque não encaminham os sinais essenciais de comunicação da TCU.

Este guia, baseado no desenvolvimento de hardware documentado pelo investigador da comunidade Bird333, descreve as peças, o mapa de pinos e a construção da cablagem utilizada nessa conversão.

> [!WARNING]
> Esta é uma conversão desenvolvida pela comunidade para uma combinação específica de peças USDM. Verifique cada pino com os manuais de serviço de fábrica para a ECU dadora, TCU e veículo antes de ligar a alimentação. Uma ligação incorreta pode danificar a ECU, TCU, cablagem ou o veículo.

## 1. Componentes Necessários

Para correr um Accord automático OBD2a (ex.: Sedan LX de 1996 com motor F22B2) com uma ECU e TCU OBD1, precisará de:

1. **ECU OBD1 P75 Automática**: O guia arquivado especifica uma ECU P75 automática de Integra de 1994-1995. Descreve etiquetas terminadas em **`-P75-A5x`** para unidades de 49 estados dos EUA ou **`-P75-L5x`** para unidades da Califórnia, sendo que o `5` identifica uma ECU automática.
2. **TCU OBD1 de Accord**: Uma unidade de controlo de transmissão automática de um Accord não-VTEC de 1994–1995 (motor F22B2).
3. **Ficheiro bin de ROM modificado**: Uma EPROM alterada (chipped) gravada com uma ROM compatível de Integra automática. O guia arquivado utilizou a ROM `332` OBD1 USDM e copiou mapas de combustível e ignição adequados para a mesma.
4. **Esquemas Elétricos**: Manuais de serviço de fábrica para o Accord de 1994–1995 (para localizar a TCU), Integra de 1994–1995 (para localizar a ECU) e Accord de 1996 (para localizar a cablagem do motor OBD2a).

---

## 2. Peças para Construção da Cablagem de Ponte

Se optar por fabricar a sua própria cablagem de conversão personalizada em vez de modificar uma cablagem de pós-venda, precisará de:

* **Fio de 20 AWG**: Aproximadamente 30–36 metros (100–120 pés).
* **Fio de 18 AWG**: Aproximadamente 3–6 metros (10–20 pés, para linhas de alimentação de alta corrente e de massa).
* **Fichas de ECU OBD1**: Conectores Tyco / AMP:
  * Duas fichas de 26 pinos (Tyco `#174516-6`)
  * Duas fichas de 22 pinos (Tyco `#174515-6`)
  * Uma ficha de 16 pinos (Tyco `#174514-6`)
* **Ficha Fêmea OBD2a**: Um conector macho de 104 pinos (Tyco `#179686-6` ou dessoldado de uma ECU OBD2a usada).
* **Terminais de Conector**:
  * 65x Pinos de contacto pequenos (Tyco `#175061-1` ou banhados a ouro `-2`)
  * 26x Pinos de contacto grandes (Tyco `#173631-1` ou banhados a ouro `-2`)
* **Alicate de Crimpagem de Terminais**: Ferramenta de crimpagem padrão para terminais abertos (ex.: Molex ou Tyco `#WM9999-ND`).

---

## 3. Tradução de Pinagem de Accord OBD2a para ECU e TCU OBD1

A tabela abaixo mapeia o encaminhamento da cablagem das **fichas da cablagem de motor do Accord OBD2a de 1996–1997** do veículo para os novos pinos da **ECU OBD1 P75** e da **TCU OBD1 F22B2**:

| Ficha/Pino Accord OBD2a 1996-97 | Pino TCU Accord 1994 | Pino ECU Accord 1994 (Ref) | Pino ECU OBD1 P75 | Nome do Sinal / Função |
| :---: | :---: | :---: | :---: | :--- |
| **A01** | - | A02 | **A02** | Controlo do Injetor 4 |
| **A02** | - | A05 | **A05** | Controlo do Injetor 3 |
| **A03** | - | A03 | **A03** | Controlo do Injetor 2 |
| **A04** | - | A01 | **A01** | Controlo do Injetor 1 |
| **A05** | - | N/C | **N/C** | Sem Ligação |
| **A06** | - | A11 | **A06** | Aquecedor do Sensor de O2 Primário |
| **A08** | - | A04 | **A04** | Solenoide VTEC (VTS) *(Opcional)* |
| **A09** | - | A26 | **A26** | Massa Lógica 1 (LG1) |
| **A10** | - | A23 | **A23** | Massa de Potência 1 (PG1) |
| **A11** | A23 | - | - | Entrada de Alimentação de Ignição da TCU |
| **A11** | - | A25 | **A25** | Alimentação de Ignição 1 (IGP1) |
| **A12** | - | A09 | **A09** | Controlo da IACV |
| **A13** | - | A10 | **N/C** | Solenoide de Controlo do Apoio de Motor (MCS) |
| **A15** | - | A20 | **A20** | Solenoide de Controlo de Purga do EVAP |
| **A16** | - | A07 | **A07** | Controlo do Relé da Bomba de Combustível (FLR) |
| **A17** | A22 | A15 | **A15** | Controlo do Relé da Embraiagem do A/C |
| **A18** | - | A13 | **A13** | Luz de Verificação do Motor (MIL) |
| **A19** | - | A16 | **A16** | Controlo do Alternador (ALT C) |
| **A20** | - | A21 | **A21** | Módulo de Controlo de Ignição (ICM) |
| **A20?** | A09 | - | - | Entrada de Rotação do Motor da TCU *(Derivar para o fio de teste do tacómetro)* |
| **A22** | A25 | - | - | Massa da TCU |
| **A22** | - | B02 | **B02** | Massa Lógica 2 (LG2) |
| **A23** | A26 | - | - | Massa da TCU |
| **A23** | - | A24 | **A24** | Massa de Potência 2 (PG2) |
| **A24** | A24 | - | - | Entrada de Alimentação de Ignição da TCU |
| **A24** | - | B01 | **B01** | Alimentação de Ignição 2 (IGP2) |
| **A27** | - | A12 | **A12** | Controlo do Ventilador do Radiador (FANC) |
| **A28** | - | N/C | **N/C** | Sem Ligação |
| **A29** | - | N/C | **N/C** | Sem Ligação |
| **B03** | A05 | - | - | Solenoide A de Controlo de Passagem de Caixa |
| **B04** | A04 | - | - | Solenoide B de Controlo de Lockup |
| **B05** | A06 | - | - | Solenoide A de Controlo de Lockup |
| **B08** | A15 | - | - | Posição D3 da Transmissão Automática |
| **B11** | A03 | - | - | Solenoide B de Controlo de Passagem de Caixa |
| **B12** | A18 | - | - | Interbloqueio de Passagem de Caixa (Shift Interlock) |
| **B13** | A08 | - | - | Luz Indicadora D4 no Painel |
| **B14** | D12 | - | - | Massa do Sensor de Velocidade do Veio Primário (Mainshaft) |
| **B15** | D19 | - | - | Sinal do Sensor de Velocidade do Veio Primário (Mainshaft) |
| **B16** | A21 | - | - | Posição de Marcha-Atrás da Transmissão Automática |
| **B17** | A13 | - | - | Posição 2 da Transmissão Automática |
| **B18** | A11 | - | - | Posição 1 da Transmissão Automática |
| **B22** | D15 | - | - | Massa do Sensor de Velocidade do Veio Secundário (Countershaft) |
| **B23** | D17 | - | - | Sinal do Sensor de Velocidade do Veio Secundário (Countershaft) |
| **B24** | A17 | - | - | Posição D4 da Transmissão Automática |
| **B25** | A19 | B07 | **B07** | Posição Park/Neutral da Transmissão Automática |
| **C02** | - | B15 | **B15** | Sensor de Posição da Cambota (CKP P) |
| **C03** | - | B13 | **B13** | Sensor de Ponto Morto Superior (TDC P) |
| **C04** | - | B11 | **B11** | Sensor de Posição do Cilindro (CYP P) |
| **C05** | - | B05 | **B05** | Interruptor do Termóstato do A/C |
| **C06** | - | B09 | **B09** | Sinal do Interruptor de Arranque (STS) |
| **C07** | D06 | D04 | **D04** | Sinal de Ponte de Verificação de Serviço (SCS) |
| **C08** | - | D07 | **D07** | Diagnóstico K-Line |
| **C10** | A20 | - | - | Entrada de Bateria de Salvaguarda (Backup) da TCU |
| **C10** | - | D01 | **D01** | Alimentação de Salvaguarda (VBU) |
| **C12** | - | B16 | **B16** | Massa do Sensor de Posição da Cambota (CKP M) |
| **C13** | - | B14 | **B14** | Massa do Sensor de Ponto Morto Superior (TDC M) |
| **C14** | - | B12 | **B12** | Massa do Sensor de Posição do Cilindro (CYP M) |
| **C15** | - | D06 | **D06** | Interruptor de Pressão do VTEC (VTP) *(Opcional)* |
| **C16** | - | B08 | **B08** | Interruptor de Pressão da Direção Assistida (PSP) |
| **C17** | - | D09 | **D09** | Sinal FR do Alternador (ALT FR) |
| **C18** | D09 | B10 | **B10** | Sensor de Velocidade do Veículo (VSS) |
| **C20** | - | N/C | **N/C** | Sem Ligação |
| **D01** | D07 | D11 | **D11** | Sensor de Posição do Acelerador (TPS) |
| **D02** | D05 | D13 | **D13** | Sensor de Temperatura do Líquido de Refrigeração do Motor (ECT) |
| **D03** | - | D17 | **D17** | Pressão Absoluta do Coletor (MAP) |
| **D04** | - | D19 | **D19** | Tensão de Referência de 5V do Sensor (VCC1) |
| **D05** | D02 | - | - | Entrada do Interruptor de Travão (TCU) |
| **D05** | - | D02 | **D02** | Entrada do Interruptor de Travão (ECU) |
| **D06** | - | - | **NOT CONN** | Sensor de Detonação (Knock) *(Não utilizado na P75)* |
| **D07** | - | D14 | **D14** | Sensor de Oxigénio Primário (O2) |
| **D08** | - | D15 | **D15** | Sensor de Temperatura do Ar de Admissão (IAT) |
| **D09** | - | D12 | **NOT CONN** | Sensor de Elevação da EGR |
| **D10** | - | D20 | **D20** | Tensão de Referência de 5V do Sensor (VCC2) |
| **D11** | - | D22 | **D22** | Massa do Sensor 2 (SG2) |
| **D12** | - | D21 | **D21** | Massa do Sensor 1 (SG1) |
| **D13** | - | N/C | **N/C** | Massa do Sensor de O2 Secundário *(Apenas OBD2, eliminar)* |
| **D14** | - | N/C | **N/C** | Sinal do Sensor de O2 Secundário *(Apenas OBD2, eliminar)* |
| **D15** | - | N/C | **N/C** | Sensor de Pressão do Depósito de Combustível *(Apenas OBD2, eliminar)* |
| **D16** | - | D10 | **D10** | Detetor de Carga Elétrica (ELD) |
| - | A10 | - | **NOT REQ** | Pino TCU (Omitir) |
| - | D03 | D05 | **D08** | Saída Barométrica (BARO OUT) |
| - | D11 | B04 | **B04** | Sensor de Fluxo de Ar B |
| - | D13 | B03 | **B03** | Sensor de Fluxo de Ar A |
| - | D16 | A18 | **A19** | Saída de Rotação do Motor para a TCU |
| - | D18 | D18 | **D16** | Referência de Tensão do Sensor |

> [!NOTE]
> Os pontos de interrogação e os mapeamentos incertos da tabela de conversão arquivada foram preservados. Em particular, é indicado para não ligar o pino TCU A09 ao pino OBD2 A20, utilizando em alternativa o fio de teste do tacómetro. Verifique cada mapeamento com os manuais de serviço aplicáveis.

---

## 4. Referências de Contagem de Pinos

> [!WARNING]
> A contagem de pinos difere entre as fichas OBD1 e OBD2. A contagem incorreta de pinos é a causa mais comum de erros nas cablagens de conversão.

### Fichas OBD1, lado da ECU
Olhando diretamente para o **lado dos fios** da ficha (onde os fios entram na parte traseira do conector de plástico) com a patilha de bloqueio voltada para **Cima**:
* O **Pino 1** é o pino superior esquerdo.
* O **Pino 2** fica diretamente abaixo do Pino 1 (inferior esquerdo).
* Os pinos alternam as colunas à medida que conta para a direita (Ímpares em cima, Pares em baixo).

```
[ Patilha no Topo ]
|  1  |  3  |  5  |  7  |  9  | ...
|  2  |  4  |  6  |  8  |  10 | ...
```

### Fichas OBD2, lado da cablagem do motor
Olhando diretamente para o **lado frontal** da ficha (face de encaixe, oposta aos fios) com a guia da patilha de bloqueio voltada para **Cima**:
* Os pinos são contados sequencialmente ao longo da linha superior, da esquerda para a direita, e depois ao longo da linha inferior.

```
[ Patilha no Topo ]
|  1  |  2  |  3  |  4  |  5  |  6  | ...
|  7  |  8  |  9  |  10 |  11 |  12 | ...
```

---

## 5. Diretrizes de Comprimento da Cablagem

Para montar a ECU OBD1 e a TCU do Accord nas suas localizações de fábrica sob o painel lateral do lado do passageiro (kick panel), corte os seus fios de ponte para os seguintes comprimentos antes de crimpar os pinos dos terminais:
* **Fios de Interface da ECU**: 47 unidades cortadas a **11,4 cm (4,5 polegadas)** (vão do conector OBD2a para as fichas da ECU OBD1).
* **Fios de Interface da TCU**: 27 unidades cortadas a **53,3 cm (21,0 polegadas)** (vão da cablagem OBD2a para as fichas da TCU OBD1).
* **Pontes de ECU para TCU**: 5 unidades cortadas a **48,3 cm (19,0 polegadas)** (ligam sinais diretamente entre as fichas da ECU e da TCU, necessitando de terminais em ambas as extremidades).

---

## 6. Notas de Montagem da Cablagem

O guia arquivado fornece os seguintes detalhes de construção:

1. Dobre ou corte a direito os terminais em ângulo reto do conector OBD2a antes de soldar.
2. Corte os fios e crimpe os seus terminais antes de montar as fichas.
3. Crimpe as patilhas exteriores do terminal em volta do isolamento e as patilhas interiores em volta do fio descarnado. Não deixe que o fio descarnado se estenda para dentro do encaixe do terminal.
4. Utilize os terminais maiores para os pinos 1-6 e 23-26 da ficha A OBD1, e para os pinos 1-2 e 19-22 da ficha D OBD1. A ficha B utiliza terminais pequenos.
5. Mantenha o tempo de soldadura em `cada` terminal do conector OBD2 curto para evitar amolecer o plástico.
6. Isole os terminais soldados do conector OBD2 com manga termorretrátil.
7. Insira os terminais OBD1 com o lado da crimpagem voltado para a patilha de bloqueio da ficha.
8. Verifique a continuidade de cada ligação concluída antes de ligar a cablagem.

> [!WARNING]
> O guia arquivado indica que os terminais OBD1 são difíceis de remover depois de bloquearem numa ficha. Confirme `cada` destino antes de inserir.

## Ficheiros de conversão
* [Folha de Cálculo da Cablagem de Conversão de Accord Automático OBD2 para OBD1 e Bin de Base (ZIP)](AutoOBDconvertinfoandIntegrabin.zip)
