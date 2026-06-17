---
summary: 'Consulte http://www.marklamond.co.uk/techhonda/pgmfi/o2input/o2input.htm para obter detalhes. Isto permite-lhe modificar a sua ECU para entrada de 0-5V.'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: intermediate
tags:
  - ecu
  - referência
  - afinação
  - rom
  - sensores
sources:
  - name: 'pgmfi.org wiki'
    title: 'O2 Input Mod'
    url: /pgmfi/wiki/library/o2-input-mod
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Modificação da Entrada de O2 (O2 Input Mod)

Consulte [http://www.marklamond.co.uk/tech-honda/pgm-fi/o2-input/o2-input.htm](http://www.marklamond.co.uk/tech-honda/pgm-fi/o2-input/o2-input.htm) para obter detalhes. Isto permite-lhe modificar a sua ECU para entrada de 0-5V. O [ADC](/cars/wiring/adc) converte a tensão analógica de 0-5V, neste caso, numa representação numérica dessa tensão que o [CPU](/cars/reference/cpu) consegue compreender e armazenar na sua memória. Repare que digo 0-5V - isto deve-se ao facto de o [ADC](/cars/wiring/adc) estar configurado para ler de 0-5V, embora a entrada de O2 seja processada de modo a limitar a tensão máxima que o [ADC](/cars/wiring/adc) lê a 3,8V. A forma mais simples de descobrir qual era o problema seria aplicar 5V na entrada de O2 e observar se esta se alterava ao longo do percurso. Feito isto, descobriu-se que a etapa do amplificador operacional (Op-Amp) estava a limitar a tensão lida pela [ECU](/cars/ecu/ecu). Sendo este o caso, contornei o op-amp levantando uma resistência e apliquei 5V diretamente ao Mux, e, sem grande surpresa, vemos agora a [ECU](/cars/ecu/ecu) a ler até 5V (ou o mais próximo disso que alguma vez conseguirá) - excelente! ** Retirado da página de Marklamond ![standard-o2_small.gif](standard-o2_small.gif)![modified-o2_small.gif](modified-o2_small.gif)Imagem real: Faça isto primeiro: ![closeup_indexed_955.jpg](closeup_indexed_955.jpg)Depois, dobre o terminal do condensador (CAP) e use-o como jumper, desta forma: ![bottom_jumpered_indexed_123.jpg](bottom_jumpered_indexed_123.jpg)
