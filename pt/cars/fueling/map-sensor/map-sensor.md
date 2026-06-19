---
summary: 'O sensor Manifold Absolute Pressure (MAP) mede o vácuo e a pressão de sobrealimentação (boost) do motor, funcionando como a principal entrada de carga para o sistema de combustível speed-density da Honda.'
tags: [sensor, fueling]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Sensor MAP'
    url: /pgmfi/wiki/library/map-sensor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Sensor MAP

O sensor Manifold Absolute Pressure (MAP) mede a pressão absoluta no interior do coletor de admissão em relação a um vácuo perfeito. A ECU utiliza estes dados para calcular a massa de ar e determinar a entrega de combustível apropriada.

## Visão Geral

Ao contrário dos sistemas Mass Air Flow (MAF), que medem diretamente o volume de ar admitido, os sistemas Honda PGM-FI utilizam um cálculo speed-density. Ao combinar a pressão do coletor de admissão (MAP) com a velocidade do motor (RPM) e a temperatura do ar de admissão (IAT), a ECU estima a massa de ar que entra nos cilindros.

### Sensor MAP Original Honda

O sensor MAP original da Honda é um sensor absoluto de 1,8 bar. Ele emite uma tensão linear em relação à pressão:
* **Chave ligada, Motor Desligado (Atmosférico):** ~2,85V

* **Limite de Leitura Máximo OBD0:** ~9,25 psi (1,63 bar absoluto / ~4,5V)

* **Limite de Leitura Máximo OBD1:** ~10,65 psi (1,73 bar absoluto / ~4,8V)

Devido à sua construção física de diafragma, o sensor não consegue atingir o retorno de referência completo de 5V, o que limita a sua leitura de pressão máxima. Se planeia utilizar níveis de sobrealimentação (boost) superiores a 9–10 psi, deve atualizar para um sensor MAP aftermarket (por exemplo, GM 3-Bar ou Motorola 2.5-Bar).

![Gráfico de tensão do sensor MAP original Honda](honda_stock_map_volt.jpg)

## Especificações

### Sensores MAP GM

Os sensores MAP GM 2-Bar, 2.25-Bar e 3-Bar podem ser calibrados medindo a tensão à pressão atmosférica e a um nível de sobrealimentação (boost) conhecido para calcular a inclinação linear.

* **Sensor GM 3-Bar:** Emite ~1,6V à pressão atmosférica (chave ligada, motor desligado).

![Identificação do sensor MAP GM](gm_mapsensor.jpg)
*Guia de identificação do sensor MAP GM.*

### Sensor Motorola 2.5 Bar (MPX4250AP)

* **Número de Peça Digi-Key:** `MPX4250AP-ND`

* **Número de Peça do Conector Pigtail Digi-Key:** `A19034-ND`

* **Nota de Pinout:** Os pinos 4, 5 e 6 são ligações internas e devem ser cortados ou deixados desligados. O pino 1 é indicado pelo entalhe no terminal.

![Sensor MAP Motorola 2.5 bar](motorola2.5barmap. JPG)
![Pinout da cablagem 2.5 bar](25barwiring5kp.jpg)

## Referência de Cablagem

### Cablagem do Sensor MAP GM

| Sinal | Cor do Fio Honda | Pino GM |
| :--- | :--- | :--- |
| **Referência +5V** | Amarelo/Vermelho | C |
| **Massa (GND)** | Verde/Branco (ou Verde) | A |
| **Sinal** | Branco (ou Vermelho/Verde) | B |

### Cablagem do Sensor MAP Motorola 2.5 Bar

| Pino Motorola | Descrição | Ligação |
| :--- | :--- | :--- |
| **Pino 1 (Vout)** | Sinal | Ligar ao fio de sinal de referência do MAP original (Branco) |
| **Pino 2 (GND)** | Massa (GND) | Ligar ao fio de massa do MAP original (Verde) |
| **Pino 3 (Vs)** | Alimentação +5V | Ligar ao fio de referência de 5V do MAP original (Amarelo/Vermelho) |

## Procedimento

### Instalar um Sensor MAP Motorola 2.5 Bar Aftermarket

1. **Localizar a cablagem original:** Rode a chave para a posição ON (motor desligado) e utilize um multímetro digital (DVOM) para identificar os fios originais:
 

* **Alimentação 5V:** Emite exatamente 5V em relação à massa.
 

* **Massa (GND):** Mostra continuidade para a massa do chassis.
 

* **Sinal:** Emite a tensão de retorno (aprox. 2,85V à pressão atmosférica).
2. **Fazer a emenda dos fios:** Em vez de cortar o conector de fábrica, faça a emenda nos fios logo atrás do conector. Isto permite-lhe reverter facilmente para o sensor MAP original, se necessário.
3. **Preparar o sensor Motorola:** Corte os pinos 4, 5 e 6 no sensor Motorola para evitar que entrem em contacto com qualquer outra coisa.
4. **Soldar as ligações:** Ligue o Pino 1 (Vout) ao fio de sinal do MAP original, o Pino 2 (GND) ao fio de massa, e o Pino 3 (Vs) ao fio de alimentação de 5V.
5. **Proteger as ligações:** Deslize manga termoretrátil ou envolva fita isoladora firmemente à volta de todos os pinos para os isolar da humidade e de curto-circuitos.
6. **Instalar a linha de vácuo:** Ligue uma mangueira de vácuo a partir de uma fonte no coletor de admissão ao bocal do sensor.
7. **Fixar o sensor:** Monte o novo sensor MAP de forma segura no compartimento do motor.
8. **Calibração da ECU:** Deve atualizar o ficheiro ROM/BIN da sua ECU com uma calibração adequada para o sensor de 2.5 Bar utilizando um editor de BIN (como o Crome ou Uberdata) antes de ligar o motor.
