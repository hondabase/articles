---
summary: 'Um guia para calibração segura do avanço da ignição em ECUs Honda. Saiba como o avanço da ignição afeta a pressão no cilindro, o binário e a segurança do motor.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - tuning
  - ignition
  - maps
sources:
  - name: 'pgmfi.org wiki'
    title: 'Tuning Timing'
    url: /pgmfi/wiki/library/tuning-timing
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Ajustar o Avanço da Ignição em ECUs Honda

Ajustar o avanço da ignição (tuning timing) requer uma compreensão profunda da mecânica do motor e da química da combustão. Ao contrário da afinação de combustível, que pode ser monitorizada diretamente com uma [sonda lambda de banda larga (wideband O2)](/cars/fueling/wide-band-o2), não existe um sensor único que apresente o avanço de ignição "correto". A calibração deve ser abordada de forma sistemática para maximizar o binário, evitando simultaneamente danos no motor causados por detonação (grilar/knock).

---

## 1. O Objetivo do Avanço da Ignição: Pressão de Pico do Cilindro

O objetivo de avançar o ponto de ignição não é simplesmente iniciar a faísca mais cedo, mas sim temporizar o processo de combustão de modo a que a expansão dos gases gere a força máxima quando o pistão tem a maior alavancagem mecânica sobre a cambota (eixo de manivelas).

- **Duração da Combustão:** O combustível não explode instantaneamente; queima numa frente de chama controlada que demora algum tempo a propagar-se pela câmara de combustão.
- **Ponto de Pressão Ideal:** Para maximizar o binário de rotação na cambota, a Pressão Máxima no Cilindro (PCP - Peak Cylinder Pressure) deve ocorrer aproximadamente **12° a 16° Depois do Ponto Morto Superior (DPMS / ATDC)**.
- **Ângulo de Avanço:** Como o pistão se move rapidamente a rotações elevadas (RPM), a faísca deve ser disparada antes do pistão atingir o Ponto Morto Superior (APMS / BTDC) para garantir que a frente de chama acumule pressão no ângulo correto da cambota.

---

## 2. Fatores que Ditam os Requisitos de Avanço

Não existem duas configurações de motor que exijam o mesmo mapa de ignição. O nível de avanço necessário depende de:

- **Geometria da Câmara de Combustão:** Câmaras de combustão compactas de quatro válvulas com velas centralizadas (típicas de motores DOHC VTEC como o B16A ou H22A) queimam o combustível rapidamente e requerem *menos

* avanço do que câmaras mais antigas e menos eficientes.
- **Taxa de Compressão:** Pistões de alta compressão comprimem mais a mistura ar-combustível, acelerando a velocidade da frente de chama. Motores de alta compressão requerem *menos

* avanço de ignição para atingir a pressão máxima.
- **Octanagem do Combustível:** Combustíveis de maior octanagem queimam mais lentamente e são mais resistentes à autoignição (detonação), permitindo ao afinador avançar a ignição mais perto do limite mecânico do motor.
- **Geometria do Motor (Relação Biela-Curso):** A relação biela-curso (R/S) determina o tempo de permanência do pistão no PMS (ponto morto superior). Motores com tempos de permanência longos necessitam de curvas de avanço diferentes porque o pistão permanece no topo do cilindro durante mais tempo.

---

## 3. Os Componentes do Avanço Total

O avanço de ignição final ordenado pela ECU é uma combinação de sincronização mecânica, valores de consulta de tabelas (mapas) e tabelas de correção ambiental:

$$\text{Avanço de Ignição Total} = \text{Avanço Mecânico Base} + \text{Avanço do Mapa da ECU} + \text{Correções (Trims)}$$

### Avanço Mecânico Base

Antes que os cálculos de avanço da ECU possam ser precisos, o distribuidor físico deve ser sincronizado mecanicamente com a cambota.
- Para a maioria dos motores Honda Série D e B de tecnologia OBD1, o avanço mecânico base é ajustado para **16° $\pm$ 2° APMS (BTDC)** (os modelos JDM podem variar; consulte a placa de especificações do motor).
- Para calibrar o avanço base, efetue um shunt no terminal de diagnóstico [Service Connector Switch (SCS)](/cars/wiring/obd) para desativar os ajustes dinâmicos do mapa da ECU, ligue uma pistola de ponto (lâmpada estroboscópica) ao cabo da vela do cilindro #1 e rode o corpo do distribuidor até que a marca vermelha de ponto na polia da cambota coincida com o ponteiro no bloco do motor.

### Avanço do Mapa da ECU

Este é o valor de avanço de ignição alvo obtido a partir da tabela de consulta da ECU, correspondente à rotação atual do motor (RPM) e à pressão do coletor (carga/MAP).

### Correções (Trims)

A ECU aplica multiplicadores de compensação para proteger o motor em condições de funcionamento extremas. For example, se a [Temperatura do Ar de Admissão (IAT)](/cars/sensors/intake-air-temperature-sensor) ou a [Temperatura do Líquido de Refrigeração do Motor (ECT)](/cars/sensors/ecu-sensors) subirem acima dos limites de segurança, a ECU atrasa automaticamente o avanço para suprimir a detonação.

---

## 4. Afinação para MBT vs. Limite de Detonação

Ao calibrar o avanço num dinamómetro, procura-se o ponto de **Binário Máximo de Travagem (MBT - Maximum Brake Torque)** — o avanço de ignição que produz a maior força de binário.

- **Limite de Detonação (Grilar / Knock):** Com combustível comercial (como gasolina de 95 ou 98 octanas), motores sob carga elevada ou sobrealimentados (turbo/compressor) atingem frequentemente o limite de detonação antes de alcançarem o MBT. Quando a detonação é detetada, o avanço deve ser atrasado para evitar falhas catastróficas nas zonas entre segmentos dos pistões (ring lands) ou nos bronzes de biela.
- **Os Perigos de Atrasar Demasiado o Ponto:** Embora atrasar o avanço previna a detonação, retirar avanço em excesso faz com que a combustão ocorra demasiado tarde no ciclo de expansão ou até mesmo dentro do coletor de escape. Isto resulta em:
 - Perda severa de binário e potência do motor.
 - Picos de Temperatura dos Gases de Escape (EGT), que podem derreter caixas de turbo, válvulas de escape e pistões.
 - Temperaturas elevadas do líquido de refrigeração e sobreaquecimento da cabeça do motor.

## Artigos Relacionados

- [Como Interpretar Mapas da ECU](/cars/fueling/understanding-maps)
- [Introdução ao Tuning de ECUs](/cars/fueling/ecu-tuning)
- [Guia do Sensor de Posição da Cambota](/cars/ignition/crankshaft-position-sensor)
