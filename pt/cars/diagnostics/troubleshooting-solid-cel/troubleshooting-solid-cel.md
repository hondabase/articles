---
summary: 'Como diagnosticar uma luz de verificação do motor (CEL/MIL) constantemente acesa em ECUs Honda OBD0/OBD1, o que normalmente indica o modo de emergência (limp mode) ou uma ROM/ligação defeituosa.'
applies_to:
  obd: [0, 1]
complexity: intermediate
tags:
  - ecu
  - diagnosticos
  - resolucao-de-problemas
sources:
  - name: 'pgmfi.org wiki'
    title: 'Troubleshooting Solid CEL'
    url: /pgmfi/wiki/library/troubleshooting-solid-cel
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Resolução de Problemas de uma CEL Acesa (Sólida)

Uma luz de verificação do motor (Check Engine Light - CEL/MIL) "sólida" (constantemente acesa) que se acende e permanece ligada imediatamente ao rodar a chave para a posição ON (sem apagar após 2 segundos) indica uma falha grave de hardware ou de software de baixo nível. Quando isto acontece, a ECU entra em "modo de emergência" (limp mode, correndo num processador de salvaguarda), o que normalmente faz com que o motor funcione de forma muito irregular, tenha um limite de rotação baixo ou se recuse a arrancar.

## Visão Geral

Durante o seu autoteste de arranque, o microcontrolador principal (MCU) da ECU realiza várias verificações de baixo nível. Numa ECU OBD0 ou OBD1, estas incluem:
*   Verificar os Registadores de Funções Especiais (SFRs) do MCU.
*   Verificar a integridade da RAM interna e externa.
*   Calcular e verificar a soma de controlo (Checksum - CS) do programa.
*   Verificar o funcionamento do conversor Analógico-Digital (A/D).
*   Verificar o chip de mapeamento 6260 (se equipado).

Se qualquer uma destas verificações de hardware ou software de baixo nível falhar, o MCU interrompe a execução e acende a CEL sólida. Em ECUs modificadas (socketed), **95% das situações de CEL acesa são causadas por um de dois problemas**:
1.  **ROM/Programa com Defeito:** Um ficheiro ROM corrompido, checksum incorreto ou uma gravação incorreta no chip EPROM.
2.  **Soldadura Inadequada:** Soldaduras frias, pontes de solda (curto-circuitos) ou circuitos abertos no suporte (socket), trinco lógico (`74HC373`) ou ligador (jumper) `J1` recentemente instalados.

## Procedimento

Siga estas instruções passo a passo para isolar e corrigir a causa de uma CEL sólida numa ECU OBD0 ou OBD1 modificada.

### Passo 1: Testar com uma ROM Original (Stock)
Elimine primeiro os problemas de software.
1.  Grave um programa original e não modificado para o seu tipo específico de ECU (por exemplo, um ficheiro bin original de P06 para uma ECU P06, ou um ficheiro bin original de P72 para uma ECU P72).
2.  *Se a ECU foi convertida para VTEC:* Experimente primeiro um programa original para a configuração de hardware não-VTEC original e, em seguida, um programa P28 original.
3.  Instale o chip e alimente a ECU (no carro ou numa bancada).
4.  Observe a CEL e ouça a bomba de combustível:
    *   **Comportamento Normal:** A CEL deve acender-se, a bomba de combustível deve pressurizar a rampa de injeção durante 2 segundos e, em seguida, tanto a CEL como a bomba de combustível devem desligar-se.
    *   **Resultado:** Se a ECU se comportar normalmente com um programa original, a sua soldadura está correta. O problema reside na ROM personalizada que estava a tentar utilizar (por exemplo, checksum incorreto, base de código incompatível ou ficheiro bin corrompido).

### Passo 2: Efetuar o Teste do Jumper `J1` (Apenas OBD1)
Se a ECU ainda apresentar uma CEL sólida com uma ROM original que sabe estar em bom estado, teste o bypass de hardware.
1.  Localize o **jumper `J1`** na placa da ECU (que diz à ECU para ler a partir do chip EPROM externo em vez da sua ROM interna).
2.  Dessorva ou corte uma das pernas do jumper `J1`. Isto desativa o suporte do chip externo e reverte a ECU para a sua ROM interna de fábrica.
3.  Alimente a ECU.
    *   **Resultado A (Funcionamento normal):** Se a CEL sólida desaparecer, os circuitos internos da ECU estão em bom estado. O problema está definitivamente localizado no suporte do chip externo, no chip de trinco `74HC373` ou nas juntas de solda que os ligam.
    *   **Resultado B (A CEL sólida persiste):** Se a CEL permanecer sólida mesmo com o `J1` cortado, a própria ECU provavelmente está danificada (queimada) e poderá ter de ser substituída.

### Passo 3: Inspecionar e Testar a Soldadura
Se o teste do `J1` provou que a área do suporte externo é o problema, inspecione a placa.
1.  Limpe a parte superior e inferior do PCB em redor do suporte e do trinco lógico utilizando álcool isopropílico e uma escova de dentes para remover todos os resíduos de fluxo de solda.
2.  Use uma lupa ou uma lupa de relojoeiro sob luz brilhante para inspecionar cada junta de solda no suporte da EPROM, no trinco `74HC373` e em `J1`. Procure por:
    *   **Juntas frias:** Solda baça, cinzenta ou rachada que não fluiu corretamente.
    *   **Pontes de solda:** Pequenas gotas de solda a unir dois pinos adjacentes.
    *   **Falta de penetração:** Solda que não fluiu por completo através da via até ao lado superior da placa.
3.  Utilize um multímetro digital no modo de continuidade para seguir as ligações entre o suporte da EPROM, o trinco lógico e o MCU para garantir que não existem circuitos abertos ou pinos em curto-circuito.

### Passo 4: Verificar os condensadores de desacoplamento
Se adicionou condensadores de desacoplamento para filtragem de ruído (por exemplo, `C91` e `C92` em ECUs JDM P30):
*   Verifique a sua capacitância. A utilização de condensadores de desacoplamento demasiado grandes (por exemplo, 0.1µF em vez dos 0.00001µF / 10pF recomendados) pode mandar abaixo sinais como PSEN ou ALE, provocando uma CEL sólida.

## Relacionado

*   [Introdução ao Chipping de ECUs](/cars/rom/introduction-to-ecu-chipping)
*   [Resolução de Problemas em ECUs](/cars/diagnostics/ecu-troubleshooting)
*   [Códigos de Avaria da ECU](/cars/diagnostics/ecu-trouble-codes)
