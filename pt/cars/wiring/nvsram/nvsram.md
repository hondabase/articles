---
summary: 'NVSRAM (Non Volatile SRAM) - RAM rápida, endereçável por byte, com escrita por byte, que retém o seu conteúdo após a perda de energia.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - wiring
  - conversion
sources:
  - name: 'pgmfi.org wiki'
    title: NVSRAM
    url: /pgmfi/wiki/library/nvsram
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# NVSRAM

[NVSRAM](/cars/wiring/nvsram) (**Non Volatile [SRAM](/cars/sensors/sram)**) - [RAM](/cars/reference/ram) rápida, endereçável por byte, com escrita por byte, que retém o seu conteúdo após a perda de energia. A [NVSRAM](/cars/wiring/nvsram) geralmente assume uma de várias formas: - **[SRAM](/cars/sensors/sram) com backup de bateria** (Dallas `DS1220`, 1230, etc., chips TI Benchmarq, ST...) - o chip contém [SRAM](/cars/sensors/sram), uma bateria e circuitos de deteção de energia. Quando a energia falha, a bateria de backup entra em ação e é usada para alimentar a [RAM](/cars/reference/ram), prevenindo a perda de dados. **Prós:** comporta-se exatamente como uma [SRAM](/cars/sensors/sram) eletricamente, tecnologia antiga. **Contras:** custo, tamanho físico grande, a bateria pode descarregar/morrer após vários anos.
- **Híbridos EEPROM/SRAM** (ZMD, chips Simtek, outros?) - o chip contém [EEPROM](/cars/diagnostics/eeprom), [SRAM](/cars/sensors/sram) e circuito de deteção de energia. Ao ligar, os dados são copiados da [EEPROM](/cars/diagnostics/eeprom) para a [SRAM](/cars/sensors/sram). Quando uma condição de falha de energia é detetada, os dados na [SRAM](/cars/sensors/sram) são gravados na [EEPROM](/cars/diagnostics/eeprom). Geralmente requer condensadores maiores na linha de alimentação para garantir que ocorra uma queda gradual da tensão na linha. **Prós:** mais barato, tamanhos de invólucro (packages) pequenos disponíveis. **Contras:** tempo de inicialização longo após ligar pode exigir modificação elétrica / lógica de designs existentes.
- **FRAM** (Ramtron) - [RAM](/cars/reference/ram) Ferroelétrica. Usa um cristal ferroelétrico para armazenar o bit. Tem a velocidade de leitura/escrita de [RAM](/cars/reference/ram) (~1ns) com a característica de reter os dados permanentemente. Ciclos de escrita quase ilimitados. **Prós:** Disponível em vários tipos de invólucro. Ciclos de durabilidade (endurance) muito elevados. Velocidades de Leitura/Escrita iguais às da [RAM](/cars/reference/ram). **Contras:** Disponibilidade. Pequenas diferenças de pinagem (pinout) face ao padrão `27C256`. Informações detalhadas no site da Ramtron: [http://www.ramtron.com/doc/AboutFRAM/technology.asp](http://www.ramtron.com/doc/AboutFRAM/technology.asp)
- **MRAM** (Cypress) - o chip contém armazenamento eletromagnético de próxima geração. Supostamente supera as desvantagens dos híbridos [EEPROM](/cars/diagnostics/eeprom)/SRAM (tempo de inicialização) e os problemas de formato (form factor) / vida útil da bateria da [SRAM](/cars/sensors/sram) com backup de bateria, sem introduzir as características elétricas/lógicas peculiares da FRAM. No geral: parece ser a tecnologia perfeita para a [Programação em Tempo Real (Real Time Programming)](/cars/sensors/real-time-programming) de dispositivos não projetados para tal. Espera-se ver componentes reais em vez de vaporware no segundo trimestre (`Q2`) de '04.
