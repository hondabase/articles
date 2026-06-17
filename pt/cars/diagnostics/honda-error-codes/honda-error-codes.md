---
summary: 'Uma lista de referência completa dos códigos de erro de diagnóstico (DTC) Honda OBD0, OBD1 e OBD2, incluindo contagens de flashes da CEL e descrições.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - diagnósticos
  - obd
  - referência
sources:
  - name: 'pgmfi.org wiki'
    title: 'Honda Error Codes'
    url: /pgmfi/wiki/library/honda-error-codes
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Guia de Referência de Códigos de Erro de Diagnóstico (DTC) Honda

Quando um sensor ou sistema de um motor Honda avaria, a Unidade de Controlo do Motor (ECU) acende a luz de verificação do motor no painel de instrumentos (Check Engine Light - CEL / MIL) e armazena um código de erro de diagnóstico (DTC) na sua memória.

Este guia de referência detalha como obter estes códigos e lista os significados e causas comuns para os códigos de erro Honda de 1 a 92.

---

## Como Obter Códigos de Diagnóstico

Antes de ler os códigos, deves identificar a geração OBD do teu veículo:

### Sistemas OBD0 (1988–1991)
As ECUs OBD0 exibem códigos através de um LED vermelho montado diretamente na placa de circuito da ECU:
1. Roda a chave de ignição para a posição ON.
2. Localiza a ECU sob a carpete ou banco do lado do passageiro.
3. Olha através da janela de visualização circular na caixa metálica da ECU.
4. Conta as intermitências do LED vermelho. Um código 9 é representado por 9 piscadelas rápidas.

### Sistemas OBD1 (1992–1995)
Os systems OBD1 piscam a luz de Check Engine (CEL) no painel de instrumentos:
1. Localiza a ficha de diagnóstico de 2 pinos (Service Connector Switch - SCS), que costuma estar envolvida em fita azul atrás do painel lateral do lado do passageiro.
2. Efetua uma ligação direta (shunt) entre os dois pinos usando um clipe de papel ou um fio.
3. Roda a chave de ignição para a posição ON.
4. Observa a luz de Check Engine e conta as piscadelas:
   - **Piscadelas longas (1,0 segundo):** representam o dígito das dezenas (ex: três piscadelas longas = 30).
   - **Piscadelas curtas (0,5 segundo):** representam o dígito das unidades (ex: quatro piscadelas curtas = 4).
   - Um código 34 é piscado como três piscadelas longas seguidas de quatro piscadelas curtas.

---

## Códigos de Erro de Diagnóstico Honda OBD0 e OBD1

Abaixo está a lista principal de códigos de erro de diagnóstico de fábrica:

