---
summary: 'Um guia abrangente de resolução de problemas para diagnosticar e resolver problemas de ECUs Honda, incluindo luzes CEL sólidas, códigos de diagnóstico de problemas (DTC) e problemas de falta de arranque do motor em veículos OBD0 e OBD1.'
tags: [ecu, diagnostics]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Ecu Troubleshooting'
    url: /pgmfi/wiki/library/ecu-troubleshooting
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Resolução de Problemas da ECU

"A minha [ECU](/cars/ecu/ecu) com chip não funciona! Ajuda!" Quando diz "não funciona", o que quer dizer com isso? Existem alguns problemas comuns encontrados ao instalar chips (chipping) em [ECU](/cars/ecu/ecu)s:

- Por vezes, a CEL (luz avisadora do motor) acende-se e apresenta um padrão de piscadelas indicando a presença de um código de erro. Consulte Verificar Códigos de Erro.
- Por vezes, a CEL acende-se e permanece continuamente acesa. As tentativas de efetuar um shunt no conector de diagnóstico de serviço para verificar as piscadelas de erro falham. Consulte Resolução de Problemas de CEL Fixa.
- Por vezes, a CEL não está acesa, mas o carro continua a funcionar muito mal. Consulte Resolução de Problemas de Funcionamento.
- Para problemas persistentes de controlo de ralenti (como ralenti baixo ou oscilante) ou Código 14 da Luz Avisadora do Motor, consulte o guia [Correção do Circuito do IACV - R58 e R59](/cars/diagnostics/iacv-circuit-fix-r58-r59).

Isto é um trabalho em progresso - por favor, sinta-se à vontade para adicionar as suas ideias e experiências. O CARRO NÃO FUNCIONA \* Primeiro, certifique-se de que o LED da [ECU](/cars/ecu/ecu) pisca em KOEO (Key On Engine Off - Chave Ligada, Motor Desligado) para ver se a alimentação da [ECU](/cars/ecu/ecu) está operacional. Outra forma de descobrir se a ECU tem alimentação e ligação à massa no estado KOEO é medir a alimentação de qualquer sensor, por exemplo o sensor TPS. Se vir +5V, a [ECU](/cars/ecu/ecu) está normalmente ligada à massa e alimentada. Caso contrário, significa que a ECU não tem alimentação nem ligação à massa. A causa pode ser o relé principal (main relay) perto do painel. São dois relés numa única caixa. Após ligar a ignição (ON), um dos relés ativa-se e fornece energia à [ECU](/cars/ecu/ecu). Depois de a [ECU](/cars/ecu/ecu) ser alimentada, esta liga o segundo relé à massa, fornecendo massa à bomba de combustível. Irá ouvir o som da bomba de combustível a funcionar. A luz MIL também se desliga após 2 segundos.
