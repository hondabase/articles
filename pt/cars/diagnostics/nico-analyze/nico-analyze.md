---
summary: 'Autor: XDEep primeiro obrigado ao nico por uma excelente ferramenta. o contratempo de que falo é quando arrastas a barra de deslocamento para cima e para baixo...'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: intermediate
tags:
  - hardware
  - education
  - ecu
  - tuning
  - rom
  - sensors
  - reference
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: 'Nico Analyze'
    url: /pgmfi/wiki/library/nico-analyze
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Nico Analyze

Autor: XDEep primeiro obrigado ao nico por uma excelente ferramenta. o contratempo de que falo é quando arrastas a barra de deslocamento para cima e para baixo, as células são empurradas. por isso, mesmo tendo descoberto onde estavam os mapas, tive dificuldade em distinguir o que era o quê o dia todo até que há instantes alinhei os multiplicadores de combustível numa única linha e todas as tabelas apareceram magicamente diante de mim! ou vai direto para o início dos mapas se já souberes onde é. por isso não arrastes, usa apenas os botões de seta. como alternativa a arrastar, podes alterar o passo para 255 para saltar uma tabela de cada vez. altera de volta para 1 se as tuas células forem empurradas e precisares de as alinhar novamente. a precisão 1 é o equivalente decimal do valor hex em formato de 8 bits. o padrão é precision:2 que é o valor decimal de 16 bits do valor hex, o que torna mais difícil identificar as tabelas ao início. obrigado ao joseph por me encaminhar na direção certa. neste post ele explicou como usar o próprio programa -

---

Re: Calculadora de Mapas Excel P30 Autor: Joseph Davis Data: 11-12-02 22:00 Sammy, tudo o que isto faz é exibir os valores hexadecimais ou binários em decimal. Abre uma [ROM](/cars/rom/rom) para a qual conheças as localizações das tabelas no programa. O offset é a localização de memória que procuras, onde a tabela começa. Colonnes é o número de colunas - algo bastante crítico para o reconhecimento de mapas por iniciantes. Os mapas são 15X17 para [OBD](/cars/wiring/obd)0 e 10X20 para [OBD](/cars/wiring/obd)1 - isso significa Colunas X Linhas. Define para 15 se for [OBD](/cars/wiring/obd)0 e 10 se for [OBD](/cars/wiring/obd)1. O passo (Step) é o número de localizações que o programa salta quando pressionas as setas para cima/baixo no offset (ótimo para procurar uma tabela numa nova [ROM](/cars/rom/rom)). A precisão é apenas um multiplicador. Se a definires para 1, obterás os valores reais de 0 a 255 em decimal em vez de 00-FF em hex - como aprendemos decimal na escola, é mais fácil de trabalhar ao início. Se te sentares com um ficheiro PM6.bin e a calculadora de mapas CRX map calculator.xls, terás zero problemas em identificar os mapas, e a calculadora de mapas terá a mesma parte decimal que vês no Analyser.exe. A malta do P30 criou uma folha de cálculo Excel semelhante se preferires começar por aí. Vês como os valores se distribuem logicamente ao longo do mapa de ignição? O combustível faz o mesmo, mas quanto mais para o lado das colunas fores, tens de começar a usar o multiplicador daquela coluna no fundo do mapa, caso contrário parecerá que o mapa começa pobre, fica rico, depois começa pobre + fica rico um par de vezes ao longo dele.

| **Anexo:** | **Modificar:** | **Tamanho:** | **Data:** | **Quem:** | **Comentário:** |
| :--- | :--- | :--- | :--- | :--- | :--- |
| ![](/pgmfi/wiki/assets/icn/exe.gif) [Analyze.exe](Analyze.exe) | mod | 589312 | 22 Jul 2004 - 16:10 | blundar | Nico's analyze.exe |
