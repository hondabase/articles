---
summary: 'Os scripts do Crome funcionam em P06, P28, P30 (EDM, JDM, USDM), P72; reconhecem a ROM assim como a maioria dos outros editores de ROM.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ecu
  - referencia
  - tuning
  - rom
  - sensores
  - diagnosticos
sources:
  - name: 'pgmfi.org wiki'
    title: 'Add Boost'
    url: /pgmfi/wiki/library/add-boost
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Add Boost

Os scripts do Crome funcionam em P06, P28, P30 (EDM, JDM, USDM), P72; reconhecem a ROM assim como a maioria dos outros editores de ROM. Nem todos os scripts funcionam em todas as [ROM](/cars/rom/rom)s. O de Boost é um caso notável a referir (atualmente funciona principalmente com P72). O script "add boost" do [Crome ROMEditor](/cars/rom/crome-rom-editor) alarga as tabelas originais para que haja uma área dedicada à pressão de sobrealimentação (boost). Isto é muito semelhante ao que a aba de boost do [Uber Data ERM](/cars/rom/uber-data-erm) também faz. O tamanho da tabela original é alterado de 10x20 -> 15x20 (edite isto se não estiver correto). Às últimas 5 colunas são atribuídos valores de MAP na região de boost em vez de atmosférica (NA), permitindo que a [ECU](/cars/ecu/ecu) compreenda o que fazer quando o carro vê pressão/boost (o sensor MAP lê uma pressão superior à pressão atmosférica).
