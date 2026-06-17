---
summary: 'Uma interação de hardware/software determina se um programa numa ECU se comporta como manual ou automático.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - ecu
  - reference
  - sensors
  - diagnosticos
sources:
  - name: 'pgmfi.org wiki'
    title: 'Automático ou Manual'
    url: /pgmfi/wiki/library/auto-or-manual
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Automático ou Manual

Uma interação de hardware/software determina se um programa numa [ECU](/cars/ecu/ecu) se comporta como manual ou automático. A configuração de hardware de RP17/RP18 determina se o hardware da [ECU](/cars/ecu/ecu) está configurado para automático ou manual. Consulte [Auto para Manual](/cars/wiring/auto-to-manual) para saber como alterar o hardware. Se uma [ECU](/cars/ecu/ecu) estiver configurada (com shunts/jumpers) para ser manual, ela funcionará sempre como manual. Os programas da [ECU](/cars/ecu/ecu) são responsáveis por verificar a configuração dos shunts para ativar o controlo da transmissão automática. Isto significa que pode fazer com que uma [ECU](/cars/ecu/ecu) configurada como automática pense que é manual usando um programa que tenha a verificação do circuito automático desativada. O exemplo mais notável deste tipo de programa são os vários programas "mugen". Além disso (posso estar enganado nisto), alguns programas de fábrica ([EDM](/cars/wiring/edm) P30???) não verificam a configuração do shunt da transmissão automática. A maioria das [USDM](/cars/sensors/usdm) (P74/P75, P28, PM6, etc.) verifica ***definitivamente*** os shunts de transmissão automática.

### Resumo:

- Se precisar de converter uma [ECU](/cars/ecu/ecu) automática em manual, pode modificar o hardware de acordo com [Auto para Manual](/cars/wiring/auto-to-manual) ***OU*** desativar a verificação de shunts no software usando um programa modificado (***OU*** fazer ambos).
- Se necessitar que a [ECU](/cars/ecu/ecu) controle uma transmissão automática, deve certificar-se de que utiliza um programa base que verifique os shunts da transmissão automática e que tenha o código necessário. A P28 [USDM](/cars/sensors/usdm) é a minha opção segura (Dave B).
