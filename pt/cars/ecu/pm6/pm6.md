---
summary: 'Especificações detalhadas de hardware, esquemas de pinagem e suporte de código personalizado para a ECU OBD0 PM6 de Civic/CRX Si SOHC.'
tags: [ecu, reference]
applies_to:
  make: Honda
  ecus: [PM6]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: PM6
    url: /pgmfi/wiki/library/pm6
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Referência de Hardware e Código da ECU PM6 (OBD0)

A **PM6** é a unidade de controlo do motor (ECU) original OBD0 utilizada nos modelos USDM Honda Civic e CRX Si de 1988–1991 equipados com o motor SOHC 1.6L D16A6. 

Devido à sua arquitetura simples e ampla disponibilidade, a PM6 serviu historicamente como uma das principais plataformas de desenvolvimento para reprogramação (tuning), desmontagem de código (disassembly) e programação em tempo real de Hondas OBD0.

## Arquitetura do Microcontrolador

A ECU PM6 é baseada na família de microcontroladores OKI `83C154` / Intel `80C154`. O código da ROM pode ser extraído, modificado e gravado em EPROMs padrão (como a `27C256`) para ajustar mapas de combustível, mapas de ignição, limites de rotação e outros parâmetros do motor.

## Recursos de Desenvolvimento

Os seguintes ficheiros de desenvolvimento estão localizados neste diretório:

* [Pm6.asm](Pm6.asm): Uma desmontagem de código (disassembly) abrangente da ROM original da PM6 USDM de 1991, com cerca de 95% do código assembly original totalmente mapeado e comentado para programadores.

## Referência do Layout da Placa

Abaixo encontram-se digitalizações de alta resolução da placa de circuito impresso (PCB) da ECU PM6 para mapeamento de componentes e referência de reparação:

### 1. Layout da Parte Superior da Placa

O lado superior do PCB da PM6 que mostra a localização de CIs (circuitos integrados), condensadores e conjuntos de resistências:

![Digitalização da parte superior da placa de circuito impresso da ECU PM6 mostrando componentes eletrónicos](PM6top.jpg)

### 2. Layout da Parte Inferior da Placa

O lado posterior de soldadura do PCB da PM6:

![Digitalização da parte inferior de soldadura da placa de circuito impresso da ECU PM6](PM6back.jpg)
