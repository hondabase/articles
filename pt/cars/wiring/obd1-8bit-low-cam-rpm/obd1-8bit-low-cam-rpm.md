---
summary: 'Esta é a conversão dos valores de RPM de 8 bits "low cam" utilizados para os pontos de transição de VTEC e nas tabelas low-cam.'
applies_to:
  obd: [1]
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - wiring
  - conversion
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1 8bit Low Cam RPM'
    url: /pgmfi/wiki/library/obd1-8bit-low-cam-rpm
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# RPM de Low Cam de 8 bits OBD1

Esta é a conversão dos valores de [RPM](/cars/sensors/rpm) de 8 bits "low cam" (came baixa) utilizados para os pontos de transição de VTEC e nas tabelas low-cam. Envolve alguma aritmética modular, pelo que é mais fácil dividi-la em alguns passos adicionais.

# Y = valor de entrada, 0 a 256

# seja H = floor(Y/64) ''Onde floor(x) = trunc(x) = int(x) = parte inteira de x. A parte fracionária é truncada. Chame-lhe o que preferir''

# seja L = Y - (H-1)*64

# [RPM](/cars/sensors/rpm) = 1875000 * L 

* 2^H / 240000 Também pode fazer desta forma, utilizando o operador módulo:

# Y = valor de entrada, 0 a 256

# Q = Y div 64 ''(divisão inteira, o mesmo que floor(Y/64) acima)''

# R = Y mod 64 ''(módulo, ou seja, o resto após a divisão)''

# [RPM](/cars/sensors/rpm) = (2^Q)*(floor(R*500/64) + 500) Isto acaba por ser uma escala linear por partes (piecewise):

- `00h`-`40h` = 500-1000 [RPM](/cars/sensors/rpm)
- `40h`-`80h` = 1000-2000 [RPM](/cars/sensors/rpm)
- `80h`-`C0h` = 2000-4000 [RPM](/cars/sensors/rpm)
- `C0h`-`100h` = 4000-8000 [RPM](/cars/sensors/rpm)

---

COMENTÁRIO EDITADO: <---- Escala linear??? Pois sim!... esta fórmula precisa de voltar ao "estirador". Os valores abaixo mostram uma escala exponencial perfeita! Tenho tentado esta equação e ela não obtém valores exatos. A equação do Ben no [BRE](/cars/electronics/bre) é mais precisa, pelo menos nos valores de teste... (Não conheço a fórmula do [BRE](/cars/electronics/bre)) Isto é linear "por partes" (piecewise). Quatro gamas lineares. Não é uma curva exponencial suave. A primeira fórmula segue bastante de perto o código [OBD1](/cars/wiring/obd1), enquanto a segunda é uma simplificação que obtém resultados ligeiramente diferentes com matemática de inteiros. Com base em que critério considera qual delas é mais precisa? Consulte [https://web.archive.org/web/http://pgmfi.org/phorum/read.php?f=13&i=3314&t=2968]() para referência. --AndySloane
