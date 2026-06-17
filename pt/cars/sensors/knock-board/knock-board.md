---
summary: 'Visão geral técnica da placa do sensor de detonação (knock board) da ECU OBD1 Honda, limitações em motores de alta performance e desativação por software.'
applies_to:
  obd: [1]
complexity: advanced
tags:
  - ecu
  - sensor
  - hardware
sources:
  - name: 'pgmfi.org wiki'
    title: 'Knock Board'
    url: /pgmfi/wiki/library/knock-board
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# A Placa do Sensor de Detonação (Knock Board) da ECU Honda OBD1

A knock board é uma pequena placa filha vertical (daughterboard) montada no canto superior direito das ECUs Honda OBD1 DOHC VTEC (como a P30 e a P72). Funciona como um módulo dedicado de processamento de sinal analógico, filtrando e interpretando a telemetria acústica do sensor de detonação (knock sensor) do bloco do motor.

---

## 1. Como Funciona

O sensor de detonação de fábrica é um sensor piezoelétrico não ressonante de um único fio. Funciona essencialmente como um microfone, captando as vibrações estruturais do bloco do motor. 

* **Filtragem Acústica:** A knock board contém circuitos de filtragem passa-banda calibrados para a frequência de ressonância da detonação para diâmetros de cilindro específicos (por exemplo, ~7 kHz para os motores de série B).

* **Sinalização do MCU:** Quando a amplitude do sinal filtrado excede um limite pré-determinado num ângulo específico da cambota, a knock board sinaliza o MCU principal. A ECU então atrasa o ponto de ignição para proteger o motor contra pré-ignição e detonação.

---

## 2. Limitações em Motores Preparados

Embora a knock board original funcione bem em motores atmosféricos originais que utilizam combustível de baixa octanagem, apresenta desvantagens significativas em aplicações de alta performance:

* **Ruído Mecânico (Componentes Internos Forjados):** Motores de alta performance reconstruídos com pistões forjados requerem maiores folgas entre o pistão e a parede do cilindro do que os pistões fundidos de fábrica. Isto cria ruído mecânico (piston slap) que a knock board frequentemente interpreta erroneamente como detonação. Isto faz com que a ECU atrase o ponto de ignição desnecessariamente, reduzindo a potência.

* **Indução Forçada (Boost):** Motores turbocomprimidos ou com compressor volumétrico geram maior ruído de combustão e vibrações harmónicas. A knock board original não está calibrada para estas frequências e níveis de ruído, tornando-se pouco fiável para detetar a detonação real sob pressão de sobrealimentação.

---

## 3. Desativar o Sensor de Detonação

Devido a estas limitações, é prática comum na reprogramação pós-venda (aftermarket tuning) desativar o ciclo de feedback do sensor de detonação.

* **Desativação por Software:** As plataformas de reprogramação (como Hondata, Crome ou Neptune) permitem desativar a rotina de verificação do sensor de detonação no código da ROM.

* **Remoção Física:** Uma vez desativado no software, a ECU ignora completamente a knock board. A placa filha física pode ser dessoldada e removida da caixa da ECU sem acionar a luz de avaria (Check Engine Light) do **Código 23 (Sensor de Detonação)**.

---

## 4. Patentes de Hardware

As knock boards das ECUs OBD1 P72 e P30 estão marcadas com várias patentes de semicondutores e processamento de dados. Curiosamente, várias destas patentes são partilhadas com outros dispositivos digitais do início da década de 1990 (como as impressoras Hewlett-Packard LaserJet), refletindo as patentes de fabrico de silício partilhadas da época:

* **Patente dos EUA 4,825,364:** Processador de dados monolítico com refrescamento de memória

* **Patente dos EUA 4,942,561:** Dispositivo de medição de tempo de atraso

* **Patente dos EUA 4,896,260:** Processador de dados com refrescamento de memória de circuito integrado

* **Patente dos EUA 4,829,419:** Controlo de máquinas por microcomputador

* **Patente dos EUA 4,954,951:** Sistema e método para aumentar o desempenho da memória

* **Patente dos EUA 4,686,622:** Arquitetura de sistema de computador usando comunicação em série
