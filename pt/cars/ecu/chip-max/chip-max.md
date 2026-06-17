---
summary: 'Especificações técnicas, configuração de software e definições de chips para o programador de dispositivos USB EETools ChipMax.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - hardware
  - reference
sources:
  - name: 'pgmfi.org wiki'
    title: 'Chip Max'
    url: /pgmfi/wiki/library/chip-max
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Programador de Dispositivos EETools ChipMax

O **ChipMax** (fabricado pela [EE Tools](http://www.eetools.com)) é um programador universal de dispositivos profissional de entrada de gama. Lançado originalmente com uma interface de porta paralela, os modelos mais recentes utilizam conectividade USB (como o ChipMax2).

É uma escolha popular para gravar EPROMs (como o `27C256`) e EEPROMs (como o [28C256](/cars/ecu/28c256)) utilizados em ECUs Honda OBD0 e OBD1.

## Principais Características

*   **Suporte Universal de Dispositivos:** Possui um socket Zero Insertion Force (ZIF) de 40 pinos de alta qualidade. Suporta uma ampla gama de dispositivos, incluindo EPROMs, EEPROMs, memória Flash e microcontroladores.
*   **Tempos de Hardware Fiáveis:** Ao contrário dos gravadores genéricos de baixo custo (como o [Willem](/cars/rom/willem) ou designs DIY "Ghetto Burner"), o ChipMax possui controladores internos dedicados que gerem tensões de programação e ciclos de temporização precisos, evitando falhas de verificação e chips danificados.
*   **Software e Suporte:** A EE Tools mantém atualizações de software regulares para suporte de dispositivos. Historicamente, o seu suporte técnico é conhecido por escrever perfis de dispositivos personalizados mediante solicitação.

## Comparação e Utilização

Comparado com gravadores de nível hobbyist/amador, o ChipMax é altamente estável, tornando-se uma opção preferida para preparadores (tuners) que lêem e gravam ROMs frequentemente. O software de controlo permite a verificação rápida de checksum, testes de integridade de gravação (blank checks) e edição de buffer antes da gravação.
