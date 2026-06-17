---
summary: 'Como configurar e resolver problemas em conversores série USB para TTL (tais como chips FTDI ou CP2102) para um datalogging fiável da ECU.'
applies_to:
  obd: [1]
complexity: advanced
tags:
  - datalogging
  - serial
  - hardware
sources:
  - name: 'pgmfi.org wiki'
    title: 'Second Gen Usb To Serial Converter'
    url: /pgmfi/wiki/library/second-gen-usb-to-serial-converter
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Guia do Conversor Série USB-para-TTL (`FTDI` e CP2102)

Os portáteis modernos não possuem portas série DB9 físicas. Para fazer a interface com o [conector de datalogging série (CN2)](/cars/tuning/serial-communication) numa ECU Honda OBD1, deve usar uma placa conversora USB-para-TTL. Estes conversores utilizam chips de circuito integrado para traduzir os sinais do barramento USB em dados de série assíncronos TTL (lógica de 0V–5V) que o microcontrolador da ECU pode processar.

Os chips mais populares e fiáveis usados nestes conversores são o **`FTDI` FT232RL** e o **Silicon Labs CP2102**.

---

## 1. Cablagem de Módulos USB-para-TTL Padrão

Ao contrário das placas modulares mais antigas e complexas que exigiam a configuração manual de jumpers e linhas de handshaking, as placas de desenvolvimento (breakout boards) modernas expõem uma interface simples de 4 ou 6 pinos. Para ligar um módulo padrão à sua ECU:

1. Localize os pinos de interface na placa de desenvolvimento: **GND**, **TXD** (Transmissão) e **RXD** (Receção).
2. Ligue o pino de terra (ground) do módulo ao **Pino 4** (GND) do conector CN2 da ECU.
3. Ligue o pino **RXD** do módulo ao **Pino 1** (TX) do conector CN2 da ECU.
4. Ligue o pino **TXD** do módulo ao **Pino 2** (RX) do conector CN2 da ECU.
5. **Não** ligue o pino VCC (+5V ou +3,3V) do módulo à ECU. O módulo deve ser alimentado pela porta USB do portátil, enquanto a ECU funciona com a sua própria fonte de alimentação interna. Isto evita loops de terra (ground loops) e interferências elétricas.

---

## 2. Diagnóstico de Hardware: O Teste de Loopback

Se o seu software de datalogging não se conseguir ligar, pode realizar um **teste de loopback** para isolar se o problema reside no conversor/driver USB ou na própria ECU.

### Passos do Teste de Loopback
1. Desligue o módulo USB-para-TTL do conector `CN2` da ECU.
2. Utilizando um pequeno fio de ligação (jumper), ligue o pino **TXD** do módulo diretamente ao seu próprio pino **RXD**.
3. Ligue o módulo à porta USB do seu portátil.
4. Abra um programa de terminal de série (como o PuTTY, Tera Term ou o Monitor Série do Arduino).
5. Selecione a porta COM correspondente ao seu módulo (encontrada no Gestor de Dispositivos do Windows em *Portas (COM e LPT)*) e configure a ligação para **38.400 baud**.
6. Abra a ligação e digite algum texto na janela do terminal:
   - **Se os caracteres que digitar aparecerem no ecrã:** A interface USB, o chip, o driver e a configuração do portátil estão a funcionar perfeitamente. O problema reside nas ligações do `CN2` da ECU, soldadura, firmware da ROM ou cablagem.
   - **Se nada aparecer no ecrã:** O módulo conversor, o cabo USB ou os drivers estão com defeito.

---

## 3. Otimização da Latência da Porta COM (Passo Crítico)

Por padrão, os drivers USB da FTDI e CP2102 estão configurados com um temporizador de latência otimizado para transferências de dados de alta largura de banda, em vez de diagnósticos em tempo real. Esta configuração padrão (normalmente de **16 ms**) causa atualizações lentas de datalogging, taxas de atualização lentas ou desconexões frequentes em programas como o Crome ou Hondata.

### Como Ajustar a Latência no Windows:
1. Abra o **Painel de Controlo** do Windows e navegue até ao **Gestor de Dispositivos**.
2. Expanda a secção **Portas (COM e LPT)**.
3. Clique com o botão direito na sua porta COM USB-para-Série e selecione **Propriedades**.
4. Aceda ao separador **Definições de Porta** e clique em **Avançadas**.
5. Localize o menu pendente **Temporizador de Latência** (o padrão é 16).
6. Altere este valor para **1 ms**.
7. Clique em **OK** para guardar e fechar. Volte a abrir o seu software de ajuste (tuning) para verificar o aumento de velocidade de datalogging.

---

## 4. Resolução de Problemas de Ligação

Se o seu teste de loopback for bem-sucedido mas ainda assim não conseguir estabelecer comunicação com a ECU:

- **Verifique a Ligação Cruzada dos Sinais:** Verifique novamente se o TX liga ao RX e o RX liga ao TX. É um erro comum ligar TX com TX e RX com RX. Se suspeitar disto, inverta as duas linhas de dados na sua ficha `CN2`.
- **Inspecione as Juntas de Soldadura:** Juntas de soldadura fria no conector de pinos `CN2` da ECU podem causar quedas de ligação intermitentes devido à vibração do motor. Refaça a soldadura dos pinos com fluxo novo.
- **Isole o Ruído de Ignição:** Os cabos de velas e as bobinas do distribuidor emitem interferência eletromagnética (EMI). Encaminhe o seu cabo USB de datalogging longe da cablagem do compartimento do motor e do distribuidor. Utilizar um cabo USB com um anel de ferrite pode ajudar a bloquear este ruído.
- **Verificação do Plugin de Datalogging:** Verifique se o seu chip de ROM foi gravado com o plugin de datalogging correto ativo (como o datalogger Quick de 2 bytes para o Crome) e se o checksum da ROM está desativado. Para mais dicas de depuração de software, consulte o [guia de depuração de datalogging](/cars/diagnostics/debugging-data-logging).
