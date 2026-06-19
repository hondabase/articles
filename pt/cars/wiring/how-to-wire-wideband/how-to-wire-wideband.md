---
title: 'Guia de Instalação de Wideband para ECUs Honda OBD1'
summary: 'Aprenda a instalar e configurar um sensor de O2 wideband AEM na sua ECU Honda OBD1 usando o Honda Tuning Suite (HTS) ou o Hondata SManager.'
tags: [ecu, referência, afinação, sensores, cablagem, obd1]
applies_to:
  brand: [honda, acura]
  ecus: [P28, P30, P72, P06, P75]
complexity: advanced
---

Um sensor de oxigénio wideband (também conhecido como UEGO - Universal Exhaust Gas Oxygen sensor) é uma ferramenta crucial para a afinação do motor do seu Honda. Ao contrário do sensor de O2 narrowband original (de fábrica), um wideband fornece medições precisas da relação ar/combustível (AFR) numa gama ampla, permitindo uma afinação precisa e a monitorização do desempenho do seu motor.

Este guia orienta-o no processo de instalação e configuração de um sensor wideband numa ECU Honda OBD1. Embora este guia seja escrito principalmente para widebands da marca AEM, os mesmos conceitos e princípios de cablagem aplicam-se a outras marcas principais (utilizando o desvio de tensão (offset) da bateria e os valores de escala especificados nos respetivos manuais).

## Visão Geral

Um sensor de O2 wideband utiliza um elemento sensor complexo e uma caixa/circuito de controlo para aquecer e ler o sensor. Fornece uma saída de tensão analógica de 0-5V, oferecendo alta resolução e precisão numa gama ampla de relações ar/combustível (tipicamente 10:1 a 20:1 AFR). Em contrapartida, os sensores narrowband originais emitem um sinal estreito de 0-1V, indicando apenas se a mistura está mais rica ou mais pobre do que a estequiometria (14.7:1 AFR), o que não é suficientemente preciso para afinação.

## Cablagem

Este método de cablagem é compatível tanto com o Hondata S300 como com outras soluções de hardware, uma vez que se liga diretamente ao pino de sinal do sensor de O2 original. Se estiver a usar um Hondata S300, também pode usar as entradas analógicas integradas da placa para uma instalação mais limpa.

> [!TIP]
> Use um conetor de derivação rápida (T-tap) para ligar os fios à cablagem de fábrica sem cortar. Se a sua ECU usar uma cablagem de conversão (jumper harness), ligue a esses fios para manter intacta a cablagem original do chassis.

### Tabela de Referência de Cablagem

::: widget wideband-wiring-table :::

> [!TIP]
> Ligar o fio Castanho (massa diferencial / differential ground) oferece a melhor qualidade de sinal com a menor interferência, exigindo pouca ou nenhuma correção de desvio de tensão (offset) no seu software de afinação.

## Configuração no HTS (Honda Tuning Suite)

### Descarregar o HTS

