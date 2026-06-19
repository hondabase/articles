---
summary: 'Um sensor piezoelétrico que permite à ECU ouvir a detonação e atrasar o ponto de ignição para proteger o motor.'
tags: [knock, sensor, ignition]
applies_to:
  engines: [B-Series, H-Series]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Knock Sensor'
    url: /pgmfi/wiki/library/knock-sensor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Sensor de Detonação

Um sensor de detonação é um "microfone" piezoelétrico aparafusado ao bloco do motor que escuta o ruído metálico de alta frequência da pré-ignição (detonação). A ECU utiliza o seu sinal para detetar a detonação e proteger o motor.

## Onde é utilizado

Os sensores de detonação são instalados em motores DOHC VTEC, tais como o B16, B18C e H22, e em motores SOHC VTEC OBD2.

## Como funciona

O sensor alimenta um circuito dedicado de deteção de detonação (a "placa de detonação" / knock board) dentro da ECU, que monitoriza a frequência de detonação do motor. Quando deteta detonação, a ECU pode atrasar o ponto de ignição para proteger o motor.

## Limitações em configurações sobrealimentadas (turbo/compressor)

A placa de detonação de fábrica é amplamente considerada pouco fiável para detetar a detonação em motores sobrealimentados (indução forçada). Na prática, atua como uma salvaguarda básica contra combustível de má qualidade, em vez de ser um sistema de deteção de detonação preciso, e pode reportar falsos positivos com componentes internos forjados.

> [!TIP]
> Numa preparação sobrealimentada, o sensor original é normalmente emparelhado com um dispositivo de deteção de detonação pós-venda dedicado (por exemplo, um J&S Safeguard) para uma proteção precisa.

## Relacionado

- [Tensões do sensor de detonação](/cars/sensors/knock-sensor-voltages)
- [Códigos de erro da ECU](/cars/diagnostics/diagnostic-trouble-codes)
