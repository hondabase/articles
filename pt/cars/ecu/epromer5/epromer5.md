---
summary: 'Visão geral técnica e guia de resolução de problemas para o programador de dispositivos legacy EPROMer5 via porta paralela, utilizado para chips 27C256 e AT29C256.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - hardware
  - referência
sources:
  - name: 'pgmfi.org wiki'
    title: Epromer5
    url: /pgmfi/wiki/library/epromer5
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Guia do Programador de Dispositivos EPROMer5

O **EPROMer5** é um gravador de ROM "faça você mesmo" (DIY) baseado em porta paralela (LPT) legacy que foi amplamente popular no início dos anos 2000 entre as comunidades de afinação de ECM da GM e ECU da Honda. Embora os programadores USB modernos (como o XGecu TL866/T48) o tenham substituído em grande parte, o EPROMer5 continua a ser uma ferramenta robusta e de baixo custo para gravar chips `27C256` e `AT29C256`.

---

## 1. Suporte a Chips e Capacidades

*   **Suporte a 27C256:** Suporta nativamente EPROMs padrão de 32 KB (por exemplo, AMD, TI ou Intel 27C256).
*   **Suporte a AT29C256:** Revisões posteriores e atualizações de software adicionaram suporte para a popular EEPROM apagável eletricamente Atmel AT29C256.

---

## 2. Dicas de Configuração e Resolução de Problemas

Devido à sua natureza DIY e à dependência de comunicação por porta paralela legacy, os utilizadores frequentemente encontravam problemas específicos de configuração:

### Verificação de Juntas de Soldadura
Se o dispositivo não conseguir identificar os chips, apresentar erros de verificação aleatórios ou falhar na inicialização, inspecione a placa de circuito. Muitos kits eram enviados parcialmente montados ou construídos à mão:
*   Use uma lupa para verificar se existem soldaduras frias nos circuitos integrados (ICs) de montagem em superfície (SMD).
*   Reaqueça quaisquer juntas suspeitas com uma ponta de soldar de cinzel fino e aplique fluxo fresco para garantir uma ligação elétrica sólida.

### Temporização da Porta Paralela (Velocidade de Gravação)
As portas paralelas são sensíveis à temporização do CPU e às velocidades de barramento (bus). 
*   **Ajustes de Temporização:** Ao correr o software do programador em computadores mais antigos (como um portátil equipado com LPT de 600 MHz), poderá ser necessário limitar manualmente a velocidade de temporização de escrita nas definições do gravador. Definir o atraso de velocidade de gravação para **"13"** (ou superior) é frequentemente necessário para evitar erros de estouro de buffer de dados ao gravar em EPROMs UV `27C256`.
*   **Vantagem da Memória Flash:** As EEPROMs flash Atmel `29C256` gerem as operações de escrita através de buffers de página internos, o que as torna menos sensíveis à temporização da porta paralela. Normalmente, podem ser programadas em qualquer definição de velocidade sem erros induzidos por problemas de temporização.
