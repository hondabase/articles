---
summary: 'Especificações técnicas do protocolo de comunicação do Data Link Connector (DLC) Honda OBD1, níveis de tensão, limites de capacitância e protocolos de comunicação série.'
applies_to:
  obd: [1]
complexity: advanced
tags:
  - datalogging
  - software
sources:
  - name: 'pgmfi.org wiki'
    title: 'DLC Communication'
    url: /pgmfi/wiki/library/dlc-communication
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Protocolos de Comunicação do Data Link Connector (DLC)

O Data Link Connector (DLC) original da Honda OBD1 é a interface utilizada por ferramentas de diagnóstico para obter códigos de diagnóstico de anomalia (DTCs) e monitorizar parâmetros dos sensores em tempo real. A camada física de comunicação baseia-se na norma **ISO 9141** (Sistemas de Diagnóstico para Veículos Rodoviários CARB).

---

## 1. Especificações da Camada Física

A linha de comunicação utiliza a tensão da bateria ($V_{\text{bat}}$, tipicamente 12V–14.4V) como referência. Os níveis lógicos são definidos como uma percentagem desta tensão de alimentação:

### Limiares de Tensão do Recetor
*   **"0" Lógico:** $\le 0.3 \times V_{\text{bat}}$
*   **"1" Lógico:** $\ge 0.7 \times V_{\text{bat}}$

### Limiares de Tensão do Transmissor
*   **"0" Lógico:** $\le 0.2 \times V_{\text{bat}}$
*   **"1" Lógico:** $\ge 0.8 \times V_{\text{bat}}$

### Integridade do Sinal e Capacitância
*   **Tempo de Transição:** Uma transição de bit lógico (tempo de subida ou descida) deve demorar menos de 10% da duração total do bit. Isto é medido entre os pontos de 20% e 80% de $V_{\text{bat}}$.
*   **Limites de Capacitância da Linha:** Para evitar a degradação do sinal e o arredondamento de impulsos em cablagens longas:
    *   Capacitância do dispositivo de teste e do cabo de diagnóstico ($C_{\text{te}}$): $\le 2\text{ nF}$
    *   Capacitância da cablagem do veículo ($C_{\text{obw}}$) + capacitância de entrada da ECU ($C_{\text{ecu}}$): $\le 7.6\text{ nF}$
    *   Capacitância máxima da linha de dados em relação à Massa: $\le 500\text{ pF}$

---

## 2. Camada de Ligação de Dados (Parâmetros da Porta Série)

O canal de comunicação original da ECU OBD1 é controlado pela UART interna do MCU.

*   **Baud Rate:** As ferramentas de diagnóstico originais comunicam a **9600 baud** (ou 10400 baud nos primeiros sistemas em conformidade com a norma ISO). 
*   **Configuração:** 8 Bits de Dados, Sem Paridade, 1 Stop Bit (8N1).
*   **Desvios para Afinação (Tuning):** Como a velocidade de 9600 baud é demasiado lenta para a afinação do motor e mapeamento em tempo real, as modificações de ROM de pós-venda (como Crome Gold, Hondata ou Neptune) contornam as rotinas lentas de fábrica da linha K. Estas redirecionam o tráfego de datalogging série para a porta de pinos **`CN2`** na placa da ECU, funcionando a **38400 baud** ou **115200 baud** utilizando níveis lógicos TTL de 5V.

---

## 3. Camada de Aplicação (Estrutura do Protocolo)

O protocolo de comunicação funciona com base numa estrutura de pedido/resposta mestre-escravo. A ferramenta de diagnóstico (mestre) deve iniciar todo o tráfego, e a ECU (escravo) responde.

1.  **Handshake / Despertar (Wakeup):** O dispositivo de teste envia um padrão de despertar específico (sequência com baud rate lenta) para inicializar a linha.
2.  **Comando de Pedido:** O dispositivo de teste transmite um pacote de múltiplos bytes contendo:
    *   Cabeçalho / Endereço de Destino
    *   Modo de Comando (ex: ler registo da RAM, verificar DTCs)
    *   Deslocamento do Endereço de Dados (qual o valor do sensor a ler)
    *   Byte de Checksum (soma de todos os bytes do pacote módulo 256)
3.  **Resposta da ECU:** A ECU verifica o checksum e devolve o bloco de dados solicitado:
    *   Cabeçalho de Resposta
    *   Carga Útil de Dados (ex: um valor em byte que representa a temperatura do líquido de refrigeração do motor escalada em volts)
    *   Byte de Checksum
