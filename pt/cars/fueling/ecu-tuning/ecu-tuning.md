---
summary: 'Um guia introdutório sobre afinação de combustível e ignição em ECUs Honda. Aprenda a calibrar relações ar-combustível, avanço de ignição e a realizar registo de dados de estrada (road logging).'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - tuning
  - ecu
  - fueling
  - ignition
sources:
  - name: 'pgmfi.org wiki'
    title: 'Ecu Tuning'
    url: /pgmfi/wiki/library/ecu-tuning
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Introdução à Afinação de ECUs Honda

A afinação de uma Unidade de Controlo do Motor (ECU) Honda envolve a calibração dos mapas de entrega de combustível e de ponto de ignição para corresponder às características de admissão de ar do motor. Quer esteja a afinar um motor naturalmente aspirado com modificações básicas (bolt-ons) ou uma configuração turbo personalizada, compreender as ferramentas fundamentais e o fluxo de trabalho é essencial para alcançar uma potência fiável e prevenir falhas no motor.

## Ferramentas de Afinação Cruciais

Não pode afinar um motor de forma segura ou precisa sem monitorizar os parâmetros em tempo real. Antes de tentar modificar os mapas, deve ter as seguintes ferramentas:

- **Sensor de Oxigénio de Banda Larga (Wideband O2):** Um sensor de oxigénio de banda estreita (narrowband) padrão apenas é capaz de ler a relação ar-combustível estequiométrica (14.7:1) com cargas baixas. Um sensor de oxigénio de banda larga é crítico para monitorizar as relações ar-combustível (AFR) em tempo real em toda a gama de carga do motor (especialmente em aceleração total - WOT).
- **Configuração de Registo de Dados (Datalogging):** Um cabo de registo de dados permite que o seu portátil registe parâmetros críticos da ECU — como a Velocidade do Motor (RPM), Pressão Absoluta do Coletor (MAP), Posição do Acelerador (TPS) e Ponto de Ignição — simultaneamente com os dados de AFR de banda larga.
- **Sensor de Temperatura dos Gases de Escape (EGT) (Opcional):** A monitorização da temperatura dos gases de escape ajuda a verificar o ponto de ignição. As alterações no ponto de ignição têm um efeito direto na EGT (atrasar o ponto aumenta a EGT, enquanto avançar o ponto diminui a EGT, até ao ponto de combustão completa).
- **Programador em Tempo Real (RTP) / Emulador (Opcional):** Hardware como o Moates Ostrich permite modificar mapas em tempo real com o motor a trabalhar, eliminando a necessidade de desligar constantemente o carro e gravar novos chips.

---

## Objetivos de Afinação Base e Regras de Segurança

Para motores Honda turboalimentados de utilização diária, os seguintes parâmetros fornecem um ponto de partida seguro para evitar a detonação:

| Parâmetro | Gama de Pressão (Boost) / Compressão | Valor Alvo |
| :--- | :--- | :--- |
| **Relação Ar-Combustível (AFR)** | Boost < 10 psi | AFR de **12.0:1** |
| **Relação Ar-Combustível (AFR)** | Boost 10 a 16 psi | AFR de **11.0:1** |
| **Atraso de Ignição** | Taxa de compressão $\le$ 9.5:1 | **1.0° de atraso** por psi de boost |
| **Atraso de Ignição** | Taxa de compressão > 9.5:1 | **Pelo menos 1.25° de atraso** por psi de boost |

---

## O Fluxo de Trabalho de Afinação (Passo a Passo)

A afinação é um processo iterativo. Estabeleça sempre uma base segura de combustível antes de ajustar o ponto de ignição.

### Passo 1: Afinar Primeiro o Combustível em Aceleração Total (WOT)

Não tente afinar a condução a meio acelerador (part-throttle) ou ajustar o ponto de ignição até que os seus mapas de combustível em aceleração total (Wide-Open Throttle) estejam calibrados. 
1. Mantenha os mapas de ponto de ignição conservadores (por exemplo, tabelas originais ou ponto de ignição base atrasado para sobrealimentação).
2. Encontre uma estrada plana e segura (ou utilize um banco de ensaio / dyno) para realizar os registos de dados (pulls).
3. Inicie o teste em 3ª ou 4ª velocidade a uma rotação baixa do motor (por exemplo, 2500 RPM) e pressione o pedal do acelerador a fundo (Wide-Open Throttle). Pise a fundo numa mudança mais alta para colocar uma carga constante e sustentada no motor, permitindo recolher pontos de dados estáveis à medida que a rotação sobe lentamente.
4. Registe as leituras de AFR de banda larga à medida que o motor acelera.
5. Reveja o registo e localize as áreas onde o motor funciona demasiado pobre (AFR > 12.0:1) ou demasiado rico (AFR < 11.5:1).
6. Ajuste as células de combustível correspondentes nas colunas mais à direita (colunas 8–10 nos mapas OBD1) do mapa de combustível ativo. Faça alterações incrementais — ficará surpreendido com a diferença que uma alteração de 3% a 5% no combustível faz.
7. Repita este processo até que o combustível em WOT atinja consistentemente a AFR alvo em toda a gama de RPM.

### Passo 2: Calibrar o Ponto de Ignição

Assim que as suas tabelas de combustível estiverem calibradas para fornecer AFRs estáveis, pode começar a ajustar o avanço de ignição:
- Ajuste o ponto em pequenos incrementos (por exemplo, 0.5 a 1.0 grau de cada vez).
- Monitorize os sinais de detonação (grilar do motor). Se ocorrer detonação, atrase imediatamente o ponto de ignição nessa faixa de carga.
- Acompanhe os valores de EGT. Se as temperaturas dos gases de escape subirem anormalmente sob carga, é frequentemente um sinal de que o ponto está demasiado atrasado, fazendo com que o combustível termine a combustão dentro do coletor de escape.

### Passo 3: Calibrar Mapas de Cruzeiro e Carga Parcial (Part-Throttle)

A condução a meio acelerador (cruising) utiliza as colunas que representam o vácuo (colunas 1–6). 
- Em modo de circuito fechado (closed-loop), a ECU tentará ajustar a compensação de combustível (fuel trim) para atingir uma AFR estequiométrica de 14.7:1 para emissões e economia de combustível.
- Garanta que a transição das colunas de vácuo em carga parcial para as colunas de boost/carga em WOT é suave para evitar picos repentinos de mistura pobre.

## Artigos Relacionados

- [Afinar para Emissões e Inspeção (Smog)](/cars/fueling/tuning-for-smog)
- [Integrar Controladores Wideband O2](/cars/fueling/wide-band-o2)
- [Como Interpretar Mapas de Combustível e Ignição](/cars/fueling/understanding-maps)
