---
summary: 'Guia de pinagem e referência do chicote da ECU Honda PM6 OBD0 usada no Civic Si, CRX Si e Integra 1988-1991.'
tags: [wiring, ecu, pinout, obd0, pm6, honda-tuning]
applies_to:
  models: [civic, crx, integra]
  chassis: [ef, da]
complexity: intermediate
---

# Referência de Pinagem da ECU Honda OBD0 PM6

Este guia fornece a pinagem completa da Unidade de Controle do Motor (ECU) Honda PM6 usada nos modelos Civic Si, CRX Si (1988–1991) e Integra OBD0 (PR4). Abrange os três conectores do chicote da ECU: **A (26 pinos)**, **B (16 pinos)** e **C (22 pinos)**.

---

## Tabela do Conector A (Saídas e Alimentação - 26 Pinos)

| Pino | Cor do Fio | Sinal | Descrição |
| :--- | :--- | :--- | :--- |
| A1 | BRN | INJ1 | Pulsador de Terra do Injetor #1 |
| A2 | YEL | INJ3 | Pulsador de Terra do Injetor #3 |
| A3 | BLU | INJ2 | Pulsador de Terra do Injetor #2 |
| A4 | RED | INJ4 | Pulsador de Terra do Injetor #4 |
| A11 | BLK/RED | EACV | Válvula de Controle de Ar Eletrônica (EACV/IACV) |
| A13 | YEL/BLK | IGP1 | Alimentação da Chave de Ignição (+12V Pós-Chave) |
| A15 | YEL/BLK | IGP2 | Alimentação da Chave de Ignição (+12V Pós-Chave) |
| A16 | BLK | PG1 | Circuito de Aterramento de Potência |
| A18 | BLK | PG2 | Circuito de Aterramento de Potência |

---

## Tabela do Conector C (Sensores do Motor - 22 Pinos)

| Pino | Cor do Fio | Sinal | Descrição |
| :--- | :--- | :--- | :--- |
| C1 | YEL/RED | VCC1 | Alimentação 5V para Sensores |
| C7 | RED/BLK | TPS | Sinal do Sensor de Posição da Borboleta |
| C11 | WHT/RED | MAP | Sinal do Sensor de Pressão Absoluta (MAP) |
| C12 | RED/YEL | IAT | Sensor de Temperatura do Ar de Admissão |
| C13 | RED/WHT | TW | Sensor de Temperatura do Líquido de Arrefecimento |
| C14 | GRN/WHT | SG1 | Circuito de Terra dos Sensores |
