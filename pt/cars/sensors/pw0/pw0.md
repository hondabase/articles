---
summary: 'Um guia de referência completo de hardware e software para a ECU OBD0 PW0 DOHC VTEC JDM e europeia, apresentando calibrações de endereços ROM e mapeamento.'
tags: [ecu, vtec, reference]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: PW0
    url: /pgmfi/wiki/library/pw0
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Guia de Referência da ECU Honda PW0 OBD0

A Unidade de Controlo do Motor (ECU) PW0 é um controlador clássico OBD0 que equipou os Hondas do mercado doméstico japonês (JDM) e europeu de 1989 a 1991. Proveniente do Civic SiR JDM (EF9), CRX SiR (EF8) e Integra XSi/RSi (DA6), a PW0 controla o motor B16A de 1.6L DOHC VTEC de primeira geração.

## Visão Geral

Sendo uma das primeiras ECUs VTEC da Honda, a PW0 apresenta um layout interno robusto que inclui entradas duplas para sensores de detonação (nas versões JDM) e utiliza uma arquitetura de microcontrolador baseada em OKI. À semelhança da ECU [PR3](/cars/sensors/pr3) similar, a PW0 é altamente popular entre entusiastas que restauram ou afinam (tuning) Civics e CRXs de 4.ª geração.

Este guia lista os endereços ROM críticos para modificar parâmetros (tais como checksums, transições de VTEC e limites de rotação) tanto em ROMs PW0 JDM como de especificação europeia.

### Imagens da Placa da ECU & Hardware

Para reparações de hardware ou verificação de encaixe (socketing), consulte estas imagens da placa:
- [Vista de Componentes PW0 1](PW0-000_component1.jpeg)
- [Vista de Componentes PW0 2](PW0-000_component2.jpeg)
- [Circuito do Sensor de Detonação da PW0](PW0-000_knock.jpeg)
- [Pontos de Soldadura da PW0 (Vista Traseira)](PW0-E00_solder.jpeg)

---

## Mapa de Endereços ROM da PW0 JDM

Abaixo estão os desvios (offsets) de endereços hexadecimais na EEPROM para calibrações de PW0 JDM (ex.: ROMs PW0-000 padrão):

| Localização | Bytes | Descrição | Notas |
| :--- | :---: | :--- | :--- |
| **20B2** | 1 | Bypass de Checksum | Alterar de `0xC9` (executar checksum) para `0xCB` (ignorar checksum) para evitar luz de motor (CEL) acesa estática em ROMs modificadas |
| **391A** | 1 | Limitador de Rotação (Came Alta) | Corte de combustível por RPM com motor quente/VTEC (usa a fórmula de RPM de 8 bits OBD0) |
| **391C** | 1 | Limitador de Rotação (Came Baixa) | Corte de combustível por RPM em came baixa (usa a fórmula de RPM de 8 bits OBD0) |
| **3922** | 1 | Recuperação de Rotação (Came Alta) | RPM onde o corte de combustível do VTEC recupera |
| **3AD8** | 1 | Velocidade de Desativação do VTEC | Limite inferior de velocidade para corte do VTEC (usa a fórmula de VTEC OBD0) |
| **3AD9** | 1 | Velocidade de Ativação do VTEC | Limite de velocidade para ativação do VTEC |
| **3ADA** | 1 | RPM de Desativação do VTEC | Limite de histerese inferior de rotação da transição (3AD8 está tipicamente ativo) |
| **3ADB** | 1 | RPM de Ativação do VTEC | Ponto de ativação superior de rotação da transição (3AD9 está tipicamente ativo) |
| **3BE6** | 255 | Mapa de Ignição (Came Baixa) | Mapa de avanço de ignição 15x17 para came baixa (usa a fórmula de Ignição OBD0) |
| **3CE5** | 255 | Mapa de Ignição (Came Alta) | Mapa de avanço de ignição 15x17 para VTEC (a primeira linha é tipicamente preenchimento vazio) |
| **3DE4** | 255 | Tabela de Combustível (Came Baixa) | Mapa de consulta de combustível base 15x17 (usa a fórmula de Combustível OBD0) |
| **3EE3** | 15 | Multiplicadores de Came Baixa | Coeficientes multiplicadores de coluna para o mapa de combustível 1 |
| **3EF2** | 255 | Tabela de Combustível (Came Alta) | Mapa de consulta de combustível VTEC 15x17 (usa a fórmula de Combustível OBD0) |
| **3FF1** | 15 | Multiplicadores de Came Alta | Coeficientes multiplicadores de coluna para o mapa de combustível VTEC |

---

## Mapa de Endereços ROM da PW0 Europeia

Abaixo estão os desvios (offsets) de endereços hexadecimais na EEPROM para calibrações de PW0 de especificação europeia:

| Localização | Bytes | Descrição | Notas |
| :--- | :---: | :--- | :--- |
| **1F21** | 1 | Bypass de Checksum | Alterar de `0xC9` para `0xCB` para ignorar as verificações de checksum |
| **3928** | 1 | Limitador de Rotação (Came Alta) | Corte de combustível por RPM com motor quente/VTEC (usa a fórmula de RPM de 8 bits OBD0) |
| **392A** | 1 | Limitador de Rotação (Came Baixa) | Corte de combustível por RPM em came baixa (usa a fórmula de RPM de 8 bits OBD0) |
| **3930** | 1 | Recuperação de Rotação (Came Alta) | RPM onde o corte de combustível do VTEC recupera |
| **3AEC** | 1 | Velocidade de Desativação do VTEC | Limite inferior de velocidade para corte do VTEC (3AEC está tipicamente ativo) |
| **3AED** | 1 | Velocidade de Ativação do VTEC | Limite de velocidade para ativação do VTEC (3AED está tipicamente ativo) |
| **3AEE** | 1 | RPM de Desativação do VTEC | Limite de histerese inferior de rotação da transição |
| **3AEF** | 1 | RPM de Ativação do VTEC | Ponto de ativação superior de rotação da transição |
| **3BE6** | 255 | Mapa de Ignição (Came Baixa) | Mapa de avanço de ignição 15x17 para came baixa |
| **3CE5** | 255 | Mapa de Ignição (Came Alta) | Mapa de avanço de ignição 15x17 para VTEC |
| **3DE4** | 255 | Tabela de Combustível (Came Baixa) | Mapa de consulta de combustível base 15x17 |
| **3EE3** | 15 | Multiplicadores de Came Baixa | Coeficientes multiplicadores de coluna para o mapa de combustível 1 |
| **3EF2** | 255 | Tabela de Combustível (Came Alta) | Mapa de consulta de combustível VTEC 15x17 |
| **3FF1** | 15 | Multiplicadores de Came Alta | Coeficientes multiplicadores de coluna para o mapa de combustível VTEC |

---

## Fórmula do Multiplicador de Coluna de Combustível

Dado que os valores das células de 8 bits (escala de `0x00` a `0xFF` ou `0-255`) não conseguem cobrir uma amplitude de largura de pulso suficientemente ampla sem perder resolução, a ECU PW0 aplica um coeficiente multiplicador específico de coluna a cada coluna de carga:

$$\text{Multiplicador de Coluna} = \frac{2^{\text{Valor do Multiplicador}}}{4}$$

O valor final calculado da largura de pulso do injetor utiliza este multiplicador para dimensionar o valor bruto da célula do mapa de combustível na duração final de injeção comandada pela ECU. Consulte o [guia para compreender mapas](/cars/fueling/understanding-maps) para obter um exemplo passo a passo de dimensionamento de carga.
