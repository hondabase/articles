---
summary: "Esta fórmula é usada para converter valores nas escalas das tabelas de high cam para RPMs reais. Se ''x'' for um valor de RPM de escala high-cam de 8 bits, Hi Cam RPM(''x'') = 1875000''x'' / 53248 53248=D000h."
applies_to:
  obd: [1]
complexity: intermediate
tags:
  - ecu
  - reference
  - sensors
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1 8bit High Cam RPM'
    url: /pgmfi/wiki/library/obd1-8bit-high-cam-rpm
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1 8bit High Cam RPM

Esta fórmula é usada para converter valores nas escalas das tabelas de high cam para [RPM](/cars/sensors/rpm)s reais. Se ''x'' for um valor de [RPM](/cars/sensors/rpm) de escala high-cam de 8 bits,

- Hi Cam RPM(''x'') = 1875000*''x'' / 53248

53248=`D000h`. Eis como é calculado usando truques matemáticos padrão de ponto fixo com inteiros: | |MOV er2, `0ach`|; 0805 0 02 00 B5AC4A | |MOV er0, #`0d000h`|; 0808 0 02 00 449800D0 | |CLR A|; 080C 1 02 00 F9 | |DIV|; 080D 1 02 00 9037 | | |; DIV = (er0, A) <-- (er0, A) / er2; neste caso, `0xd0000000` / (1875000/RPM) | | |; usando bytes em vez de words, (r1, r0,`Ah`, Al) <-- (r1, r0,`Ah`, Al) / (r5, r4) |||''... guarda o bit mais significativo de A, decide se a divisão transbordou (overflow), etc...'' | |LB A, r0|; 0817 0 02 00 78 | | |;r0 é o byte menos significativo de er0, que é a word mais significativa do quociente! | |JNE label_081f|; 0818 0 02 00 CE05 |||''... condições de transbordo (overflow), etc...'' |label_081f:|STB A, `0aah`|; 081F 0 02 00 D5AA
