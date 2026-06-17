---
summary: 'Guia técnico para injetores de combustível de baixa impedância (peak-and-hold), caixas de resistências em série e conversão entre tipos de injetores em motores Honda.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - injectors
  - fueling
  - hardware
sources:
  - name: 'pgmfi.org wiki'
    title: 'Low Impedance Injectors'
    url: /pgmfi/wiki/library/low-impedance-injectors
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Injetores de Baixa Impedância

Os injetores de baixa impedância, também referidos como **injetores peak-and-hold**, têm uma resistência interna da bobina muito baixa, tipicamente entre **2 e 6 ohms** (mais comummente 2,5 a 3 ohms em configurações Honda clássicas).

## Visão Geral

Ao contrário dos circuitos saturados, os injetores peak-and-hold são concebidos para abrir o mais rapidamente possível. Devido à sua baixa resistência da bobina, permitem que uma grande quantidade de corrente flua através do circuito quando são aplicados 12V. 

Para controlar esta corrente, os drivers da ECU de sistemas peak-and-hold genuínos utilizam um perfil de corrente de duas fases:
1.  **Fase de Pico (Peak Phase):** A ECU atinge o injetor com um impulso de corrente elevado (cerca de 4 amperes) para abrir rapidamente a agulha interna pesada.
2.  **Fase de Retenção (Hold Phase):** Uma vez aberto, a ECU reduz a corrente para um nível de retenção mais baixo (cerca de 1 ampere) para manter a válvula aberta durante o resto da largura de impulso.

Se ligar injetores de baixa impedância diretamente a um driver saturado padrão (encontrado na maioria das ECUs Honda Civic e Integra OBD1/OBD2) sem limitação de corrente, o fluxo excessivo de corrente irá sobreaquecer e queimar os transístores de driver internos da ECU em poucos minutos.

---

## A Solução da Caixa de Resistências

Para utilizar de forma segura injetores de baixa impedância numa ECU concebida para injetores de alta impedância (saturados), deve instalar uma **caixa de resistências em série** (também chamada de resistor pack).

A caixa de resistências adiciona aproximadamente **6 a 10 ohms** de resistência em série com o fio de alimentação de cada injetor. Isto eleva a resistência total do circuito para cerca de 10–13 ohms, imitando um injetor de alta impedância. Isto limita a corrente para um nível seguro (~1,2 amperes) e protege os drivers da ECU, embora sacrifique uma pequena parte da vantagem de velocidade de abertura de um circuito de driver peak-and-hold genuíno.

---

## Especificações

Abaixo encontram-se os veículos de fábrica comuns da Honda que vinham equipados com injetores de baixa impedância e as respetivas especificações:

| Motor / Veículo | Geração OBD | Taxa de Fluxo (cc/min) | Resistência Nominal | Caixa de Resistências de Fábrica? |
| :--- | :---: | :---: | :---: | :---: |
| **D16A6 (CRX/Civic Si)** | OBD0 | `240cc` | ~2,5 ohms | Sim |
| **B16A (JDM EF8/EF9)** | OBD0 | `240cc` | ~2,5 ohms | Sim |
| **H22A1 (Prelude VTEC)** | OBD1 | `345cc` | ~2,5 ohms | Sim |

---

## Referência de Cablagem da Caixa de Resistências

Uma caixa de resistências original (OEM) da Honda (tipicamente encontrada montada na parede de fogo do lado do condutor de um CRX Si ou Prelude) tem **5 fios** a sair dela:
*   **1 Fio de Alimentação (Vermelho):** Recebe alimentação de +12V comutada a partir do relé principal (main relay).
*   **4 Fios de Saída (Preto):** Ligam ao lado de alimentação de cada um dos quatro injetores de combustível.

```
                  Alimentação de +12V Comutada (do Relé Principal)
                            |
                     [ Caixa de Resistências ]
                       (Fio Vermelho)
                      /    |    \    \
                   [10Ω] [10Ω] [10Ω] [10Ω]  (Resistências Internas)
                    /      |      \      \
                (Preto) (Preto) (Preto) (Preto)  (Fios de Saída)
                  |        |        |        |
             [Inj 1]   [Inj 2]   [Inj 3]   [Inj 4]
                  |        |        |        |
             (Para os Pinos de Controlo de Massa da ECU A1, A3, A5, A2)
```

---

## Procedimento de Instalação

### Ligar uma Caixa de Resistências numa Cablagem Saturada (ex: Civic/Integra OBD1)

1.  **Localize a Junção de Alimentação dos Injetores:** Numa cablagem saturada de fábrica, todos os quatro injetores partilham um fio comum de fonte de alimentação de +12V (geralmente Amarelo/Preto) que se divide perto do coletor de admissão.
2.  **Corte os Fios de Alimentação:** Corte os fios de alimentação individuais Amarelo/Preto que vão para a ficha de cada injetor. Deixe os fios de retorno de massa (que vão para a ECU) intactos.
3.  **Monte a Caixa:** Monte a caixa de resistências de alumínio de forma segura na parede de fogo.
4.  **Ligue a Alimentação Comutada:** Ligue o único **fio Vermelho** da caixa de resistências ao fio principal de alimentação de +12V comutada vindo da cablagem do veículo.
5.  **Ligue as Saídas:** Ligue os **quatro fios Pretos** da caixa de resistências ao lado do injetor dos fios de alimentação Amarelo/Preto cortados (um fio Preto para cada injetor).
6.  **Solde e Isole:** Solde todas as ligações e isole-as com manga termorretrátil com adesivo de grau marítimo para as proteger da humidade do compartimento do motor.

---

## Relacionado

- [Injetores de alta impedância](/pt/cars/fueling/high-impedance-injectors)
- [Dimensionamento de injetores](/pt/cars/fueling/injector-sizing)
- [Introdução ao chipping de ECU](/pt/cars/rom/introduction-to-ecu-chipping)
