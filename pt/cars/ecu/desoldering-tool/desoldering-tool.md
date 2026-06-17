---
summary: 'Visão geral e comparação de ferramentas manuais de dessoldadura, incluindo bombas de vácuo, malhas e peras de dessoldar.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - hardware
  - education
sources:
  - name: 'pgmfi.org wiki'
    title: 'Desoldering Tool'
    url: /pgmfi/wiki/library/desoldering-tool
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Ferramentas de Dessoldadura para Modificação de ECU

Ao realizar chipping ou modificar uma ECU, remover a soldadura de fábrica de forma limpa, sem danificar as delicadas pistas de cobre, é fundamental. Utiliza-se um [Ferro de Soldar](/cars/ecu/soldering-iron) padrão para derreter a soldadura, enquanto uma ferramenta de dessoldadura é utilizada para a remover. 

Estão vulgarmente disponíveis vários estilos de ferramentas manuais de dessoldadura:

## 1. Bombas de Dessoldar por Êmbolo (Aspiradores de Solda)
Estas ferramentas utilizam um pistão acionado por mola no interior de um cilindro para gerar uma sucção súbita de vácuo quando um botão de libertação é acionado.
*   **Como funciona:** A mola é comprimida manualmente, a ponta de teflon é colocada diretamente contra a junta de solda derretida que está a ser aquecida pelo ferro, e o botão de libertação é premido para libertar o êmbolo, aspirando a solda para a câmara.
*   **Prós/Contras:** Os modelos padrão de plástico podem apresentar uma sucção inconsistente ou sofrer de recuo que pode riscar as pistas se a ferramenta não for segurada com firmeza. Modelos profissionais de alta qualidade (com pontas de silicone) oferecem um desempenho muito melhor.

## 2. Peras de Dessoldar (Estilo Balão de Borracha)
Uma pera de borracha ligada a uma ponta oca permite gerar sucção manual.
*   **Como funciona:** A pera é espremida antes do aquecimento, a ponta é colocada sobre a solda derretida e a pera é libertada para aspirar a solda para o seu interior.
*   **Prós/Contras:** Exigem bombagem manual, o que pode ser cansativo. Existe também o risco de espremer acidentalmente a pera *enquanto* está sobre a junta, o que sopra solda quente de volta para a PCB e pode criar curtos-circuitos.

## 3. Fita / Malha de Dessoldar
Uma malha fina de cobre revestida com fluxo de colofónia (fluxo de resina) que suga a solda derretida de uma junta por ação capilar.
*   **Como funciona:** Coloque a malha diretamente sobre a junta de solda, pressione a ponta quente do ferro de soldar sobre a malha e veja a solda ser absorvida pela malha de cobre.
*   **Prós/Contras:** Excelente para limpar contactos planos de montagem em superfície (SMD) e desimpedir orifícios difíceis, mas às vezes pode ficar colada à placa se o calor for removido demasiado cedo. Consulte o guia de [Dicas de Dessoldadura](/cars/ecu/desoldering-tips) para obter detalhes sobre a utilização correta.
