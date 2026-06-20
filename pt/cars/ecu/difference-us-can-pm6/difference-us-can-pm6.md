---
summary: 'Explica as diferenças de hardware entre as ECUs PM6 OBD0 USDM e Canadianas e como contornar o CEL do Código 20 do Electrical Load Detector (ELD) cortando o jumper BR1.'
tags: [ecu, reference]
applies_to:
  make: Honda
  ecus: [PM6]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Diferença Us Can PM6'
    url: /pgmfi/wiki/library/difference-us-can-pm6
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Diferenças entre as ECUs PM6 OBD0 USDM e Canadiana (Bypass do ELD)

A ECU PM6 OBD0 é a unidade de controlo do motor de fábrica para o Honda Civic Si e CRX Si de 1988–1991. Embora os mapas de combustível e ignição armazenados nos seus chips ROM sejam idênticos, existe uma diferença física de hardware entre as ECUs vendidas nos Estados Unidos e as vendidas no Canadá.

Esta diferença está relacionada com o circuito do **Electrical Load Detector (ELD)**.

---

## 1. O Sistema Electrical Load Detector (ELD)

O ELD é um sensor localizado dentro da caixa de fusíveis do compartimento do motor. Ele monitoriza o consumo de corrente elétrica do alternador e da bateria (como faróis, motores do ventilador e ventoinhas do radiador). O ELD envia um sinal à ECU, permitindo-lhe aumentar a velocidade de ralenti do motor ou ajustar a saída do alternador para evitar a descarga da bateria.

* **Civic / CRX USDM:** Equipado com um ELD na caixa de fusíveis do motor. A ECU PM6 USDM monitoriza ativamente este pino de entrada do sensor (pino B14 no conetor OBD0).

* **Civic / CRX Canadiano:** Estes modelos não foram construídos com um ELD. A ECU PM6 de especificação canadiana tem este circuito de monitorização do sensor desativado no hardware.

### Sintomas de Incompatibilidade (Código 20)

Se instalar uma ECU PM6 USDM num veículo canadiano, ou num chassis com swap de motor que não tenha a cablagem do ELD, a ECU detetará a falta de tensão do sensor. Isto aciona o **Código 20 (Electrical Load Detector)**. Embora o Código 20 não coloque o motor em modo de segurança (limp mode), ele aciona a luz de verificação do motor (CEL) e pode interferir com o datalogging de série ativo.

---

## 2. Conversão de Bypass de Hardware (Jumper BR1)

Como a ROM de software é idêntica, o comportamento do ELD da ECU é ditado inteiramente por um jumper de fio físico na placa rotulado como **`BR1`**.

Para contornar o Código 20 e converter uma ECU USDM para as especificações canadianas:
1. Abra a caixa da ECU.
2. Localize o jumper **`BR1`** na placa de circuito principal.
3. Dessolde e remova o fio do jumper `BR1` (ou corte o fio com um alicate de corte), deixando o circuito aberto.

Uma vez aberto o `BR1`, a ECU deixará de monitorizar o pino de entrada do ELD e a CEL do Código 20 será desativada permanentemente.

---

## 3. Imagens de Referência da Placa

Abaixo estão digitalizações comparando os layouts das duas placas:

### Placa Canadiana PM6-`C00`

Note os pontos de solda abertos onde o jumper `BR1` é omitido:

![Scan da placa da ECU PM6-C00 de especificação canadiana](crx90CA_89-10-17modif2.jpg)
*Layout da placa PM6-`C00` do mercado canadiano.*

### Placa USDM PM6-A09

Note o fio do jumper `BR1` instalado perto do conetor de extremidade:

![Scan da placa da ECU PM6-A09 de especificação USDM mostrando o jumper BR1](crx91US_90-12-19modif2.jpg)
*Layout da placa PM6-A09 do mercado USDM.*
