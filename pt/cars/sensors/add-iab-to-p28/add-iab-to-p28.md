---
summary: 'Guia de modificação de hardware para adicionar controlos secundários do Intake Air Bypass (IAB) a uma ECU OBD1 Honda P28 Civic.'
tags: [ecu, hardware, iab]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Add IAB To P28'
    url: /pgmfi/wiki/library/add-iab-to-p28
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Adicionar Controlo IAB a uma ECU OBD1 P28

O sistema **Intake Air Bypass (IAB)** controla as condutas de admissão de duplo estágio em motores como o Acura Integra GS-R (B18C1) e o Prelude VTEC (H22A). Ao abrir as condutas secundárias a uma rotação de transição específica (geralmente às 5.750 RPM), o sistema otimiza o binário em baixas rotações e a potência máxima em altas rotações.

Embora a ECU Acura P72 controle o solenoide IAB de fábrica, a popular ECU Honda P28 (Civic SOHC VTEC) não contém os componentes de hardware necessários na placa. Este guia detalha como modificar a placa de uma ECU OBD1 P28 para adicionar controlo físico de IAB.

> [!IMPORTANT]
> **Verifique Primeiro o Seu Protocolo de Ligação**:
> O procedimento de modificação de hardware difere dependendo de como o solenoide IAB do seu veículo está ligado. Um dos lados do solenoide vai sempre para a ECU, mas o outro lado liga a alimentação de +12V (USDM Ativo por Massa/Active-Low) ou à Massa (JDM/OBD2 Ativo por Corrente/Active-High). Deve fazer coincidir a modificação com a configuração da sua cablagem.

---

## 1. Configuração USDM OBD1 Ativo por Massa / Active-Low (ECU Fecha Massa)

Esta é a configuração padrão para conversões (swaps) de USDM OBD1 B18C1 (Integra GS-R). O solenoide IAB é alimentado com +12V constantes sob o capô, e a ECU comuta o Pino **A17** para a Massa (Ground) para ativar as condutas.

### Componentes a Remover

* **`R135`** (apenas presente nas revisões de placa 11F0/1720 de ECUs automáticas)

* **`R150`** (apenas presente em placas de revisão 1980/LS)

### Componentes a Adicionar

* **`Q17`** (transístor digital PNP A143): Já presente em placas automáticas USDM 11F0/1720. Se não estiver presente, solde um novo transístor A143 aqui.

* **`Q34`** (transístor NPN D1780 ou C3225): Já presente em placas automáticas USDM 11F0/1720. Se não estiver presente, pode reaproveitar um transístor D1780 da saída do solenoide de purga (Q31) se tiver desativado o controlo de purga (EVAP) no software.

* **Fio Jumper (Shunt)**: Solde um fio jumper do orifício direito de **`R135`** (o lado do transístor) a **`D13`** (o lado da seta do díodo).

![USDM OBD1 IAB Jumper Wire](P28_IAB_OBD1.jpg)
*Configuração física do fio jumper na placa P28 para controlo IAB ativo por massa (active-low).*

---

## 2. Configuração JDM OBD1 / OBD2 Ativo por Corrente / Active-High (ECU Envia +12V)

Os motores JDM B18C e os veículos OBD2 ligam um dos lados do solenoide IAB diretamente à Massa. A ECU deve enviar um **sinal de +12V** no Pino **A19** para ativar o solenoide. Isto requer a adição de um chip de comutação do lado de alta tensão ou **High-Side Switch** (localização `515X` / `IC15`) na placa.

### Componentes a Remover

* **`Q34`** (Corte o pino de controlo do driver `IC15` curto, passe o fio de sinal através do orifício e solde-o ao orifício de controlo de `Q34`).

### Componentes a Adicionar

* **`IC15`** (IC High-Side Switch 515X): Solde o chip 515X no lugar, na localização `IC15`.

* **`C61`** (Condensador de Tântalo de 1&mu;F 35V): Solde este condensador no lugar para filtrar a tensão de alimentação do high-side switch.

* **`Q17`** (transístor A143): Se não estiver presente na sua placa, adicione um novo transístor A143.

* **Fio de Sinal**: Ligue um fio do pino de controlo cortado do `IC15` ao pad de controlo de `Q34`.

### Modificações na Placa (High-Side Switch)

![High-Side Switch Board Modification - View 1](P28_IAB_1.jpg)
*Visão geral da instalação do chip High-Side Switch `IC15` e encaminhamento da cablagem.*

![High-Side Switch Board Modification - View 2](P28_IAB_2.jpg)
*Vista aproximada do fio de sinal soldado ao pad de controlo de `Q34`.*

---

## 3. Configuração de Software e ROM

Como o software padrão do Civic P28 não possui parâmetros de código para monitorizar ou controlar IABs, modificar a placa física é apenas metade da batalha. Deve configurar o seu software de ROM para o suportar:

1. **Base de Código P72**: Grave uma ROM modificada de Acura Integra P72 (que suporta nativamente IABs) na sua EPROM com chip. Se o seu motor não tiver um sensor de detonação (knock sensor), deve utilizar um ficheiro.bin com a rotina do knock sensor desativada (caso contrário a ECU acionará o Código de Erro 23).
2. **Editor de ROM Crome**: Se estiver a usar uma base de código P28 personalizada em Crome, deve ativar manualmente o **IAB Plugin** e definir o limite de rotação desejado para ativação (normalmente 5.750 RPM).