| Código (Piscadelas) | Sensor / Sistema com Avaria | Causas Comuns e Sintomas |
| :---: | :--- | :--- |
| **1** | Sensor de Oxigénio Primário (Sonda $O_2$ Primária) | Cablagem danificada, sensor defeituoso ou funcionamento incorreto do circuito de aquecimento. |
| **2** | Sensor de Oxigénio Secundário (Sonda $O_2$ Secundária) | Origem em modelos de carburador duplo ou modelos específicos JDM/Europeus com sensor duplo. |
| **3** | Pressão Absoluta do Coletor (Sensor MAP) | Circuito elétrico aberto ou em curto-circuito nas fichas da cablagem do sensor MAP. |
| **4** | Sensor de Posição da Cambota (Sensor CKP) | Falha no sensor interno do distribuidor ou falha na cablagem. Impede o arranque do motor. |
| **5** | Pressão Absoluta do Coletor (Sensor MAP) | Falha mecânica na faixa de vácuo. Verifica se há um tubo de vácuo do MAP rachado ou desligado. |
| **6** | Temperatura do Líquido de Refrigeração (Sensor ECT) | Aberto ou curto-circuito no circuito do ECT. Causa dificuldade no arranque a frio e ralenti instável. |
| **7** | Sensor de Posição do Acelerador (TPS) | Sensor TPS defeituoso, calibração base incorreta (deve ler 0,5V com borboleta fechada). |
| **8** | Sensor de Ponto Morto Superior (Sensor TDC) | Falha no sensor interno do distribuidor. Causa ponto de ignição errático ou problemas no arranque. |
| **9** | Sensor de Posição do Cilindro (Sensor CYP) | Falha no sensor interno do distribuidor. Causa falha na injeção sequencial ou falhas de ignição. |
| **10** | Temperatura do Ar de Admissão (Sensor IAT) | Circuito do sensor aberto ou em curto-circuito. Restringe as correções de combustível baseadas na temperatura. |
| **12** | Recirculação dos Gases de Escape (EGR Lift) | Passagens de EGR entupidas ou sensor de posição da válvula EGR defeituoso. |
| **13** | Pressão Barométrica (Sensor BARO) | Avaria no sensor de pressão barométrica dentro da caixa da ECU. Requer reparação da ECU. |
| **14** | Válvula de Controlo do Ar de Ralenti (IACV / EACV) | Circuito do solenoide da IACV defeituoso, fugas de vácuo ou acumulação de carvão na válvula. |
| **15** | Sinal de Saída de Ignição | Falta de sinal de ignição do Módulo de Controlo de Ignição (ICM) no distribuidor. |
| **16** | Sistema de Injetores de Combustível | Cablagem dos injetores defeituosa, fichas soltas ou falha na caixa de resistências (modelos OBD0). |
| **17** | Sensor de Velocidade do Veículo (VSS) | Falha no sensor de velocidade ou cabo do velocímetro partido. **Nota:** Impede a ativação do VTEC. |
| **19** | Solenoide de Controlo de Bloqueio da A/T | Falha no circuito elétrico do solenoide de bloqueio da transmissão automática. |
| **20** | Detetor de Carga Elétrica (ELD) | Unidade ELD defeituosa na caixa de fusíveis do compartimento do motor ou alta resistência elétrica. |
| **21** | Válvula Solenoide do VTEC | Cablagem do solenoide do VTEC aberta ou em curto-circuito. Impede a ativação do VTEC. |
| **22** | Interruptor de Pressão de Óleo do VTEC | Nível de óleo do motor baixo, pressão de óleo baixa ou interruptor de pressão defeituoso no conjunto do VTEC. |
| **23** | Sensor de Detonação (Knock Sensor - KS) | Sensor de detonação defeituoso, corpo do sensor rachado ou fio blindado cortado. |
| **30** | Sinal FI da A/T A | Falha no circuito de comunicação da transmissão automática com a ECU. |
| **31** | Sinal FI da A/T B | Falha no circuito de comunicação da transmissão automática com a ECU. |
| **41** | Aquecedor do Sensor $O_2$ Primário | Elemento de aquecimento danificado dentro da sonda $O_2$ de 4 fios. Requer substituição do sensor. |
| **43** | Sistema de Alimentação de Combustível | Limite de alimentação de combustível em malha fechada excedido. O motor está a funcionar extremamente rico ou pobre. |
| **45** | Sistema Demasiado Rico / Demasiado Pobre | Limite da faixa de adaptação de combustível atingido (código transicional inicial OBD2). |
| **48** | Sensor de Mistura Pobre Ar-Combustível (Sensor LAF) | Falha no sensor de oxigénio de mistura pobre de 5 fios (típico nos modelos Civic VX D15Z1). |
| **54** | Flutuação da Velocidade da Cambota (CKF) | Falha no sensor de deteção de falhas de ignição no bloco do motor/bomba de óleo (modelos OBD2). |
| **58** | Sensor TDC 2 | Avaria no circuito do sensor de Ponto Morto Superior (equipado em modelos V-6). |
| **80** | Fluxo de EGR Insuficiente | Canais de EGR entupidos com carvão no coletor de admissão. Requer limpeza dos canais. |
| **90** | Fuga no Sistema EVAP | Fuga no sistema EVAP, válvula de purga defeituosa ou tampa de combustível solta (modelos OBD2). |
| **91** | Sensor de Pressão do Depósito de Combustível | Sinal de entrada elétrica baixo vindo do sensor de pressão do depósito de combustível. |
| **92** | Fluxo de Purga EVAP Insuficiente | Fluxo de vácuo insuficiente através do sistema de purga do filtro EVAP. |

---

## Guia de Resolução de Problemas para Códigos Comuns

### Solenoide e Interruptor de Pressão do VTEC (Códigos 21 e 22)
A ativação do VTEC requer o cumprimento de múltiplos parâmetros. Se a ECU lançar um Código 21 ou 22:
1. **Verifica o nível de óleo do motor:** Um nível de óleo baixo ou pressão de óleo baixa irá acionar o Código 22 quando a ECU comandar a transição para VTEC.
2. **Verifica o VSS (Código 17):** Se o teu velocímetro estiver partido ou o VSS estiver desligado, a ECU não ativará o VTEC e poderá lançar um código.
3. **Verifica a cablagem:** O solenoide do VTEC requer um sinal de 12V da ECU (pino A4 em OBD1). O interruptor de pressão do VTEC deve ligar à ECU (pino D6) e à massa.

### Aquecedor do Sensor de Oxigénio (Código 41)
Se o Código 41 for lançado:
- O elemento de aquecimento interno no sensor $O_2$ de 4 fios falhou (geralmente apresenta resistência infinita entre os dois fios pretos no lado do sensor).
- Substitui o sensor. Não tentes contornar este teste do aquecedor, pois ele garante que o sensor atinja a temperatura de funcionamento rapidamente.

### Sensores do Distribuidor (Códigos 4, 8 e 9)
A caixa do distribuidor contém os sensores CKP, TDC e CYP.
- Se algum destes códigos ocorrer, verifica se a ficha do distribuidor tem corrosão.
- Se a cablagem estiver intacta, as bobinas internas dos sensores dentro do distribuidor estarão provavelmente a falhar devido à idade ou calor. O distribuidor completo deve ser substituído. Consulta o [guia do sensor de posição do cilindro](/cars/sensors/cylinder-position-sensor) para diagnósticos.
