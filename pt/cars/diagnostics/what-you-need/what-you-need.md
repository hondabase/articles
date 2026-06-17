---
summary: 'Introdução prática à reprogramação (chipping) de ECUs Honda: o que significa, as ferramentas essenciais necessárias e o processo de gravação de novos ficheiros bin.'
tags: [hardware, educação, ecu, tuning, rom, sensores, referência, diagnóstico]
applies_to:
  obd: [0]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'What You Need'
    url: /pgmfi/wiki/library/what-you-need
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# O que Precisas

Fazer o "chipping" (ou chipar) de uma [ECU](/cars/ecu/ecu) significa substituir o programa que corre na [ECU](/cars/ecu/ecu). "Chipping" é apenas calão. O que na verdade fazemos é programar (ou "gravar") um novo ficheiro.bin na [ROM](/cars/rom/rom) para substituir o programa que corre atualmente na [ECU](/cars/ecu/ecu). Para chipar uma [ECU](/cars/ecu/ecu), irás precisar do seguinte:

- [Ferro de Soldar](/cars/ecu/soldering-iron) - para soldar os chips na [ECU](/cars/ecu/ecu)
- [Ferramenta de Dessoldar](/cars/ecu/desoldering-tool) - para remover os chips/solda de uma [ECU](/cars/ecu/ecu). Um [Ferro de Dessoldar](/cars/ecu/desoldering-iron), [Fita de Dessoldar](/cars/wiring/desoldering-braid) ou uma [Estação de Dessoldar](/cars/ecu/desoldering-station) também funcionam. Lê as [Dicas de Dessoldagem](/cars/ecu/desoldering-tips). Se não te sentires confortável a fazer isto, ou se não tiveres acesso às ferramentas, alguns membros da PGMFI vendem [ECU](/cars/ecu/ecu)s com suporte [ZIF](/cars/rom/zif) pré-instalado.
- [Editor de ROM](/cars/rom/rom-editor) - para criar o novo ficheiro.bin para gravar no chip
- [Gravador de ROM](/cars/ecu/rom-burner) - para gravar num chip para substituir o programa original
- [Biblioteca de ROMs](/cars/ecu/ecu-definition-codes) - Para obter alguns ficheiros.bin já prontos
- [Chips para ECUs](/cars/rom/chips-for-ec-us) - para gravar o novo ficheiro.bin - o [ATMEL AT29C256](/cars/diagnostics/29c256) parece ser o chip recomendado
- [Peças para ECUs](/cars/ecu/parts-for-ec-us) - é uma lista bastante completa das peças necessárias para as [ECU](/cars/ecu/ecu)s.

Parece bastante fácil, não é? O Dave B. escreveu um excelente artigo de [Introdução ao ECU Chipping](/cars/rom/introduction-to-ecu-chipping) que é um ótimo ponto de partida para aprender a chipar [ECU](/cars/ecu/ecu)s. NOTA: Nem todas as [ECU](/cars/ecu/ecu)s [OBD0 MPFI](/cars/diagnostics/obd0mpfi) têm uma [ROM](/cars/rom/rom) para ser substituída. Não te preocupes, pois [Chipar uma ECU de 88-89](/cars/rom/chipping-an88-89ecu) também é possível.
