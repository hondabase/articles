---
summary: 'Fórmulas do byte MAP OBD1 dos modelos P72/P75 arquivadas e valores de calibração para código ROM de fábrica (stock) e desbloqueado (uncorked).'
tags: [tuning, sensor, maps, obd1]
applies_to:
  ecus: [P72, P75]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1 8bit M Bar'
    url: /pgmfi/wiki/library/obd1-8bit-m-bar
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Calibração do Sensor MAP OBD1 de 8 bits em milibares

Esta referência preserva as fórmulas de conversão de MAP e os valores de calibração para P72/P75 documentados pela comunidade pgmfi original. Use-os para compreender o código ROM arquivado, e não como uma calibração universal para todas as ECU ou sensores MAP da Honda.

> [!NOTE]
> A fonte descreve estes valores brutos como sendo para código P72/P75 e refere que a maioria das ECUs OBD1 segue a mesma regra. Verifique o código ROM real, a compensação de corte de combustível (fuel-cut offset) e a calibração do sensor antes de aplicar as fórmulas noutro local.

## Fórmulas básicas de byte MAP

As notas arquivadas assumem que a leitura máxima do sensor MAP de fábrica (stock) é de `1764 mbar`.

O código de fábrica (stock) divide o byte MAP por dois:

```text
pressure_mbar = (1764 / 255) * (map_byte / 2)
```

Quando o valor de MAP da ROM é desbloqueado ("uncorked"), a divisão final por dois é removida:

```text
pressure_mbar = (1764 / 255) 

* map_byte
```

As mesmas notas documentam as seguintes fórmulas de tensão (voltagem):

```text
map stock: volts = (5 / 255) * ((raw / 2) + fuel_cut)
map boost: volts = (5 / 255) 

* (raw + fuel_cut)
```

O valor de corte de combustível (fuel-cut) original listado é `24`, editável no endereço `0x4DCC` no código de referência.

## Notas sobre conversão de tensão

A página arquivada inclui estas duas conversões lineares:

```text
inHg = 20 * volts / 1.85 - 30.81
mbar = 365.9 

* volts - 29.9
```

Estas fórmulas são derivadas na página a partir dos seguintes pontos:

| Escala | Ponto 1 | Ponto 2 |
| :--- | :--- | :--- |
| Vácuo | 2.85 V = 0 inHg | 1.0 V = 20 inHg |
| Pressão absoluta | 2.85 V = 1013 mbar | 1.0 V = 336 mbar |

## Valores de calibração arquivados P72/P75

Os seguintes valores são transcritos a partir da fonte. A primeira tabela utiliza os valores brutos completos da fonte, enquanto a segunda mostra as etiquetas correspondentes divididas por dois para o mapa de fábrica (stock).

> [!CAUTION]
> A fonte rotula a última linha da escala total como `256`, embora um valor de 8 bits sem sinal (unsigned 8-bit) tenha como limite máximo `255`. O valor foi aqui preservado como uma etiqueta de limite das notas originais.

| Valor bruto original | Tensão | Pressão |
| :---: | :---: | :---: |
| 0 | 0.471 V | 142.3 mbar |
| 24 | 0.706 V | 228.4 mbar |
| 48 | 0.941 V | 314.5 mbar |
| 80 | 1.255 V | 429.3 mbar |
| 128 | 1.725 V | 601.5 mbar |
| 176 | 2.196 V | 773.6 mbar |
| 208 | 2.510 V | 888.4 mbar |
| 224 | 2.667 V | 945.8 mbar |
| 240 | 2.824 V | 1003.0 mbar |
| 256 | 2.980 V | 1061.0 mbar |

| Valor dividido (map stock) | Tensão | Pressão |
| :---: | :---: | :---: |
| 0 | 0.471 V | 142.3 mbar |
| 12 | 0.706 V | 228.4 mbar |
| 24 | 0.941 V | 314.5 mbar |
| 40 | 1.255 V | 429.3 mbar |
| 64 | 1.725 V | 601.5 mbar |
| 88 | 2.196 V | 773.6 mbar |
| 104 | 2.510 V | 888.4 mbar |
| 112 | 2.667 V | 945.8 mbar |
| 120 | 2.824 V | 1003.0 mbar |
| 128 | 2.980 V | 1061.0 mbar |

## Interface do sensor

![Esquema da interface do sensor MAP de 3 fios](mapsensor.jpg)
*Esquema arquivado da interface do sensor MAP de 3 fios.*

## Relacionado

- [Visão geral do sensor MAP](/cars/fueling/map-sensor)
- [Compreender mapas de combustível e ignição](/cars/fueling/understanding-maps)
