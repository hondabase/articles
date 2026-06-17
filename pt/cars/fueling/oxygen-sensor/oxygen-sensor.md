---
summary: 'Como funciona o sensor de oxigénio de banda estreita (narrowband) de origem, resolução de problemas de CELs do sensor de O2 e conversão entre sensores de 1 fio e 4 fios.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - sensor
  - combustivel
  - diagnosticos
sources:
  - name: 'pgmfi.org wiki'
    title: 'Oxygen Sensor'
    url: /pgmfi/wiki/library/oxygen-sensor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Sensor de Oxigénio (O2)

O sensor de oxigénio (O2) mede o teor de oxigénio nos gases de escape. A ECU utiliza esta leitura para determinar se o motor está a funcionar com uma mistura rica ou pobre e ajusta a entrega de combustível no modo de malha fechada (closed-loop) para manter o equilíbrio estequiométrico.

## Visão Geral

A Honda utilizou vários estilos de sensores de oxigénio ao longo de diferentes gerações:
*   **Sensor de 1 Fio (OBD0 / Primeiros OBD1):** Um sensor simples de banda estreita (narrowband) sem aquecimento. Depende unicamente do calor dos gases de escape para atingir a sua temperatura de funcionamento (cerca de 315°C / 600°F).
*   **Sensor de 4 Fios (OBD1 / OBD2):** Contém um elemento de aquecimento interno alimentado pelo sistema elétrico do carro para aquecer o sensor rapidamente e manter leituras estáveis mesmo ao ralenti ou sob cargas leves.
*   **Sensor Wideband de 5 Fios (L1H1 / LAF):** Utilizado em motores de combustão pobre (lean-burn), como o Civic VX (1992–1995) e o Civic HX (1996–1998). Ao contrário dos sensores de banda estreita, consegue medir a relação ar-combustível (AFR) numa gama ampla (desde extremamente pobre a rica).

### Características da Saída de Banda Estreita (Narrowband)
Os sensores padrão de 1 fio e 4 fios são sensores de banda estreita (lambda). São projetados para detetar apenas uma relação específica: a estequiométrica (**relação ar-combustível de 14.7:1**).
*   **Estequiométrica (14.7:1):** Saída de exatamente **0.45V**.
*   **Rica (AFR < 14.7):** A tensão de saída sobe (até cerca de ~0.9V–1.0V).
*   **Pobre (AFR > 14.7):** A tensão de saída desce (até cerca de ~0.1V).

Como a curva de tensão de saída é extremamente íngreme em torno do ponto de 14.7:1, o sensor funciona como um interruptor binário (rico/pobre). A ECU não consegue determinar *quão* rica ou *quão* pobre a mistura está a ser queimada a partir de um sensor de banda estreita; apenas sabe de que lado da estequiometria se encontra.

![Curva de saída do sensor de O2 lambda de banda estreita](honda_stock_o2sensor.jpg)
*Curva típica de tensão de saída com transição acentuada de um sensor lambda de banda estreita.*

![Curva de saída do sensor de O2 de banda larga linear](honda_stock_o2sensor_linear.jpg)
*Curva linear de tensão de saída de um sensor de O2 de banda larga (wideband).*

## Referência de Cablagem

### Converter Sensor de O2 de 1 Fio para 4 Fios
Ao efetuar uma conversão para OBD1 num chassis mais antigo (como um Civic EF ou Integra DA), frequentemente necessita de ligar um sensor de O2 aquecido de 4 fios à nova ECU OBD1 (por exemplo, P28 ou P30) para evitar códigos de avaria do circuito de aquecimento (Código 41).

| Pino / Fio do Sensor de O2 (4 Fios) | Função | Ponto de Ligação |
| :--- | :--- | :--- |
| **Branco** | Sinal | Ligar ao pino **D14** da ECU (Sinal de O2) |
| **Verde** | Massa do Sensor | Ligar ao pino **D22** da ECU (SG2 / Massa do Sensor) |
| **Preto (Aquecedor)** | Alimentação +12V | Ligar a uma fonte de 12V pós-chave (por exemplo, fio Amarelo/Preto no distribuidor ou no relé principal) |
| **Preto (Aquecedor)** | Controlo do Aquecedor | Ligar ao pino **A6** da ECU (Controlo de massa do aquecedor) |

## Relacionado

*   [Sensor MAP](/cars/fueling/map-sensor)
*   [Sensor de Posição da Borboleta (TPS)](/cars/diagnostics/tps-sensor)
*   [Códigos de Avaria da ECU](/cars/diagnostics/ecu-trouble-codes)
