---
summary: 'Uma introdução ao TurboEdit, o software livre e de código aberto para edição de ROM e afinação (tuning) de ECUs Honda OBD0 (bases de código PM6/PM7).'
tags: [tuning, software]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Turbo Edit'
    url: /pgmfi/wiki/library/turbo-edit
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Introdução ao TurboEdit (Afinação de Honda OBD0)

O TurboEdit é uma suite de software livre e de código aberto para edição de ROM e afinação (tuning) concebida especificamente para Unidades de Controlo do Motor (ECUs) Honda OBD0 Multi-Point Fuel Injection (MPFI) de primeira geração. É a principal plataforma utilizada para afinar modelos Honda Civic e CRX de 1988–1991 sem converter a cablagem do chassis do veículo para os padrões OBD1 mais recentes.

---

## 1. ECUs e Bases de Código Suportadas

O TurboEdit tem como alvo os microcontroladores baseados em OKI encontrados nas ECUs Honda OBD0:

- **PM6:** A ECU USDM originária do Civic/CRX Si de 1988–1991 (equipado com o motor SOHC D16A6).
- **PM7 / PP5:** Originárias de modelos JDM e europeus equipados com motor DOHC ZC.

Como as ECUs OBD0 de origem nunca foram concebidas para lidar com sobrealimentação (boost) ou comunicação em tempo real, o TurboEdit depende de bases de código ROM modificadas com patches personalizados (sendo as mais notáveis as bases de código **NG69** e **NG22**). Estes patches reescrevem secções do código de fábrica para adicionar suporte para indução forçada (turbo/compressor), injetores maiores e datalogging por porta série.

---

## 2. Principais Características do TurboEdit

O TurboEdit transforma uma ECU OBD0 padrão num sistema de gestão de motor totalmente programável:

### Escala do Sensor MAP

Os sensores MAP originais da Honda apenas leem até à pressão atmosférica (1-bar). O TurboEdit permite-lhe calibrar as colunas de pressão do mapa (escaladores de MAP) para suportar sensores MAP pós-venda de 2-bar ou 3-bar (como os sensores GM ou Motorola), permitindo que a ECU calcule o combustível e a ignição sob pressão (boost).

### Calibração de Atraso de Ignição sob Pressão (Boost Retard)

Sob indução forçada, o ponto de ignição deve ser atrasado para evitar a detonação (knock). O TurboEdit permite aos preparadores definir uma rampa de atraso de ponto (por exemplo, retirar 0,75° de ponto por cada psi de boost) à medida que a pressão sobe nas colunas de carga positiva. Consulte o [guia de ponto de ignição](/cars/ignition/tuning-timing) para diretrizes seguras de atraso.

### Ajuste do Multiplicador de Combustível (Escala de Injetores)

A ECU OBD0 calcula a entrega de combustível utilizando um valor de mapa de 8 bits e um multiplicador específico para cada coluna. Ao atualizar para injetores de combustível maiores (como os injetores padrão DSM de 450cc), os multiplicadores de fábrica enviarão demasiado combustível. O TurboEdit permite ajustar esses multiplicadores de combustível para reduzir a escala de todo o mapa de combustível, correspondendo ao débito dos injetores maiores.

### Programação em Tempo Real (RTP)

Com emuladores de hardware (como o Moates Ostrich ou o Xtronics Pocket ROMulator) ligados ao socket de ROM de 28 pinos da ECU, o TurboEdit permite modificar a injeção, o ponto e os limites de rotação dinamicamente enquanto o motor está a funcionar.

---

## 3. Resolução de Problemas Comuns em Afinação OBD0

Ao afinar com o TurboEdit, tenha em atenção estas limitações comuns de hardware do padrão OBD0:

- **Luz de Motor Acesa Fixa (Modo de Emergência / Limp Mode):** A modificação de qualquer byte na ROM altera a sua soma de verificação (checksum). Se não aplicar o patch de desvio do checksum (alterando o byte de checksum no endereço `20B2` nas [ECUs PW0](/cars/sensors/pw0) ou na localização correspondente nas ECUs PM6), a ECU apresentará uma luz de motor (CEL) fixa e entrará em modo de emergência (limp-home).
- **Ruído no Sinal de Datalogging:** As ECUs OBD0 não têm um chip de buffer dedicado nas linhas de série como as ECUs OBD1. Os sinais de datalogging são altamente sensíveis ao ruído elétrico dos cabos das velas. Encaminhe sempre os cabos de série longe do distribuidor e das velas de ignição.

## Artigos Relacionados

- [Visão Geral das Gerações OBD da Honda](/cars/wiring/obd)
- [Como Interpretar Mapas de Combustível e Ignição](/cars/fueling/understanding-maps)
- [Metas de Referência para Combustível e Ponto de Ignição](/cars/fueling/ecu-tuning)
