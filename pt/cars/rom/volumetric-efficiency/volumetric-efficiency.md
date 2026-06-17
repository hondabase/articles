---
summary: 'A Eficiência Volumétrica (VE) é uma comparação do volume real da mistura ar/combustível admitida com o volume real do cilindro se este estivesse completamente cheio.'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
sources:
  - name: 'pgmfi.org wiki'
    title: 'Volumetric Efficiency'
    url: /pgmfi/wiki/library/volumetric-efficiency
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Eficiência Volumétrica

A [Eficiência Volumétrica](/cars/rom/volumetric-efficiency) (VE - Volumetric Efficiency) é uma comparação do volume real da mistura ar/combustível admitida com o volume real do cilindro se este estivesse completamente cheio. "Eficiência de Bombeamento" é outro sinónimo. Os valores típicos para motores atmosféricos (naturalmente aspirados) situam-se em torno de 80%. Os motores turboalimentados (turbo) e sobrealimentados (compressor/supercharger) têm quase sempre uma VE superior a 100%. As tabelas de combustível presentes nas [ECU](/cars/ecu/ecu)s Honda são (de uma forma ligeiramente indireta) tabelas de eficiência volumétrica. O valor de VE é armazenado como o resultado da VE multiplicado pelo fluxo de ar máximo teórico, corrigido para o tamanho do injetor para obter a [Relação Ar/Combustível](/cars/fueling/air-fuel-ratio) (Air Fuel Ratio) desejada, ou seja, **Tamanho do Injetor x VE x Possibilidade Teórica de Bombeamento** (assumindo a temperatura e pressão atmosférica para condições da [Lei dos Gases Ideais](/cars/rom/ideal-gas-law)). Isto é apenas um atalho para evitar que a [ECU](/cars/ecu/ecu) tenha de efetuar todos os cálculos da lei dos gases ideais e depois multiplicar pela VE para obter o fluxo de ar, e depois multiplicar novamente por um fator para contabilizar o tamanho do injetor. A correção do [Sensor de Temperatura do Ar de Admissão](/cars/sensors/intake-air-temperature-sensor) (IAT) é então utilizada para ajustar o fornecimento de combustível de modo a corresponder à temperatura real do ar de admissão, em vez daquela que foi assumida na criação da tabela de VE.
