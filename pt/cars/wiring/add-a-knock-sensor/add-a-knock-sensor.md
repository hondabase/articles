---
summary: 'Adicionar um sensor de detonação (knock sensor) a um motor que não vinha equipado com um de fábrica.'
applies_to:
  obd: [1]
complexity: intermediate
tags:
  - knock
  - sensor
  - wiring
sources:
  - name: 'pgmfi.org wiki'
    title: 'Add A Knock Sensor'
    url: /pgmfi/wiki/library/add-a-knock-sensor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Adicionar um Sensor de Detonação (Knock Sensor)

Para adicionar um Sensor de Detonação (Knock Sensor) a uma P75, eis o que fiz:

1. Remova a placa de detonação (knock board) de uma P30 JDM
2. Mova a tira de conectores do porto "A" para o porto "B"
3. Remova `R12`
4. Adicione `R15` e `R11` (ambos de 100 ohm... pode reutilizar o `R12`)
5. Solde-o à conversão p75/p72 na localização FC1

E já está. Se já converteu a p75 para uma p72, então tem agora uma placa p72 100% funcional. Avance, ative o sensor de detonação no seu código da p72 e divirta-se!! -Andrew

**Nota:** Eu recuperei uma ECU JDM de sucata de uma sucateira e o processo para utilizar uma placa de detonação de uma P72 JDM é o mesmo, com a exceção de mover a tira de conectores do porto do conector B para o porto do conector A. Acredito que era isto que o Andrew estava a tentar dizer acima, apenas um pequeno erro de digitação, penso eu? -S\_K
