---
summary: Visão geral histórica dos métodos, portas, adaptadores e software para datalogging de ECUs Honda OBD0 e OBD1.
applies_to:
  obd: [0, 1]
complexity: intermediate
tags: [datalogging, serial, diagnostics, ecu]
sources:
  - name: 'pgmfi.org wiki'
    title: 'Data Logging'
    url: /pgmfi/wiki/library/data-logging
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Visão geral do datalogging de ECUs Honda OBD0 e OBD1

O datalogging regista as condições de funcionamento de um motor em marcha. Esta visão geral arquivada descreve os dois métodos de comunicação de série (serial) e os softwares comummente utilizados pela comunidade pioneira de reprogramação de ECUs Honda.

## Métodos de ligação

| Método | Descrição arquivada |
| --- | --- |
| Conector de Ligação de Dados Original (DLC) | Utiliza a via original de comunicação de diagnóstico da ECU através do DLC do veículo |
| Conector de série interno da ECU | Utiliza a porta `CN2` nas ECUs OBD1 ou `CN3` nas ECUs OBD0 com um módulo de tratamento de série modificado no código da ECU |

As ECUs originais OBD0 e OBD1 incluíam capacidade de comunicação de diagnóstico. A fonte refere que a taxa de transmissão (baud rate) de série original não era padrão para as portas de série dos PCs, mas explicitamente não se recorda da taxa exata nem estabelece se um PC poderia utilizá-la diretamente.

Para mais detalhes sobre as interfaces físicas, consulte a [comunicação de série (serial)](/cars/tuning/serial-communication) e a [referência do Conector de Ligação de Dados (DLC)](/cars/wiring/dlc).

## Software histórico

A página arquivada menciona estas ferramentas da comunidade para ROMs que utilizam um módulo de tratamento de série modificado, derivado do código de datalogging original do Doc:

- **ECUControl:** descrito como o software original de datalogging do PGMFI, com suporte histórico para Windows, Palm OS e suporte planeado para Pocket PC.
- **Cuddle:** software histórico de datalogging e controlo RTP para OBD1.
- **TurboEdit:** software histórico de datalogging e afinação automática offline para OBD0.

A página também assinala que o código de datalogging original do Doc continha um erro de programação (bug), sem no entanto o identificar.

## Interface elétrica

Se o hardware do computador não suportar a comunicação TTL de 5 V da ECU, a fonte afirma que é necessário um adaptador de série. Os portáteis mais recentes que não possuem portas de série podiam, em alternativa, utilizar um conversor USB para série (USB-to-serial).

Consulte o guia arquivado do [conversor USB para série de segunda geração](/cars/tuning/second-gen-usb-to-serial-converter) e o [guia de resolução de problemas de datalogging](/cars/diagnostics/debugging-data-logging) para notas de hardware relacionadas.

## Nota sobre o jumper do P30 JDM

A fonte regista `J12 = J4` numa ECU P30 JDM e refere que isto pode aplicar-se a outras ECUs JDM, mas assinala explicitamente que essa aplicabilidade mais ampla é incerta.

## Relacionado

- [Comunicação de série (serial)](/cars/tuning/serial-communication)
- [Conector de Ligação de Dados (DLC)](/cars/wiring/dlc)
- [TurboEdit](/cars/rom/turbo-edit)
- [Conversor USB para série de segunda geração](/cars/tuning/second-gen-usb-to-serial-converter)
- [Resolução de problemas de datalogging de ECU](/cars/diagnostics/debugging-data-logging)
- [Registar um sensor externo de 0-5 V através do pino P30 D12](/cars/tuning/how-to-log-external-data-such-as-an-egt-sensor)
