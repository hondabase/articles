---
summary: 'Um guia abrangente sobre como ajustar os mapas de combustível e ignição na ROM da sua ECU Honda para passar nas inspeções de emissões e gases de escape do veículo.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - tuning
  - emissions
  - fueling
sources:
  - name: 'pgmfi.org wiki'
    title: 'Tuning For Smog'
    url: /pgmfi/wiki/library/tuning-for-smog
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Afinar ECUs Honda para Inspeções de Emissões e Gases de Escape

Passar numa inspeção de emissões de escape (teste de gases) com um Honda modificado ou com swap de motor pode ser um desafio, particularmente em regiões com controlos visuais e de gases rigorosos (como as inspeções BAR na Califórnia). Ao compreender a química das emissões de escape e ao otimizar as calibrações da sua ECU, pode reduzir significativamente os poluentes do escape sem sacrificar a fiabilidade do motor.

---

## 1. Compreender os Poluentes do Escape

Os analisadores de emissões medem três poluentes químicos principais no fluxo de gases de escape, medidos em partes por milhão (PPM) ou percentagem de volume:

- **Hidrocarbonetos (HC):** Moléculas de combustível não queimado. Valores elevados de HC são causados por combustão incompleta, que geralmente resulta de falhas de ignição (misfires), temperaturas baixas do motor, entrega excessiva de combustível ou árvores de cames com elevado cruzamento (overlap).
- **Monóxido de Carbono (CO):** Combustível parcialmente queimado. As emissões de CO estão diretamente relacionadas com a relação ar/combustível. Funcionar com mistura rica (excesso de combustível em relação ao oxigénio) causa CO elevado porque não há oxigénio suficiente no cilindro para converter CO em Dióxido de Carbono ($CO_2$) não nocivo.
- **Óxidos de Azoto (NOx):** Compostos formados quando as temperaturas da câmara de combustão excedem os **2.500 °F (1.370 °C)**. Sob calor e pressão extremos, o azoto e o oxigénio presentes no ar fundem-se. Valores elevados de NOx são causados por avanço excessivo do ponto de ignição, misturas ar/combustível pobres ou pistões de alta compressão.

---

## 2. Química do Escape vs. Relação Ar/Combustível (AFR)

A afinação para emissões requer o equilíbrio da relação ar/combustível. Cada poluente comporta-se de forma diferente à medida que a mistura se altera:

- **Mistura Rica (AFR < 14.7):** Reduz as temperaturas da câmara de combustão (reduzindo o NOx), mas aumenta drasticamente as emissões de HC e CO devido ao combustível não queimado.
- **Mistura Pobre (AFR > 14.7):** Reduz as emissões de CO e HC, mas aumenta as temperaturas dos cilindros, o que faz disparar o NOx.
- **Alvo Estequiométrico (14.7:1):** O ponto de funcionamento ideal onde um catalisador de três vias funciona com a máxima eficiência, convertendo HC, CO e NOx simultaneamente.

---

## 3. Estratégias de Calibração para Passar nas Emissões

Para otimizar um mapa de ECU customizado (como uma calibração de ROM Crome ou Hondata) para um teste de gases, foque-se nas faixas de cruzeiro de baixa carga (as primeiras 4 a 6 colunas dos mapas de vácuo):

### Retardar o Ponto de Ignição (Faixas de Cruzeiro)
Pistões de maior compressão ou cabeças de motor retificadas aceleram a propagação da chama dentro do cilindro. Isto requer o atraso (retard) do ponto para evitar que as pressões de pico no cilindro ocorram demasiado cedo, o que gera temperaturas de combustão elevadas.
- **Dica de Afinação:** Retire **2° a 4° de avanço de ignição** nas colunas 1–6 nas faixas de RPM testadas durante o teste de gases (geralmente entre 1.500 e 3.000 RPM). Isto reduz as temperaturas de pico da câmara de combustão e diminui significativamente as emissões de NOx.

### Manter a Estequiometria em Closed-Loop (Circuito Fechado)
Não desative o sensor de oxigénio (sonda lambda) de fábrica nem force o funcionamento do motor em open loop (circuito aberto) permanente para um teste de emissões.
- **Dica de Afinação:** Certifique-se de que o sensor de oxigénio de fábrica de 1 ou 4 fios está totalmente funcional e ativo no software da ECU. A ECU deve ter permissão para oscilar em torno do alvo estequiométrico de 14.7:1. Esta oscilação cíclica permite que o catalisador armazene e liberte oxigénio, permitindo a redução química de NOx e a oxidação de HC/CO.
- *Aviso:* Desativar o sensor de O2 no código ativará a luz de verificação do motor (CEL) no painel ou falhará nos monitores de prontidão OBD2, resultando numa reprovação automática na inspeção.

### Controlar o Enriquecimento Transitório (Tip-In)
O "tip-in" refere-se ao breve enriquecimento de combustível quando a borboleta de admissão (throttle) é aberta rapidamente. Se o enriquecimento no tip-in for demasiado agressivo, causará picos ricos momentâneos que aparecerão no analisador como HC e CO elevados.
- **Dica de Afinação:** Suavize e reduza ligeiramente as tabelas de combustível de tip-in para evitar picos ricos transitórios durante as transições de velocidade nos rolos do dinamómetro.

---

## 4. Lista de Verificação Pré-Inspeção

Os mapas de afinação por si só não conseguem compensar hardware desgastado. Certifique-se de verificar os seguintes itens antes do teste:

1. **Temperatura do Catalisador:** Um catalisador precisa de estar quente para funcionar. Conduza o veículo em autoestrada durante pelo menos 15 a 20 minutes imediatamente antes de chegar ao centro de inspeção para garantir que o catalisador está totalmente ativo ("lit off").
2. **Velas de Ignição Novas:** Instale velas de ignição novas e com a folga (gap) correta. Uma faísca fraca ou uma folga incorreta causam pequenas falhas de ignição que resultam em HC elevado no escape.
3. **Verificar o Funcionamento do Termóstato:** Se o seu motor funcionar a frio (devido a um termóstato em falta ou preso aberto), a ECU permanecerá no modo de "enriquecimento de arranque a frio", funcionando com mistura rica e impedindo o motor de entrar em modo closed-loop.
4. **Conformidade Visual:** Certifique-se de que todos os componentes do swap do motor cumprem as diretrizes locais. Para inspeções BAR, todas as peças pós-venda (coletores, coletores de admissão) devem exibir um número de Ordem Executiva (EO) CARB válido, e não deve haver hardware de afinação ou cabos de datalogging expostos. Consulte o [guia de gerações OBD](/cars/wiring/obd) para detalhes sobre as configurações de fábrica.
