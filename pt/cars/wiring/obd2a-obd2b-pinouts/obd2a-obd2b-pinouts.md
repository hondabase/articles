---
summary: 'Guia completo de pinagem das ECUs Honda OBD2A (1996-1998) e OBD2B (1999-2000) para modelos Civic, Integra e Del Sol.'
tags: [wiring, ecu, pinout, obd2a, obd2b, honda-tuning]
applies_to:
  models: [civic, crx, del-sol, integra]
  chassis: [ej8, ek4, ek9, dc2]
complexity: intermediate
---

# Referência de Pinagem das ECUs Honda OBD2A e OBD2B

Este guia de referência fornece tabelas detalhadas de pinagem para as Unidades de Controle do Motor (ECUs) Honda OBD2A (1996–1998) e OBD2B (1999–2000). Esses esquemas são essenciais para swaps de motor, conversões de chicote e instalação de injeções programáveis ou adaptadores de datalogging.

---

## Visão Geral dos Conectores

Os plugues do sistema Honda OBD2 dividem-se em conectores cinzas de múltiplos pinos:
*   **OBD2A (1996–1998):** Composto pelos conectores **A (31 pinos)**, **C (31 pinos)** e **D (16 pinos)**. (O conector B é não utilizado em ECUs OBD2A USDM).
*   **OBD2B (1999–2000):** Composto pelos conectores **A (32 pinos)**, **B (25 pinos)** e **C (31 pinos)**.

> [!IMPORTANT]
> Sempre verifique as cores dos fios no chicote do seu veículo antes de alimentar o sistema ou efetuar soldas, pois o posicionamento dos pinos pode variar ligeiramente entre os modelos USDM, JDM e EDM.

---

## Tabela de Pinagem OBD2A (1996–1998)

### Conector A (Chicote Principal - 31 Pinos)

| Pino | Cor do Fio | Sinal | Descrição |
| :--- | :--- | :--- | :--- |
| A1 | BRN | INJ1 | Saída do Injetor do Cilindro 1 |
| A2 | YEL | INJ2 | Saída do Injetor do Cilindro 2 |
| A3 | BLU | INJ3 | Saída do Injetor do Cilindro 3 |
| A4 | RED | INJ4 | Saída do Injetor do Cilindro 4 |
| A6 | BLK/RED | IACV | Negativo da Válvula de Controle de Marcha Lenta |
| A8 | GRN/YEL | VTS | Controle da Válvula Solenoide VTEC |
| A11 | PNK | MIL | Lâmpada de Anomalia (Check Engine) |
| A12 | BLK/RED | FANC | Saída do Relé da Ventoinha do Radiador |
| A23 | BLK | PG1 | Aterramento de Potência 1 |
| A24 | BLK | PG2 | Aterramento de Potência 2 |
| A25 | YEL/BLK | IGP1 | Alimentação de Ignição (+12V Pós-Chave) |

---

## Tabela de Pinagem OBD2B (1999–2000)

### Conector A (Chicote Principal - 32 Pinos)

| Pino | Cor do Fio | Sinal | Descrição |
| :--- | :--- | :--- | :--- |
| A1 | BRN | INJ1 | Pulsador de Terra do Injetor 1 |
| A2 | YEL | INJ2 | Pulsador de Terra do Injetor 2 |
| A3 | BLU | INJ3 | Pulsador de Terra do Injetor 3 |
| A4 | RED | INJ4 | Pulsador de Terra do Injetor 4 |
| A8 | GRN/YEL | VTS | Controle de Alimentação da Solenoide VTEC |
| A10 | BLK/RED | FANC | Saída do Relé da Ventoinha do Radiador |
| A17 | GRN/RED | MIL | Saída de Terra da Luz de Injeção |
| A23 | BLK | PG1 | Circuito de Terra de Potência |
| A24 | BLK | PG2 | Circuito de Terra de Potência |
