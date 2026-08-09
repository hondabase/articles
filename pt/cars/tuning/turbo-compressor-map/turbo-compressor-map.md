---
summary: 'Guia para ler e interpretar mapas de compressores de turbocompressores para adequar os turbocompressores aos objetivos de performance do motor Honda.'
tags: [tuning, sensors, reference]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Turbo Compressor Map'
    url: /pgmfi/wiki/library/turbo-compressor-map
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Mapa do Compressor do Turbo (Turbo Compressor Map)

Um mapa de compressor de turbocompressor ilustra as características operacionais da combinação da carcaça e rotor do compressor. Ler um mapa de compressor permite determinar a eficiência, os limites de fluxo de ar e os limites de pressão para adequar corretamente o turbo ao seu motor Honda e aos seus objetivos de potência.

![Mapa do Compressor T-3 Super 60](t3-60.jpg)
*Exemplo de Mapa do Compressor Garrett T3 Super 60*

## Parâmetros Principais de um Mapa de Compressor

### 1. Relação de Pressão (Eixo Y)

O eixo vertical (eixo Y) representa a **Relação de Pressão (Pressure Ratio - PR)** do compressor. Esta é a relação entre a pressão absoluta de descarga e a pressão absoluta de admissão:

$$\text{Relação de Pressão} = \frac{\text{Pressão Alvo (PSI)} + \text{Pressão Atmosférica (14,7 PSI)}}{14,7\text{ PSI}}$$

**Exemplo de Cálculo (Pressão Alvo de 15 PSI):**
1. Somar a pressão atmosférica: $15\text{ PSI} + 14,7\text{ PSI} = 29,7\text{ PSI absolutos}$
2. Dividir pela pressão ambiente: $29,7 / 14,7 = 2,02$

Uma pressão alvo de 15 PSI corresponde a uma Relação de Pressão de **2,02** no eixo Y.

### 2. Fluxo de Ar (Eixo X)

O eixo horizontal (eixo X) representa o fluxo de massa de ar através do compressor, medido normalmente em **libras por minuto (lb/min)** ou **pés cúbicos por minuto (CFM)**.

- **Estimativa de Potência:** Como regra geral, **1 lb/min de fluxo de ar $\approx$ 10 cv no volante (flywheel hp)**. Certifique-se de contabilizar as perdas da transmissão ao estimar a potência à roda.
- **Conversão de CFM para lb/min:** Multiplique o valor em CFM por 0,075 para obter lb/min:
  $$\text{lb/min} = \text{CFM} \times 0,075$$
- **Diferenciação de Gráficos:** Os gráficos em CFM têm números no eixo X na ordem das centenas (ex.: 400 CFM), enquanto os gráficos em lb/min têm números na ordem das dezenas (ex.: 30 lb/min).

### 3. Ilha de Eficiência

Os anéis concêntricos fechados no gráfico representam a eficiência adiabática do compressor (ex.: 75%, 72%, 70%, 65%). O anel mais interno é a **ilha de eficiência máxima**.

> [!TIP]
> Dimensionamento ideal: procure que a faixa de RPM principal e a pressão alvo do seu motor fiquem posicionadas diretamente na ilha de maior eficiência (70%+).

### 4. Anéis de Eficiência Externos

À medida que os pontos de operação se afastam da ilha central para os anéis externos, a eficiência diminui. Uma menor eficiência significa que mais calor é transferido para o ar de admissão para uma dada pressão, reduzindo a densidade de oxigénio e aumentando o risco de detonação (knock).

### 5. Limite de Surge (Surge Limit)

A linha limite inclinada à esquerda do gráfico representa o **limite de surge**.

> [!WARNING]
> Operar à esquerda da linha de surge ocorre quando a saída do compressor excede a capacidade volumétrica do motor para esse nível de pressão. O fluxo de ar descola das pás do compressor, causando oscilações violentas de pressão, surge do compressor, desgaste severo nos rolamentos e picos térmicos.

### 6. Limite de Estrangulamento / Choke (Overspin Choke)

A linha limite à extrema direita do gráfico representa o **choke**.

Operar à direita deste limite significa que a turbina compressora é demasiado pequena para o fluxo de ar pretendido. A velocidade do ar através da entrada do compressor atinge o limite da velocidade do som, fazendo com que a eficiência colapse, a temperatura do ar de saída aumente drasticamente e a potência estabilize independentemente do aumento de RPM.

### 7. Linhas de Rotação do Compressor

As linhas curvas horizontais ao longo do mapa indicam a velocidade de rotação do veio em **RPM** (ex.: 100.000 a 150.000+ RPM). Velocidades de veio mais elevadas geram temperaturas de saída significativamente mais quentes.

> [!NOTE]
> Temperaturas de admissão mais elevadas reduzem a densidade do ar. A instalação de um intercooler frontal (FMIC) eficiente é essencial para arrefecer o ar comprimido antes de chegar ao corpo de borboleta.

## Recursos Adicionais

Para bases de dados de desempenho de compressores e fichas técnicas de fabricantes:
- [BorgWarner Turbochargers](https://www.borgwarner.com)

