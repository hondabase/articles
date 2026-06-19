---
summary: 'Guia de hardware passo a passo para adicionar um circuito de sensor de detonação a ECUs Honda P30 OBD1 não equipadas, utilizando modificações de componentes específicos.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Add Knock To P30G00'
    url: /pgmfi/wiki/library/add-knock-to-p30g00
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Adicionar Detonação (Knock) à P30G00

Nas placas 1720 ou 11f0 eu fiz: remover `R140`, `R141` - 10k, adicionar `R107`, `R115`, `R116` - 220R. Também adicionei (podem não ser essenciais): `C94` - 4u7 16v de tântalo, `Q20` - a143. Nas placas 1550-150x: remover `R78`, `R77` (lado oposto / Reverse Side), adicionar `R37` (lado oposto), `R50` (lado oposto), `R38` - marcado como 221, e adicionar `C82` - 4u7 16v de tântalo. Pode converter uma P75 para P30/72. As únicas que vi utilizam a placa 1550 e não têm KS (knock sensor). Já converti uma para P72 no passado. Essa que tem é uma versão americana (US)? Também já usei uma placa P29 1550 e adicionei KS, O2 aquecida e código VTEC [DOHC](/cars/sensors/dohc)... por exemplo. A própria placa de KS foi documentada noutro local no que diz respeito ao ajuste da frequência do KS - assumo que seja o `R12` e `R15` a que se refere. A frequência do sensor de detonação e, consequentemente, o seu funcionamento, são afetados pelo diâmetro (bore) do cilindro. Pelo que consigo perceber, a placa de detonação de `cada` [ECU](/cars/ecu/ecu) é afinada para características específicas do motor, a fim de filtrar o ruído do motor da detonação propriamente dita... usar uma placa de detonação num motor diferente daquele para o qual foi concebida poderá não ser muito eficaz...
