---
summary: 'O que é um sistema de gestão de motor baseado em Velocidade-Densidade (Speed Density)? Os sistemas Speed Density calculam a quantidade de ar que entra no motor utilizando sensores que monitorizam as condições de funcionamento do motor.'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: advanced
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: 'Speed Density'
    url: /pgmfi/wiki/library/speed-density
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Speed Density

O que é um sistema de gestão de motor baseado em [Velocidade-Densidade (Speed Density)](/cars/diagnostics/speed-density)? Os sistemas [Speed Density](/cars/diagnostics/speed-density) calculam a quantidade de ar que entra no motor utilizando sensores que monitorizam as condições de funcionamento do mesmo. A [Lei dos Gases Ideais](/cars/rom/ideal-gas-law) (**PV = nRT**) é a base para este tipo de gestão de motor. Em vez de medir diretamente a quantidade de ar que entra no motor ("n" na equação acima), os sistemas de velocidade-densidade estimam-na utilizando **n = PV / RT**, aplicando posteriormente correções adicionais. Os mapas (tabelas) de combustível numa [ECU](/cars/ecu/ecu) Honda (de um ponto de vista teórico) são mapas de Eficiência Volumétrica (VE). Funcionamento básico:

- É utilizado um [Sensor MAP](/cars/fueling/map-sensor) para medir a pressão do ar no coletor de admissão (termo DENSIDADE em velocidade-densidade). Isto fornece o termo **P** no cálculo da [Lei dos Gases Ideais](/cars/rom/ideal-gas-law).
- A velocidade de rotação do motor (termo VELOCIDADE em velocidade-densidade) é utilizada para estimar o volume de ar que entra no motor, multiplicando a quantidade de ar aspirada para o cilindro em `cada` curso (geralmente a cilindrada dividida por dois) pelo número de rotações do motor. Isto fornece o termo **V** no cálculo da [Lei dos Gases Ideais](/cars/rom/ideal-gas-law).
- O [Sensor de Temperatura do Ar de Admissão (IAT)](/cars/sensors/intake-air-temperature-sensor) mede a temperatura do ar que entra no motor, fornecendo o termo **T** no cálculo da [Lei dos Gases Ideais](/cars/rom/ideal-gas-law).
- **R** é uma constante
- Sabendo **P**, **V**, **R** e **T**, a [ECU](/cars/ecu/ecu) pode então calcular uma estimativa de **n** (moles de ar que entram no motor) a partir dos dados dos sensores e da fórmula **n = PV / RT**

Dado que a gestão por velocidade-densidade calcula o fluxo de ar em vez de o medir diretamente, são frequentemente utilizados fatores adicionais para obter uma melhor estimativa. O [Sensor TPS](/cars/diagnostics/tps-sensor) é fundamental em muitos deles — o enriquecimento por aceleração rápida (TPS tip-in enrichment) é utilizado para fornecer mais combustível do que o sugerido pelo cálculo da [Lei dos Gases Ideais](/cars/rom/ideal-gas-law), de forma a compensar a entrada súbita de ar novo antes de o [Sensor MAP](/cars/fueling/map-sensor) atingir um estado estável. O empobrecimento em desaceleração (off-throttle leaning) é utilizado para evitar que o motor funcione com uma mistura rica após desacelerações repentinas. Aqui estão alguns links para obter mais informações sobre sistemas de velocidade-densidade: - [http://web.archive.org/web/20081203203734/http://web.archive.org/web/20081203203734/http://www.asashop.org/autoinc/jan97/techtotech.htm](http://web.archive.org/web/20081203203734/http://web.archive.org/web/20081203203734/http://www.asashop.org/autoinc/jan97/techtotech.htm) - bom link, não muito técnico.
- [http://web.archive.org/web/20070205103708/http://www.wincom.net:80/trog/efi.html](http://web.archive.org/web/20070205103708/http://www.wincom.net:80/trog/efi.html) - bastante técnico mas com orientação prática.
- [http://www.simcar.com/literature/sae940759/sae940759.htm](http://www.simcar.com/literature/sae940759/sae940759.htm) - artigo **altamente técnico** sobre o uso prático de sistemas de velocidade-densidade para gestão de ar/combustível. Possui ilustrações **excelentes** sobre o papel dos fatores de correção secundários, como aceleração/desaceleração do TPS.
- [Um](http://web.archive.org/web/20050304210413/http://baen.tamu.edu:80/users/lepori/Teaching/BSEN265/Lectures/Energy_Basics.ppt) [Dois](http://web.archive.org/web/20040825011344/http://baen.tamu.edu:80/users/lepori/Teaching/BSEN265/Lectures/ICEng_Power_Eff. PPT) [Três](http://baen.tamu.edu/users/lepori/Teaching/BSEN265/Lectures/Revu_GasLaws.ppt) [Quatro](http://web.archive.org/web/20050913080557/http://baen.tamu.edu:80/users/lepori/Teaching/BSEN265/Lectures/Engine_cycles. PPT) [Cinco](http://web.archive.org/web/20050304211227/http://baen.tamu.edu:80/users/lepori/Teaching/BSEN265/Lectures/PowerTrans_notes.ppt) apresentações de Microsoft Powerpoint de uma aula de engenharia universitária sobre leis dos gases, termodinâmica e motores.