Descarregue a versão mais recente do Honda Tuning Suite no site oficial: [hondatuningsuite.com](http://www.hondatuningsuite.com).

### Abrir as Definições de Wideband

Inicie o Honda Tuning Suite e navegue até **File** > **Settings** > **Wideband** para abrir a janela de configuração.

### Selecionar o Pino da ECU

Selecione o pino **D14** para a entrada de sinal do wideband.

> [!NOTE]
> Devido ao layout físico do circuito D14, o pino D14 tem um limite de tensão de `3.8V`, o que corresponde a uma leitura de AFR de aproximadamente `16.0` or higher. Consulte o [tópico de limitações do circuito D14 da Hondata](https://www.hondata.com/forum/viewtopic.php?t=10423) para mais detalhes.

![Interface de seleção do pino da ECU mostrando o pino D14](hts_ecu-input.png)
*Seleção do pino da ECU para entrada do wideband no HTS.*

### Configurar a Tabela de Conversão

Configure a *tabela de conversão de Tensão para Lambda/AFR

* selecionando uma predefinição ou especificando desvios personalizados. O HTS tem valores pré-configurados tanto para manómetros AEM mais antigos (30-4100/30-4110) como para modelos mais recentes (X-Series, que foram corrigidos na versão 2.22F2).

![Valores pré-configurados no HTS 2.22F2](hts2.22F2_conversion-table.png)
*Predefinições de escala de wideband pré-configuradas no HTS 2.22F2.*

![Valores pré-configurados no HTS 2.15](hts_conversion-table.png)
*Predefinições de escala de wideband pré-configuradas no HTS 2.15.*

### Desvios Personalizados (Custom Offsets)

Se o seu modelo de wideband não estiver listado, selecione **Custom** no menu suspenso e insira os valores de escala de tensão para lambda do seu wideband a partir do manual do fabricante. Certifique-se de que a gama de saída é adequada; se 3.75V não atingir 15 AFR, configure a gama de saída do controlador para caber dentro do limite de 3.8V do pino D14. Alternativamente, pode usar o pino de entrada da EGR D12, mas isso requer dessoldar resistências na placa da ECU e [apenas funciona em ECUs USDM/não-JDM](https://www.hondata.com/forum/viewtopic.php?t=8259).

![Tabela mostrando a tabela de escala da AEM](x-series_scaling-table.png)
*Tabela de escala de tensão do AEM X-Series.*

### Calibrar o Desvio de Tensão (Voltage Offset)

Se estiver a usar um manómetro físico, compare a leitura do manómetro com a indicação do HTS. Ajuste o valor do desvio (usando os botões `-` e `+`) até que os valores coincidam exatamente.

![Interface de correção de offset](hts_offset-correction.png)
*Definições do fator de correção de desvio (offset) no HTS.*

## Configuração no Hondata SManager

O processo de configuração no Hondata SManager (para placas S300) segue princípios semelhantes aos do HTS.

### Cablagem

Ligue a saída analógica do seu wideband a qualquer um dos pinos de entrada analógica da placa S300 (identificados de **A0** a **A7**). Se o seu wideband tiver um fio de massa analógico, ligue-o diretamente ao pino de massa analógica do S300 (**GND**).

> [!TIP]
> Para evitar desvios de tensão, use fios de secção grossa para a massa, mantenha os fios de massa curtos e ligue à massa tanto o controlador wideband quanto a ECU no mesmo ponto físico de massa.

![Diagrama de ligações mostrando o AEM 30-4100 com ligação de saída analógica simples ao S300](analog-wideband-1.jpg)
*Ligação de saída analógica simples do AEM 30-4100 ao S300.*

![Diagrama de ligações mostrando o AEM 30-2310 com saída analógica e ligação de massa ao S300](analog-wideband-2.jpg)
*Ligação de saída analógica e massa do AEM 30-2310 ao S300.*

### Passos de Configuração

1. Descarregue o SManager em [hondata.com/software](https://hondata.com/software).
2. Abra o SManager e navegue até às definições de **Parameters** > **Closed Loop** ou **Closed Loop Advanced**.
3. Em **Closed Loop**, configure os seus parâmetros de funcionamento.

![Visão geral dos parâmetros de Closed loop](hondata_closed-loop_overview.png)
*Parâmetros gerais de Closed loop no SManager.*

![Interface de definições de funcionamento em Closed loop](hondata_closed-loop-operation.png)
*Definições do modo de funcionamento em Closed loop.*

![Menu suspenso de seleção do modo de funcionamento em Closed loop](hondata_closed-loop-operation-dropdown.png)
*Selecionar a fonte de entrada de Closed loop no SManager.*

4. Em **Closed Loop Advanced**, defina a sua fonte de entrada para o pino analógico do S300 que ligou (A0-A7) e insira quaisquer desvios de tensão (offsets) necessários.

![Visão geral das definições avançadas de Closed loop](hondata_closed-loop-advanced_overview.png)
*Visão geral das definições avançadas de Closed loop.*

![Seleção de Fonte de Entrada avançada de Closed loop e introdução do desvio de tensão.](hondata_closed-loop-advanced.png)
*Selecionar o pino de entrada analógica e introduzir o desvio de tensão.*

![Seleção da fonte de entrada wideband para Closed loop avançado](hondata_closed-loop-advanced_input-source-dropdown.png)
*Lista de opções de entrada analógica do S300.*

### Ficheiro de Ajuda

A Hondata fornece documentação abrangente nos seus ficheiros de ajuda, acessíveis tanto no SManager quanto online no [Índice de Ajuda do Hondata SManager](https://www.hondata.com/help/smanager/index.html?analog_wideband.htm).
