---
summary: 'Consulte http://www.marklamond.co.uk/techhonda/pgmfi/o2input/o2input.htm para obter detalhes. Isto permite-lhe modificar a sua ECU para entrada de 0-5V.'
tags: [ecu, referência, afinação, rom, sensores]
applies_to:
  make: Honda
complexity: intermediate
---

# Modificação da Entrada de O2 (O2 Input Mod)

Esta modificação permite que a sua ECU aceite uma entrada de 0-5V para o sensor de O2. Para detalhes completos, consulte o guia original em [http://www.marklamond.co.uk/tech-honda/pgm-fi/o2-input/o2-input.htm](http://www.marklamond.co.uk/tech-honda/pgm-fi/o2-input/o2-input.htm).

## Como funciona o ADC

O [ADC](/cars/wiring/adc) (Conversor Analógico-Digital) converte a tensão analógica de 0-5V, neste caso, numa representação numérica dessa tensão que o [CPU](/cars/reference/cpu) consegue compreender e armazenar na sua memória. Repare que digo 0-5V - isto deve-se ao facto de o [ADC](/cars/wiring/adc) estar configurado para ler de 0-5V, embora a entrada de O2 seja processada de modo a limitar a tensão máxima que o [ADC](/cars/wiring/adc) lê a 3,8V.

## O Problema e a Solução

A forma mais simples de descobrir qual era o problema seria aplicar 5V na entrada de O2 e observar se esta se alterava ao longo do percurso. Feito isto, descobriu-se que a etapa do amplificador operacional (Op-Amp) estava a limitar a tensão lida pela [ECU](/cars/ecu/ecu).

Para contornar o op-amp e permitir que a ECU leia até 5V, siga os passos abaixo:

> [!IMPORTANT]
> *   **Passo 1:** Levante uma resistência e aplique 5V diretamente ao Mux.
> *   **Passo 2:** Dobre o terminal do condensador (CAP) e use-o como jumper.

## Imagens da Modificação

```carousel
![Vista da placa antes da modificação](standard-o2_small.gif)
*Vista da placa antes da modificação da entrada de O2.*
<!-- slide -->
![Vista da placa após a modificação](modified-o2_small.gif)
*Vista da placa após a modificação da entrada de O2.*
<!-- slide -->
![Detalhe da resistência a ser levantada](closeup_indexed_955.jpg)
*Detalhe da resistência a ser levantada para a modificação.*
<!-- slide -->
![Condensador usado como jumper](bottom_jumpered_indexed_123.jpg)
*Condensador dobrado e usado como jumper.*
```
