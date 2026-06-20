---
summary: 'Guia técnico para injetores de combustível de alta impedância (saturados) nos motores Honda PGM-FI, explicando as suas propriedades elétricas, tipos de driver e compatibilidade.'
tags: [injectors, fueling, hardware]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'High Impedance Injectors'
    url: /pgmfi/wiki/library/high-impedance-injectors
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Injetores de Alta Impedância (High Impedance Injectors)

Os injetores de alta impedância, também conhecidos como **injetores saturados**, têm uma resistência interna da bobina relativamente alta, tipicamente variando entre **12 e 16 ohms**.

## Visão Geral

Nos sistemas de injeção de combustível, a ECU controla a entrega de combustível ligando o circuito do injetor à massa (terra) para abrir a válvula solenoide interna do injetor. Os injetores de alta impedância recebem o seu nome devido à forma como o circuito do driver da ECU opera: o driver aplica um sinal constante de 12V à bobina do injetor, e a corrente "satura" a bobina, mantendo a válvula aberta durante o tempo de largura de pulso.

Devido à sua alta resistência, a corrente elétrica que flui pelo injetor é baixa (cerca de 1 ampére). Esta corrente baixa gera um calor mínimo nos drivers de injetor internos da ECU, permitindo que a ECU controle os injetores diretamente, sem a necessidade de resistências em linha (resistor box) ou circuitos de driver especializados.

---

## Evolução nos Motores Honda

O uso de injetores por parte da Honda evoluiu ao longo das diferentes gerações OBD:

* **OBD0 MPFI (motores D/B-series 1988–1991):** Utilizavam de fábrica injetores de **baixa impedância** (2–3 ohms), que exigiam uma caixa de resistências (resistor box) em linha para limitar a corrente e evitar queimar os drivers da ECU.

* **OBD1 (motores D/B/H-series 1992–1995):** Os modelos Civic e Integra transitaram para injetores de **alta impedância** (saturados), ligando diretamente à cablagem sem caixa de resistências. (O Prelude H22/H23 continuou a ser de baixa impedância com uma caixa de resistências de fábrica).

* **OBD2 (motores D/B/H/F-series 1996–2001):** Todos os modelos Honda transitaram para injetores saturados de alta impedância.

* **K-Series (2001+):** Utilizam injetores modernos de alta impedância com conectores de ficha atualizados.

---

## Especificações

Os injetores de alta impedância são altamente fiáveis e amplamente utilizados em configurações originais e aftermarket. Abaixo encontram-se as especificações dos injetores de alta impedância de fábrica comuns da Honda:

| Motor / Veículo | Geração OBD | Caudal (cc/min) | Resistência Nominal |
| :--- | :---: | :---: | :---: |
| **D16Z6 (Civic EX/Si)** | OBD1 | `240cc` | ~12.5 ohms |
| **B18C1 (Integra GS-R)** | OBD1 / OBD2 | `240cc` | ~12.5 ohms |
| **H22A4 (Prelude VTEC)** | OBD2 | `290cc` | ~13.0 ohms |
| **K20A2 (RSX Type-S)** | K-Series | `310cc` | ~12.0 ohms |
| **S2000 (F20C/F22C)** | OBD2 | `360cc` | ~12.5 ohms |

---

## Referência de Ligação (Cablagem)

Os injetores de alta impedância são ligados num esquema simples e direto. Cada injetor recebe uma fonte de alimentação comutada de +12V, e a sua linha de retorno à massa liga-se diretamente a um pino dedicado na ECU.

```
 Alimentação Comutada +12V (do Relé Principal)
 |
 +--------+--------+
 | |
 [Injetor 1] [Injetor 2]...
 | |
 | |
 Pino INJ1 da ECU Pino INJ2 da ECU... (ECU liga à massa para acionar)
```

Não existem caixas de resistências em linha ou módulos de drivers externos num circuito de injetores saturados.

---

## Vantagens e Diretrizes para Projetos Modernos

### Vantagens:

* **Cablagem mais Simples:** Não é necessária caixa de resistências, reduzindo pontos de falha e limpando o cofre do motor.

* **Menos Calor:** Gera menos calor tanto no corpo do injetor como nos drivers da ECU.

* **Tecnologia Moderna:** Os injetores aftermarket de melhor qualidade disponíveis atualmente (como os Injector Dynamics ID1050x ou os injetores Fuel Clinic) são de alta impedância. A fabricação moderna permite que estes injetores de alta impedância debitem grandes quantidades de caudal (1000cc/min+) mantendo um excelente controlo de ralenti e tempos de resposta rápidos.

### Dica de Conversão:

Se estiver a converter um chassis OBD0 (que possui uma caixa de resistências de fábrica) para funcionar com uma ECU OBD1 com injetores de alta impedância, deve **remover a caixa de resistências** e unir os fios de alimentação (conhecido como "eliminação da caixa de resistências" ou "resistor box delete"). Caso não contorne a caixa de resistências, a ativação dos injetores será fraca, resultando em condições de mistura extremamente pobre porque a resistência total do circuito será demasiado elevada.

---

## Relacionado

- [Injetores de baixa impedância](/cars/fueling/low-impedance-injectors)
- [Dimensionamento de injetores](/cars/fueling/injector-sizing)
- [Introdução à alteração de ECUs (ECU chipping)](/cars/tuning/introduction-to-ecu-chipping)
