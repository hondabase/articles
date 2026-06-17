---
summary: 'Resolução de problemas comuns de datalogging em ECUs Honda, incluindo quedas de ligação, interferência de ruído e configurações incorretas de controladores (drivers).'
applies_to:
  obd: [1]
complexity: advanced
tags:
  - datalogging
  - diagnóstico
  - série
sources:
  - name: 'pgmfi.org wiki'
    title: 'Debugging Data Logging'
    url: /pgmfi/wiki/library/debugging-data-logging
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Resolução de Problemas de Datalogging em ECUs Honda (Depuração de `CN2`)

O datalogging permite a monitorização em tempo real das variáveis do motor, mas as falhas de ligação são comuns durante as configurações iniciais. Se o seu software de afinação (como o Crome, Hondata ou Neptune) não conseguir estabelecer uma ligação em direto com a ECU, siga esta lista de verificação de resolução de problemas para isolar problemas de hardware, software ou configuração do sistema operativo.

---

## 1. Verificações de Hardware e de Continuidade da Placa

Antes de verificar as definições do software, utilize um multímetro digital no **modo de continuidade (sinal sonoro/beep)** para verificar as pistas elétricas em redor do [conetor de datalogging CN2](/cars/tuning/serial-communication) na placa de circuito da ECU:

- **Verifique se existem Pontes de Solda:** Inspecione os pontos de solda do conetor CN2. Certifique-se de que não existem pontes de solda microscópicas ou resíduos de fluxo a ligar pinos adjacentes.
- **Verifique a Ligação à Massa:** Verifique se o **Pino 4** (GND) do CN2 tem uma continuidade sólida e de resistência zero com o chassis metálico principal da ECU e com os pinos de massa de alimentação (pinos A26/B2).
- **Rastreie a Linha de Receção (RX):** Verifique a continuidade do **Pino 2** (RX) do CN2 até ao processador principal OKI 66207:
  - Em placas com processador de montagem em superfície (a maioria das placas JDM), rastreie até ao **Pino 42**.
  - Em placas com processador dual-in-line package (DIP) (comum em placas USDM), rastreie até ao **Pino 39**.
- **Rastreie a Linha de Transmissão (TX):** Verifique a continuidade do **Pino 1** (TX) do CN2 até ao **Pino 6** do **IC19** (o chip buffer de linha TX de montagem em superfície).
- **Verificação de Troca de Sinais TX/RX:** O erro de cablagem mais comum é ligar TX com TX e RX com RX. Verifique se o fio RXD do seu adaptador USB para TTL está ligado ao Pino 1 (TX) do CN2, e se o fio TXD está ligado ao Pino 2 (RX) do CN2.

---

## 2. Calibração da ROM e Definições de Firmware

Se as pistas de hardware passarem nos testes de continuidade, verifique a configuração do ficheiro binário da ROM gravado no seu chip EEPROM:

### Desative a Rotina de Checksum
A ROM de uma ECU original calcula constantemente um checksum para verificar a integridade do código. Se carregar código de datalogging personalizado numa ROM, este checksum irá falhar, ativando uma luz de Check Engine (CEL) sólida (sempre acesa) e bloqueando a interface série.
- **Ação:** Abra a sua ROM no seu editor, aceda ao menu de melhorias (enhancements) e selecione **Remove Checksum Routine** (Remover Rotina de Checksum) antes de gravar o chip.

### Instale um Plugin de Protocolo de Datalogging
O código original da ROM não envia dados de diagnóstico série pelo conetor `CN2` por padrão. Deve aplicar um plugin de protocolo de datalogging sobre o ficheiro binário:
- **Ação:** Instale um plugin de protocolo (como o plugin *Quick Datalogger* do Crome). Isto insere ciclos de transmissão série na execução do programa principal da ECU.
- **Correspondência de Baud Rate (Taxa de Transmissão):** Verifique se as definições de ligação do seu software correspondem à taxa de transmissão do protocolo do plugin. Por exemplo, o Quick Datalogger do Crome predefine-se para **38.400 bps**, enquanto os protocolos mais antigos podem funcionar a **9.600 bps** ou **115.200 bps**.

---

## 3. Otimização do Controlador (Driver) e da Porta COM Virtual

Se o seu hardware estiver correto e a ROM estiver devidamente configurada, configure o sistema operativo do seu portátil:

- **Ajuste o Temporizador de Latência (Crítico):** Abra o **Gestor de Dispositivos** do Windows, localize a sua porta USB-to-Serial em *Portas (COM e LPT)*, aceda a **Propriedades > Definições de Porta > Avançadas** e altere o **Temporizador de Latência** de 16 ms para **1 ms**. As definições de latência padrão causam falhas de comunicação por limite de tempo (timeouts) e atualizações lentas no datalogging.
- **Verifique a Atribuição da Porta COM:** Confirme se o seu software de afinação está apontado para o número exato da porta COM atribuído pelo Windows (ex: COM2). Se o sistema operativo atribuir um número de porta COM elevado (ex: COM18), reatribua-o manualmente nas propriedades do Gestor de Dispositivos para uma porta inferior (COM1 a COM4), pois os programas de afinação mais antigos não conseguem fazer a leitura de portas COM elevadas.

---

## 4. Teste de Bancada da ECU

Para resolver problemas na interface de datalogging sem ter de lidar com a cablagem do carro, pode ligar uma cablagem básica de teste de bancada para alimentar a ECU na sua secretária.

### Pinagem de Teste de Bancada OBD1
Para inicializar uma ECU Honda OBD1 numa fonte de alimentação de 12V DC, faça as seguintes ligações nas fichas da ECU:

| Tipo de Ligação | Número do Pino da ECU | Descrição |
| :--- | :---: | :--- |
| **Alimentação Direta +12V (Constante)** | **D1** | Fonte de alimentação de reserva (backup) |
| **Alimentação Pós-Chave +12V (Ignitada)** | **A25 e B1** | Entradas principais de alimentação de ignição |
| **Massa do Chassis** | **A26 e B2** | Massas de alimentação principais |
| **Jumper de Diagnóstico (SCS)** | **D4** | Ligue este pino à massa para ativar os códigos de pisca de diagnóstico |
| **Luz de Check Engine (CEL)** | **A11** | Ligue um LED em série com uma resistência de 1k Ohm entre o pino A11 e +12V. O LED irá acender para replicar a luz de CEL do painel de instrumentos. |

Uma vez alimentada na bancada, ligue o seu conversor USB para TTL ao conetor `CN2` e inicie o seu software de datalogging. Embora o datalogger reporte valores incorretos devido à falta de sensores, deverá ver números ativos a atualizar no seu ecrã, indicando que a interface série está totalmente funcional.

## Artigos Relacionados
- [Pinagens da Porta Série CN2](/cars/tuning/serial-communication)
- [Configurar Adaptadores USB para TTL](/cars/tuning/second-gen-usb-to-serial-converter)
- [Como Interpretar Diagnósticos de Sensores](/cars/diagnostics/honda-error-codes)
