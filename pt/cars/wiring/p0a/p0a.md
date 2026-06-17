---
summary: 'P0A 94-95 OBD1 Accord EX imagem anexada é uma 94 P0A-A51 PCB é IPT 02D010B01502 Os dados abaixo foram copiados da página da P13 como um marcador temporário.'
applies_to:
  obd: [1]
  brand: Honda
complexity: advanced
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
    title: P0A
    url: /pgmfi/wiki/library/p0a
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# P0A

P0A 94-95 [OBD1](/cars/wiring/obd1) Accord EX imagem anexada é uma 94 P0A-A51 
[PCB](/cars/wiring/pcb) é IPT 02D010B0-1502. Os dados abaixo foram copiados da página da P13 como um marcador temporário (place holder). Apenas algumas das localizações são realmente conhecidas neste momento.

###  [RAM](/cars/reference/ram) 

| **Location** | **Bytes** | **Description** | **Notes** | | :--- | :--- | :--- | :--- | | | 1 | Sensor MAP | | | | 1 | Sensor TPS | [OBD1\\_8bit TPS](/cars/sensors/obd1-8bit-tps) | | | 2 | [RPM](/cars/sensors/rpm) em formato 16bit | | | | 1 | Sensor [ECT](/cars/sensors/ect) | ?? | | | 1 | Sensor [VSS](/cars/sensors/vss) | km/h | | | 1 | Coluna da tabela | Ver [ROM](/cars/rom/rom) @6050 - escala mBar | | | 1 | Linha da tabela low cam | Ver [ROM](/cars/rom/rom) @6000 - escala [RPM](/cars/sensors/rpm) low cam | | | 1 | Linha da tabela high cam | Ver [ROM](/cars/rom/rom) @6028 - escala [RPM](/cars/sensors/rpm) high cam | | | 2 | Palavra #1 [CEL](/cars/wiring/cel) | contém `0x0000` caso contrário um bit dependendo da [CEL](/cars/wiring/cel) | | | 2 | Palavra #2 [CEL](/cars/wiring/cel) | contém `0x0000` caso contrário um bit dependendo da [CEL](/cars/wiring/cel) | | | 2 | Palavra #3 [CEL](/cars/wiring/cel) | contém `0x0000` caso contrário um bit dependendo da [CEL](/cars/wiring/cel) | | | 2 | Palavra #4 [CEL](/cars/wiring/cel) | contém `0x0000` caso contrário um bit dependendo da [CEL](/cars/wiring/cel) | | | 2 | Corte de Rotação Real | [OBD1\\_16bit RPM](/cars/sensors/obd1-16bit-rpm) | | | 2 | Retoma de Rotação Real | [OBD1\\_16bit RPM](/cars/sensors/obd1-16bit-rpm) | | | 1 | [RPM](/cars/sensors/rpm) atual em formato 8bit | | | | 1b | VTEC Ativo | ?? | | | 1b | Entrada do Interruptor de A/C | Se o pino B5 (ACS) for ligado à massa, `0x0224`.0 lerá 1 | | | 1 | [RPM](/cars/sensors/rpm) em formato 8bit | | | | 1 | Sensor de O2 | ??? | | | 1 | Sensor [IAT](/cars/sensors/iat) | 0v-5v `0x00`-`0xFF` | | | 1 | Sensor Baro | 0v-5v `0x00`-`0xFF` | | | 1 | Sensor [ECT](/cars/sensors/ect) | 0v-5v `0x00`-`0xFF` |

###  [ROM](/cars/rom/rom) 

| **Location** | **Bytes** | **Description** | **Notes** | | :--- | :--- | :--- | :--- | | 0C90 | 4 | Instrução de Desvio de Checksum | Alterar 909DF17F->03A40C00 para desativar o checksum | | | 2 | Reset do Limite de Rotação High Cam | Movido para a memória aqui, bem como nas entradas posteriores | | | 2 | Definição do Limite de Rotação High Cam | Movido para a memória aqui, bem como nas entradas posteriores | | | 1 | Limitador de Velocidade | 0-255km/h (0-159MPH) FF desativa o limitador | | | 1 | Verificação de Temp. do Líquido do VTEC | (`0x44` ativa, `0xFF` desativa) | | | 2 | Reset do Limite de Rotação Low Cam | Formato [OBD1\\_16bit RPM](/cars/sensors/obd1-16bit-rpm) | | | 2 | Definição do Limite de Rotação Low Cam | Formato [OBD1\\_16bit RPM](/cars/sensors/obd1-16bit-rpm) | | | 2 | Reset do Limite de Rotação High Cam | Formato [OBD1\\_16bit RPM](/cars/sensors/obd1-16bit-rpm) | | | 2 | Definição do Limite de Rotação High Cam | Formato [OBD1\\_16bit RPM](/cars/sensors/obd1-16bit-rpm) | | 6000 | 40 | Escalar de RPM Low Cam 1x40 | Cada escalar está no formato [OBD1\\_16bit RPM](/cars/sensors/obd1-16bit-rpm) | | 6028 | 40 | Escalar de RPM High Cam 1x40 | Cada escalar está no formato [OBD1\\_16bit RPM](/cars/sensors/obd1-16bit-rpm) | | 6050 | 10 | Escalar MAP Low e High Cam 1x10 | \\[OBD1\\_8bitMBar\\] | | 605A | 40 | Um escalar? Ou Multiplicador? 1x40 | Formato 16bit | | 6082 | 40 | Um escalar? Ou Multiplicador? 1x40 | Formato 16bit | | 60AA | 200 | Tabela de Combustível Low Cam | Fórmula de Conversão Desconhecida | | 6172 | 200 | Tabela de Combustível High Cam | Fórmula de Conversão Desconhecida | | 623A | 110 | Tabela Extra - sem ideia, semelhante aos mapas @6316 & 6384 | 10 col x 11 linhas | | 62A8 | 110 | Tabela Extra - sem ideia, semelhante aos mapas @6316 & 6384 | 10 col x 11 linhas | | 6316 | 110 | Tabela Extra - sem ideia, tudo 80s | 10 col x 11 linhas | | 6384 | 110 | Tabela Extra - sem ideia, tudo 80s | 10 col x 11 linhas | | 63F8 | 200 | Tabela de Ignição Low Cam | [OBD1\\_8bit Advance](/cars/sensors/obd1-8bit-advance) | | 64C0 | 100 | Tabela de Ignição Low Cam Extra | 10 col x 10 linhas | | 642E | 100 | Tabela de Ignição Low Cam Extra | 10 col x 10 linhas | | 659C | 200 | Tabela de Ignição High Cam | [OBD1\\_8bit Advance](/cars/sensors/obd1-8bit-advance) | | 6664 | 100 | Tabela de Ignição High Cam Extra | 10 col x 10 linhas | | 66D2 | 100 | Tabela de Ignição High Cam Extra | 10 col x 10 linhas | | 681C | 110 | Tabela Extra - sem ideia, tudo 00s | 10 col x 11 linhas | | 688A | 120 | Tabela Extra - sem ideia, tudo 00s | 10 col x 12 linhas | |7FF1|1|Modo Debug/Teste????| `0xFF` ativa, `0x00` desativa???? [aqui]()|4-95 [OBD1](/cars/wiring/obd1) Accord EX imagem anexada é uma 94 P0A-A51 
[PCB](/cars/wiring/pcb) é IPT 02D010B0-1502 
<figure>
    <img src="P0A_A51.JPG" alt="Speedz">
    <figcaption>Speedz</figcaption>
</figure>
