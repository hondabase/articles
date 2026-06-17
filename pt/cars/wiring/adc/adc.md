---
summary: 'Conversor Analógico para Digital: Um circuito integrado (IC) que converte um sinal analógico numa representação digital.'
applies_to:
  obd: [0, 1, 2]
  brand: Acura
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - wiring
  - conversion
sources:
  - name: 'pgmfi.org wiki'
    title: ADC
    url: /pgmfi/wiki/library/adc
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# ADC

Conversor Analógico para Digital (Analog to Digital Converter): Um circuito integrado (IC) que converte um sinal analógico numa representação digital. Como exemplo, consideremos um [ADC](/cars/wiring/adc) de 8 bits com uma referência de 5,00V. 8 bits: Um "[ADC](/cars/wiring/adc) de 8 bits" significa que este irá converter o sinal de entrada num equivalente de representação numérica de 2^8 (daí vem o "8"). 2^8 = 2*2*2*2*2*2*2*2 = 256 valores possíveis. No mundo digital, o zero é um número legítimo, o qual utiliza uma das combinações possíveis, dando-nos uma saída de contagem de 0 a 255. Referência de 5,00V: A tensão de referência é aquilo com o qual o sinal de entrada é comparado, como uma fração. Se introduzirmos um sinal de 5,00V no nosso [ADC](/cars/wiring/adc), e este estiver a usar uma referência de 5,00V, qual será o resultado de saída? Escala total! No nosso exemplo de 8 bits, a "escala total" é uma contagem de 255, pelo que é isso que obtemos na saída. Uma entrada de sinal zero produzirirá uma saída de zero. De qualquer forma, a matemática resulta em: Saída digital = ((Vin / Vref) * 2^número de bits) - 1 Com isto, pode descobrir exatamente o que o seu software lerá do [ADC](/cars/wiring/adc) com um determinado sinal de entrada. (Para efeitos deste exemplo, excluí o caso de medição de tensões positivas e negativas, algo que não veremos numa [ECU](/cars/ecu/ecu) automóvel.) A conversão analógico-digital ***nunca*** é perfeita. É um processo de aproximação - `cada` valor digital ***exato*** tem de representar uma ***gama*** de valores analógicos. A resolução (normalmente medida in bits) de um conversor analógico para digital representa em quantos valores possíveis a gama analógica pode ser dividida.
