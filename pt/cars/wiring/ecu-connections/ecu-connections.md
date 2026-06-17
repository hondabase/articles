---
summary: 'Um índice de esquemas de pinagem (pinouts) de conectores de ECU, diagramas elétricos e guias de conversão de cablagens da Honda e Acura para as gerações OBD0, OBD1 e OBD2.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - ecu
  - pinagem
  - cablagem
sources:
  - name: 'pgmfi.org wiki'
    title: 'Ecu Connections'
    url: /pgmfi/wiki/library/ecu-connections
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Índice de Ligações e Pinagens de ECUs Honda

As cablagens (harnesses), fichas (plugs) e esquemas de pinos (pin layouts) variam significativamente entre as gerações de unidades de comando do motor (ECUs) da Honda. Conhecer estas ligações de pinos é fundamental para conversões de motor (swaps), adição de sensores personalizados (como controladores de banda larga ou registo de EGT) e conversões de transmissão automática para manual.

Abaixo encontra-se um índice de diagramas elétricos, pinagens (pinouts) e modificações personalizadas de cablagens categorizadas por geração OBD.

---

## 1. Geração OBD0 (1988–1991)

As ECUs OBD0 utilizam três fichas de cablagem amarelas (Conetores A, B e C) para comunicar com o veículo.
*   **Esquemas do PR4:** Para veículos equipados com B18A1, consulte o guia [Pinagem e Esquemas da ECU Acura Integra PR4](/cars/wiring/acura-integra-pr4ecu-pinout-and-schematics).
*   **Swaps de Cablagem:** Para atualizar um chassis OBD0 para funcionar com uma ECU OBD1 mais recente, consulte o [Guia de Conversão OBD0 para OBD1 do Kurt](/cars/wiring/kurts-obd0-obd1).

---

## 2. Geração OBD1 (1992–1995)

As ECUs OBD1 uniformizaram-se com três fichas cinzentas (pinos A, B e D) e representam a era mais popular para afinações personalizadas.

### Modificações Personalizadas de Interruptores
*   **Bypass do Interruptor de Pedido de A/C:** Como ligar e ativar a linha de entrada de A/C (Pino B5) em veículos não equipados com ar condicionado de fábrica. Isto é frequentemente utilizado por afinadores para ativar mapas secundários (como um modo valet ou mapa para piso molhado).
*   **Interruptor de Passagem de Caixa a Fundo (Full-Throttle Shift):** Utilização do interruptor de embraiagem de fábrica ou do interruptor de cancelamento do cruise control para enviar um sinal de massa (ground) para a ECU (geralmente Pino B8 ou D10) para ativar algoritmos de flat-foot shifting em Crome ou Hondata.

---

## 3. Geração OBD2 (1996–2001)

Os esquemas OBD2 dividem-se em duas configurações de pinos distintas (OBD2A para veículos de 1996–1998 e OBD2B para veículos de 1999–2001).

*   **Conversões OBD2 para OBD1:** Como as ECUs OBD2 estão bloqueadas e não podem levar chips, os afinadores utilizam uma cablagem de conversão plug-and-play para adaptar as fichas OBD2 do veículo a uma ECU OBD1.
*   **Conversões de Accord:** Para conversões específicas de Accord, consulte o [Guia de Conversão de Automático para Manual OBD2 para OBD1 de Accord](/cars/wiring/accord-auto-obd2-obd1).

---

## 4. Ficheiros Arquivados e Downloads

Para referência ao cablar um Civic ou Integra de meia geração:

*   [Descarregar o PDF da Pinagem OBD2 USDM Civic 1996–1998](OBD2Pinout.pdf) *(615 KB, referência detalhada da pinagem do conetor OBD2A)*
