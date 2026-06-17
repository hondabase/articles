---
summary: "Cansado de escrever isto repetidamente em fóruns de discussão, decidi adicioná-lo aqui. Se não sabe o que é um controlador Piggyback, leia sobre o assunto primeiro."
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
sources:
  - name: 'pgmfi.org wiki'
    title: 'Why Do Piggybacks Suck'
    url: /pgmfi/wiki/library/why-do-piggybacks-suck
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Porque é que os Piggybacks são Maus

Cansado de escrever isto repetidamente em fóruns de discussão, decidi adicioná-lo aqui. Se não sabe o que é um controlador [Piggyback](/cars/rom/piggy-back), leia sobre o assunto primeiro. Os controladores [Piggyback](/cars/rom/piggy-back) permitem que as [ECU](/cars/ecu/ecu)s de fábrica façam coisas que normalmente não conseguem fazer, como funcionar com injetores maiores ou lidar com boost. Lembre-se de que os controladores piggyback funcionam alterando os sinais dos sensores **antes** de estes chegarem à [ECU](/cars/ecu/ecu). Na maioria das vezes, o principal sinal a ser manipulado é o do [Sensor MAP](/cars/fueling/map-sensor). Isto é **criticamente** importante num carro com sistema [Speed Density](/cars/diagnostics/speed-density). O [Sensor MAP](/cars/fueling/map-sensor) é utilizado pela [ECU](/cars/ecu/ecu) para estimar a quantidade de ar que entra no motor e, portanto, quanto combustível fornecer para corresponder ao fluxo de ar. Quando se empobrece ("lean") a mistura de um carro com um AFC, está simplesmente a diminuir o sinal do [Sensor MAP](/cars/fueling/map-sensor) - a [ECU](/cars/ecu/ecu) responde à diminuição da pressão do coletor fornecendo menos combustível. Quando se enriquece ("richen") a mistura de um carro com um AFC, está simplesmente a aumentar o sinal do [Sensor MAP](/cars/fueling/map-sensor) - a [ECU](/cars/ecu/ecu) responde ao aumento da pressão do coletor fornecendo menos combustível. A alteração na dosagem de combustível acontece por uma razão: se olhar para uma tabela de combustível, os valores do [Sensor MAP](/cars/fueling/map-sensor) correspondem às colunas. Ao aumentar ou diminuir o sinal do [Sensor MAP](/cars/fueling/map-sensor), está simplesmente a fazer com que a [ECU](/cars/ecu/ecu) utilize uma coluna diferente da que utilizaria originalmente. (consulte [Compreender Tabelas](/cars/fueling/understanding-maps) se precisar de ajuda para compreender a leitura de tabelas de Combustível e Ignição). Mas espere, o [Sensor MAP](/cars/fueling/map-sensor) também não é utilizado para determinar as necessidades de ignição? Quando se empobrece a mistura de um carro com um [Piggyback](/cars/rom/piggy-back), também é muito provável que tenha **avançado o ponto de ignição.** Quando se enriquece a mistura de um carro com um [Piggyback](/cars/rom/piggy-back), também é muito provável que tenha **atrasado o ponto de ignição.** Olhe para as tendências horizontais (à medida que a pressão MAP muda) numa tabela de ignição, e verá porque é que isto acontece. Isto ajuda a explicar por que razão tantos carros com turbo/compressor a funcionar com o "AFC hack" têm problemas devido ao avanço excessivo da ignição. **A conclusão:** os Controladores [Piggyback](/cars/rom/piggy-back) são maus porque não se pode ajustar o combustível e a ignição de forma independente. Qualquer alteração no combustível produzirá também uma alteração na ignição, e muitas vezes isso é indesejável.
