---
summary: 'Conversor Digital para Analógico. O processo de pegar num valor digital e convertê-lo num sinal analógico de algum tipo.'
tags: [tuning, rom, sensors, reference]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: DAC
    url: /pgmfi/wiki/library/dac
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# DAC

Conversor Digital para Analógico (Digital to Analog Converter). O processo de pegar num valor digital e convertê-lo num sinal analógico de algum tipo. Usaremos como exemplo um [DAC](/cars/rom/dac) de 8 bits com uma referência de 5,00V. O [DAC](/cars/rom/dac) produz uma tensão (que pode ser medida com um DVM/multímetro) que varia de (geralmente) zero até à tensão de referência, sendo diretamente proporcional à entrada. `0x0` = saída de 0V. `0xff` (escala completa no nosso exemplo) = saída de 5,00V. Fórmula geral: Vout = Vref * count / 2^n. Onde 2^n é o número de bits do conversor. Para o nosso exemplo usámos um conversor de 8 bits, logo 2^8 = 256 combinações possíveis. O zero é um valor válido, consumindo uma das nossas combinações, pelo que a gama total é de 0 a 255 contagens. Assim, refazendo a nossa equação geral: Vout = 5,00V 

* count / 255 = 0,0196 * count. Isto significa que pode produzir qualquer valor DC com uma precisão de aproximadamente 20mv. Bastante útil! Os [DAC](/cars/rom/dac)s de maior resolução oferecem mais passos, o que permite uma melhor resolução. Por exemplo, um [DAC](/cars/rom/dac) de 12 bits forneceria passos de 1,22mv, 16 vezes melhor do que o componente de 8 bits.
