---
summary: 'A Honda utiliza um interruptor high side de 5 pinos em muitas das suas ECUs OBD1 e OBD2 para controlar solenoides, como os de transmissão automática e solenoides VTEC.'
tags: [ecu, reference, tuning, sensors]
applies_to:
  brand: Honda
complexity: intermediate
---

# Interruptor High Side 515X

A Honda utiliza um **interruptor high side de 5 pinos** em muitas das suas [ECU](/cars/ecu/ecu)s [OBD1](/cars/wiring/obd1) e [OBD2](/cars/wiring/obd2) para controlar solenoides, tais como os de transmissão automática e solenoides VTEC.

## Peças OEM Conhecidas

A Allegro / Sanken é o fabricante original (OEM) desta peça. As seguintes peças são conhecidas por funcionar:

*   SK-5050S (original - geralmente em placas 1720)
*   SK-5151S (versão de corrente mais elevada do 5050 - geralmente em placas 11F0/1980)
*   SK-5154S (versão de corrente mais elevada do 5151 - geralmente em placas [OBD2](/cars/wiring/obd2))
*   SI-5151S (alteração de referência da SK-5151S)
*   SI-5154S (alteração de referência da SK-5154S)
*   SI-5151SG (alteração de referência da SI-5151S)
*   SI-5154SG (alteração de referência da SI-5154S)

> [!NOTE]
> Estas peças são frequentemente difíceis de obter devido à sua disponibilidade limitada junto dos distribuidores.

## Substituição Alternativa (IR6220)

Uma alternativa conhecida é o **IR6220-ND**, que pode ser encontrado em distribuidores de eletrónica como a Digikey. O custo é de aproximadamente $4.63 por unidade.

> [!IMPORTANT]
> A instalação do IR6220 requer uma modificação nos pinos para corresponder ao layout da placa. É necessário mover o pino #3 para a posição #5 na placa e o pino #5 para a posição #3 na placa.

> [!CAUTION]
> Utilize manga termoretrátil ou isolamento adequado no pino #3 para evitar qualquer contacto indesejado entre os pinos após a modificação.

![Exemplo de modificação do pino IR6220](dsc00595.jpg)
*Modificação do pino para o IR6220*

> [!NOTE]
> O IPS521 é considerado uma substituição direta para o IR6220.
