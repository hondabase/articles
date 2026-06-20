---
summary: 'Aplicação da Lei dos Gases Ideais nos sistemas de gestão de motor Honda baseados em velocidade-densidade para calcular os requisitos de combustível com base na pressão e temperatura.'
tags: [tuning, sensors, reference]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Lei dos Gases Ideais'
    url: /pgmfi/wiki/library/ideal-gas-law
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Lei dos Gases Ideais

A Lei dos Gases Ideais é uma equação de que se pode ou não lembrar da química do ensino secundário. **PV = nRT**

- **P** = Pressão (deve ser numa escala de [Pressão Absoluta](/cars/diagnostics/absolute-pressure))
- **V** = Volume
- **n** = número de moles (número de átomos) de gás
- **R** = constante dos gases ideais = 8.3145 J/mol K
- **T** = temperatura (sempre em Kelvin para este cálculo - escala absoluta)

A forma da lei dos gases ideais mais aplicável à gestão do motor é **n = PV / RT** Ao resolver para **n**, estamos a resolver para o fluxo de ar real que entra no motor, estimado pelos fatores de pressão, temperatura e volume medidos noutros locais. Um artigo aleatório pesquisado no Google de uma aula universitária: [http://www.chm.davidson.edu/ChemistryApplets/GasLaws/GasConstant.html](http://www.chm.davidson.edu/ChemistryApplets/GasLaws/GasConstant.html)
