---
summary: 'Referência técnica e guia de offsets do mapa de memória para a modificação de ROM personalizada John Cui High-Resolution (Hi-Res) P72.'
tags: [tuning, software]
applies_to:
  make: Acura
  ecus: [P72]
complexity: advanced
---

# Especificações da ROM P72 de Alta Resolução (Hi-Res)

A ECU original OBD1 Acura Integra GS-R P72 utiliza tabelas de combustível e ignição com dimensões de grelha de linhas e colunas diferentes em comparação com a ECU Civic P28. Esta diferença de tamanho torna difícil copiar e colar diretamente mapas calibrados entre ficheiros P28 e P72.

A **ROM P72 Hi-Res** é um binário de ROM P72 modificado de forma personalizada (pioneiramente desenvolvido por John Cui) que ajusta o código das tabelas de consulta (lookup tables) da ECU. Ao redefinir o tamanho das tabelas de consulta internas da P72 para corresponder ao padrão da P28, permite aos afinadores transferir tabelas de mapas diretamente entre calibrações P28 e P72 sem erros de interpolação.

## Mapa de Offset de Memória (Localizações RAM & ROM)

Ao escrever plugins ou scripts personalizados para modificar uma ROM P72 Hi-Res, os programadores devem referenciar estes endereços de memória específicos. Estes endereços diferem dos mapas de ROM P72 originais de fábrica:

| Localização Hex | Comprimento (Bytes) | Descrição | Notas |
| :--- | :---: | :--- | :--- |
| `0x0A50` | 2 | Referência de localização do vetor de valores de RPM de cames baixas (low cam) | |
| `0x0A68` | 2 | Referência de localização do vetor de valores de RPM de cames altas (high cam) | |
| `0x0A71` | 1 | Comprimento do vetor de valores de RPM de cames altas (high cam) | |
| `0x0A80` | 2 | Referência de localização do vetor de valores de RPM de cames altas (alternativo) | |
| `0x0A89` | 1 | Comprimento do vetor de valores de RPM de cames altas (alternativo) | |
| `0x0AA3` | 2 | Referência ao vetor de valores do sensor MAP | |
| `0x0AB8` | 2 | Referência ao vetor de valores do sensor MAP (alternativo) | |
| `0x0ACD` | 2 | Referência ao vetor de valores do sensor MAP (alternativo) | |
| `0x1269` | 2 | Configuração do mapa de combustível de cames altas, tamanho da linha | |
| `0x1277` | 2 | Localização do salto (jump) da consulta de combustível de cames altas | |
| `0x128B` | 2 | Localização do salto (jump) da consulta de combustível de cames baixas | |
