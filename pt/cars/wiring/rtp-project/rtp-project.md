---
summary: "Blá blá, descrever isto mais tarde. Link para o fórum de discussão. Aqui está uma lista incompleta de encomenda de peças até ao momento. Lista de peças da opção de montagem com MAX233. Peças disponíveis..."
applies_to:
  obd: [0, 1, 2]
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
    title: 'RTP Project'
    url: /pgmfi/wiki/library/rtp-project
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Projeto RTP

Blá blá, descrever isto mais tarde. [link para o fórum](). Aqui está uma lista incompleta de encomenda de peças até ao momento.

## Lista de peças

### Opção de montagem com `MAX233`

- Peças disponíveis na Digi-key

|Qtd|N.º Digi-Key|Descrição|Designador(es)|Preço unitário |1|[399-1760-1-ND](http://www.digikey.com/scripts/DkSearch/dksus.dll?PName?Name=399-1760-1-ND)|COND TANT 220UF 6.3V 20% SMD |`C1` |1.85000 |3|[490-1318-1-ND](http://web.archive.org/web/20050119055802/http://www.digikey.com:80/scripts/DkSearch/dksus.dll?PName?Name=490-1318-1-ND)|COND CER .1UF 10V 10% X5R 0402 |`C2`,`C3`,`C6` |0.05100|* |3|[311-10KGCT-ND](http://web.archive.org/web/20050119055514/http://www.digikey.com:80/scripts/DkSearch/dksus.dll?PName?Name=311-10KGCT-ND)|RES 10K OHM 1/10W 5% 0603 SMD |`R1`-`R3` |0.07000|* |1|[311-100KGCT-ND](http://web.archive.org/web/20050119055352/http://www.digikey.com:80/scripts/DkSearch/dksus.dll?PName?Name=311-100KGCT-ND)|RES 100K OHM 1/10W 5% 0603 SMD |`R4` |0.07000|* |1|[1N4148WDICT-ND](http://web.archive.org/web/20050119055643/http://www.digikey.com:80/scripts/DkSearch/dksus.dll?PName?Name=1N4148WDICT-ND)|DÍODO DE COMUTAÇÃO 75V 400MW SOD-123 |D1 |0.44000 |1|[MMBT4401FSCT-ND](http://web.archive.org/web/20050119055258/http://www.digikey.com:80/scripts/DkSearch/dksus.dll?PName?Name=MMBT4401FSCT-ND)|TRANSÍSTOR GP NPN AMP SOT-23 |`Q1` |0.17000 |1|[ED4628-ND](http://www.digikey.com/scripts/DkSearch/dksus.dll?PName?Name=ED4628-ND)|SUPORTE DE CI 28 PINOS W/W OURO .600 |`IC1` |3.20000|??? |1|[MM74HC00M-ND](http://www.digikey.com/scripts/DkSearch/dksus.dll?PName?Name=MM74HC00M-ND)|CI PORTA NAND QUAD 2 ENTRADAS 14-SOIC |`IC2` |0.39000 |1|[MAX233ACWP-ND](http://web.archive.org/web/20050119055723/http://www.digikey.com:80/scripts/DkSearch/dksus.dll?PName?Name=MAX233ACWP-ND)|CI 2DVR/2RCVR RS232 5V 20-SOIC |?? |10.7600|eek ||||||>* vendido em múltiplos de 10 - Peças disponíveis em allamerican.com

|Qtd|N.º allamerican|Descrição|Designador(es)|Preço unitário |1|[U634H256SC35](http://www1.allamerican.com/direct/product.asp?T%5FPRDKEY=ZMD+U634H256SC35+++++++++&T%5FMFGCOD=ZMD+&T%5FPRDID=U634H256SC35+++++++++)|256KNVSRAM,POWERSTORE,32KX8 SOP32 (300 MIL)|??|7.50 - Peças disponíveis em arrow.com

|Qtd|N.º arrow|Descrição|Designador(es)|Preço unitário |1|STK14C88-N25|256K [NVSRAM](/cars/wiring/nvsram), 25ns, SOIC32 300mil|??|11.56 Os `MAX233` são mesmo um roubo. Os de gama de temperatura alargada custam 14,63 $! É provavelmente mais barato usar apenas um `MAX232` com os malditos condensadores externos. Os chips USB UART [FTDI](http://web.archive.org/web/20260508084903/https://ftdichip.com/) [FT232BM](ds232b12.pdf) podem ser encomendados na [Saelig](https://www.saelig.com) por 5,75 $ cada, 4,25 $ para 100 unidades - nota: encomenda mínima de 30 $. Também precisamos de pinos de cabeçalho/fêmea (pin headers/receptacles/crimp pins), e provavelmente de uma porta RS232 de painel para a versão com `MAX233` e algum tipo de ficha USB para a opção USB. E talvez algum fio Kynar para as modificações necessárias na [ECU](/cars/ecu/ecu).
