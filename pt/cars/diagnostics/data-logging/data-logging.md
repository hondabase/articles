---
summary: "Visão geral técnica dos métodos, interfaces e software para datalogging em ECUs Honda OBD0 e OBD1."
tags: [datalogging, serial, diagnostics, ecu, obd0, obd1]
applies_to:
  obd: [0, 1]
complexity: intermediate
---

# Datalogging em ECUs Honda OBD0 e OBD1

O datalogging permite o registro em tempo real das condições de funcionamento do motor. Este guia descreve os métodos de comunicação serial e as ferramentas de software utilizadas para extrair dados de diagnóstico de ECUs Honda OBD0 e OBD1.

## Métodos de Conexão

A comunicação com a ECU pode ser estabelecida através da porta de diagnóstico original ou via conexão direta na placa da ECU.

| Método | Descrição |
| :--- | :--- |
| **Conector de Diagnóstico (DLC)** | Utiliza a porta de diagnóstico original do veículo para comunicação. |
| **Porta Serial Interna (CN2/CN3)** | Utiliza o conector `CN2` (OBD1) ou `CN3` (OBD0) na placa da ECU, exigindo um módulo de tratamento de dados modificado no firmware. |

> [!IMPORTANT]
> As ECUs originais utilizam uma taxa de transmissão (baud rate) não padrão para portas seriais de PC. A conexão direta requer hardware compatível com níveis de sinal TTL de 5V.

## Interface Elétrica

Para conectar a ECU a um computador moderno, é necessário converter os sinais da ECU para o protocolo do host:

*   **Adaptadores de Nível:** Se o hardware do computador não suportar níveis TTL de 5V, um conversor de nível lógico é obrigatório.
*   **USB para Serial:** Em computadores sem porta serial nativa, deve-se utilizar um adaptador USB-to-Serial de alta qualidade.

Consulte o [guia de resolução de problemas de datalogging](/cars/diagnostics/debugging-data-logging) para obter detalhes sobre a configuração de hardware e drivers.

## Software de Datalogging

O desenvolvimento histórico de datalogging para ECUs Honda baseou-se em módulos de código modificados. As ferramentas legadas incluem:

*   **ECUControl:** Software de referência para datalogging, com suporte histórico para Windows, Palm OS e Pocket PC.
*   **Cuddle:** Ferramenta de datalogging e controle RTP (Real-Time Programming) para sistemas OBD1.
*   **TurboEdit:** Software focado em datalogging e afinação para sistemas OBD0.

## Notas Técnicas

### Jumper P30 JDM
Em unidades P30 JDM, a configuração `J12 = J4` é utilizada para habilitar certas funções de comunicação. A aplicabilidade desta configuração em outras variantes de ECU JDM não é universal e deve ser verificada via esquema elétrico específico.

### Recursos Adicionais
*   [Comunicação de série (serial)](/cars/tuning/serial-communication)
*   [Referência do Conector de Ligação de Dados (DLC)](/cars/wiring/dlc)
*   [Registar um sensor externo de 0-5 V através do pino P30 D12](/cars/tuning/how-to-log-external-data-such-as-an-egt-sensor)