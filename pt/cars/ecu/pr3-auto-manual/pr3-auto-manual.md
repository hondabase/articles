---
summary: 'Guia técnico para converter uma ECU OBD0 PR3 de transmissão automática para manual através da realocação de componentes na placa.'
tags: [ecu, obd0, pr3, conversao, manual]
applies_to:
  obd: [0]
  ecus: [PR3]
complexity: beginner
---

# Conversão de Transmissão Automática para Manual em ECU OBD0 PR3

Para converter uma ECU OBD0 PR3 de uma configuração de transmissão automática para manual, é necessário realizar a realocação de um componente resistivo na placa de circuito impresso (PCB).

## Procedimento de Modificação

1. Localize a resistência identificada como **R68** na placa da ECU, situada próxima à divisória central do PCB.
2. Remova a resistência **R68** através de dessoldagem.
3. Solde o componente removido na posição **R67**, que se encontra vazia na placa.

> [!CAUTION]
> Utilize um ferro de solda com controle de temperatura e sugador de solda de qualidade para evitar danos às trilhas da placa de circuito impresso durante a remoção e instalação do componente.

## Localização dos Componentes

Abaixo estão as referências visuais para a localização dos pontos de solda na placa PR3.

```carousel
![Localização da resistência R68 na ECU PR3](OBD0_pr3-auto-manual.jpg)
*Vista superior da placa indicando a posição original do componente R68*
<!-- slide -->
![Detalhe da área de conversão R67/R68](OBD0_pr3-auto-manual-zoom.jpg)
*Detalhe da área de soldagem para a transição de automático para manual*
```

{{> esd-safety-precautions }}