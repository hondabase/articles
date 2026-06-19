---
summary: 'Guia de resolução de problemas para erros comuns de configuração, problemas de redimensionamento de colunas do sensor MAP e modificações de bytes VTEC no software de afinação TurboEdit OBD0.'
tags: [afinação, rom, software, diagnósticos]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Common TE Problems'
    url: /pgmfi/wiki/library/common-te-problems
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Resolução de Problemas Comuns do TurboEdit (TE)

O TurboEdit é uma suite de edição de ROM amplamente utilizada para as ECUs OBD0 da Honda (principalmente a PM6). Como as ECUs OBD0 dependem de uma estrutura de processador de 8 bits e têm espaço de memória limitado, bases de código personalizadas (como a série `ng`) requerem regras de configuração específicas. 

Abaixo estão os problemas mais comuns encontrados ao editar, redimensionar ou gravar ROMs no TurboEdit.

---

## 1. Luz de Aviso do Motor Ativa (CEL)

Antes de tentar afinar ou calibrar uma ROM personalizada, certifique-se de que o veículo não tem códigos de erro ativos. 
* **O Problema:** Se um erro de sensor acionar a CEL, a ECU entrará no modo de emergência ("limp mode"), utilizando tabelas de ignição e combustível conservadoras.

* **A Solução:** Diagnostique e resolva todas as avarias mecânicas e elétricas dos sensores antes de afinar. Um mapa não pode ser calibrado corretamente se a ECU estiver a ignorar as suas tabelas normais da ROM.

---

## 2. Larguras de Pulso Limitadas (Multiplicador de Combustível Incorreto)

Este problema ocorre tipicamente ao redimensionar mapas para injetores de combustível maiores em bases de código `ngXX`. Se copiar um mapa ou introduzir novos valores, poderá notar que os valores atingem o limite máximo ou são exibidos incorretamente.

### A Restrição Matemática

Como a ECU OBD0 é uma plataforma de 8 bits, o valor decimal armazenado em qualquer endereço de coordenada do mapa (`Dec At Addy`) não pode exceder 255. Na base de código `ng`, o valor bruto do byte é convertido na largura de pulso do injetor (em milissegundos) utilizando as seguintes fórmulas:

$$a = 2^{\text{Column Multiplier}}$$

$$\text{Pulsewidth (ms)} = \frac{\text{Dec At Addy} + \frac{224}{a}}{\frac{208}{a}}$$

Se o multiplicador de coluna for configurado manualmente com um valor demasiado baixo (por exemplo, definido para `3`), a largura máxima de pulso alcançável é restrita a **10,88 ms**, independentemente da carga do motor.

* **A Solução:** No TurboEdit, navegue até **Tools** -> **Options** e certifique-se de que a opção do multiplicador de combustível está definida para **Auto Detect**. Isto permite que o software redimensione o multiplicador de forma dinâmica para evitar limitações.

---

## 3. Alinhamento das Colunas do Sensor MAP (Origem vs. `ng48`)

Ao migrar tabelas de mapas de um ficheiro BIN OBD0 de origem para uma base de código personalizada `ng48`, copiar e colar as tabelas diretamente causará problemas graves de afinação.

### O Desvio nas Colunas de Pressão

Colar diretamente os valores das células desvia o índice de carga porque os cabeçalhos das colunas de pressão (índice MAP) são redimensionados de forma diferente entre as ROMs de fábrica e as ROMs `ng48`:

| Coluna do Mapa | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Origem (inHg)** | 26 | 24 | 22 | 21 | 19 | 18 | 16 | 14 | 13 | 11 | 9 | 8 | 4 | 1 | 1,3 psi |
| **`ng48` (inHg)** | 31 | 29 | 26 | 24 | 22 | 20 | 18 | 16 | 14 | 12 | 10 | 8 | 5 | 2 | 0 psi |

Valores que outrora controlavam o ralenti estável de um motor de fábrica são deslocados para células que representam desaceleração acentuada, fazendo com que o motor funcione com uma mistura pobre ou vá abaixo.

* **A Solução:** Utilize uma folha de cálculo de conversão de mapas (como a antiga calculadora de conversão da Xenocron) para interpolar e redimensionar os valores de combustível/ignição para corresponderem aos cabeçalhos de pressão corretos antes de os inserir no BIN personalizado.

---

## 4. Falha na Ativação do VTEC no `ng60`

Ao utilizar scripts de conversão VTEC ou placas personalizadas numa ECU OBD0, o botão de alternância do VTEC no interface de utilizador do TurboEdit pode não funcionar corretamente.

* **A Solução:** Utilize um editor hexadecimal para sobrescrever manualmente os bytes de controlo do VTEC no BIN da ROM `ng60` nos seguintes offsets:
 

* Alterar o offset **`0x2882`** para **`0x21`**
 * Alterar o offset **`0x2888`** para **`0xA3`**
