---
summary: 'Esquema de cablagem, detalhes do pinout e análise de esquemas para a ECU OBD0 e OBD1 do Acura Integra PR4.'
tags: [ecu, pinout, schematic]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Acura Integra PR4ECU Pinout And Schematics'
    url: /pgmfi/wiki/library/acura-integra-pr4ecu-pinout-and-schematics
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Pinouts e Cablagem da ECU OBD0 Acura Integra PR4

A ECU OBD0 PR4 foi utilizada no Acura Integra de 1990 e 1991 equipado com o motor B18A1. Encontrar um esquema de pinout oficial e completo para esta ECU específica pode ser difícil, uma vez que muitos manuais de fábrica apenas mostram cablagens completas em vez da disposição individual dos conectores da ECU.

Ao analisar os esquemas de fábrica do sistema de controlo do motor do Integra de 1990–1991, as cores e funções dos fios podem ser cruzadas com os padrões gerais das ECUs OBD0 para mapear os pinos principais.

## Sinais dos Conectores Mapeados

Os seguintes pinos foram verificados utilizando códigos de cores de fios e caminhos elétricos padrão de OBD0:

### Recirculação de Gases de Escape (EGR) (Apenas Modelos da Califórnia)

Os modelos Integra de especificação da Califórnia equipados com transmissões automáticas possuem um sistema EGR. Estes utilizam as seguintes atribuições de pinos:
* **Pino A10:** Solenoide de Controlo EGR (fio Vermelho)

* **Pino `C8`:** Sensor de Elevação da Válvula EGR (fio Amarelo)

### Corte do Regulador de Pressão

Nos modelos com transmissão manual padrão e não-Califórnia, os pinos EGR são reutilizados ou omitidos:

* **Pino A10:** Válvula Solenoide de Corte do Regulador de Pressão (PRC) (fio Verde/Amarelo)

### Sinal do Interruptor de Direção

* **Pino `C9`:** Interruptor de Pressão da Direção Assistida (fio Vermelho), utilizado pela ECU para aumentar a velocidade de ralenti quando a carga da direção é elevada.

## Cablagem Não Resolvida e Pinos em Falta

Algumas ligações nos manuais de fábrica não se mapeiam diretamente para os pinos OBD0 padrão ou não estão totalmente documentadas:

* **Conector de Ligação de Dados (DLC):** O fio do Conector de Ligação de Dados OBD0 (Azul Claro) não está mapeado para um pino verificado na documentação padrão.

* **Sinais de Transmissão Automática:** As disposições dos pinos para os controlos de velocidades de transmissão automática e solenoides de bloqueio (lockup) são omitidas dos guias de cablagem padrão de transmissão manual.

* **Fios Terminados:** Dois fios da cablagem de fábrica (**Vermelho/Azul** e **Laranja/Preto**) aparecem nos esquemas, mas não se ligam a pinos ou sensores definidos nos modelos padrão.
