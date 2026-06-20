---
summary: 'Um guia detalhado de diagnóstico e reparação para o circuito da Válvula de Controlo do Ralenti (IACV) em ECUs Honda OBD1, focando-se especificamente nos resistores R58, R59 e no transistor driver Q21.'
tags: [ecu, repair, diagnostics, idle]
applies_to:
  make: Honda
complexity: advanced
---

# Correção do Circuito da IACV - R58 e R59: Ralenti Baixo

Uma falha no circuito do driver da Válvula de Controlo do Ralenti (IACV) é um problema clássico que afeta as Unidades de Controlo do Motor (ECUs) Honda OBD1, como as P28, P06, P72, P30 e P75. Quando este circuito falha, o motor sofre de problemas extremos de ralenti e é incapaz de regular a rotação de ralenti desejada.

## Sintomas de um Circuito de IACV Queimado

Quando o circuito interno de controlo da IACV da ECU está danificado, apresenta tipicamente os seguintes sintomas:
1. **Luz de Verificação do Motor (CEL) persistente com o Código 14**: Mau funcionamento da Válvula de Controlo do Ralenti (IACV / EACV). O código voltará imediatamente, mesmo após limpar a memória da ECU ou substituir a válvula física.
2. **Ralenti Extremamente Baixo**: O motor pode funcionar em ralenti a 200–400 RPM ou ir abaixo (ir buscar) completamente, a menos que a borboleta de aceleração seja mantida ligeiramente aberta.
3. **Ralenti Inconstante ou Oscilante**: Em algumas configurações, o ralenti pode oscilar repetidamente entre 1000 e 1500 RPM.
4. **Danos Físicos na ECU**: A inspeção visual da placa da ECU revela resistores carbonizados, queimados ou estalados nas localizações **R58** e **R59**, e potencialmente um transistor queimado em **Q21**.

---

## Causa Raiz: Fichas Invertidas

A causa mais comum para a queima deste circuito é um erro humano nas ligações elétricas durante um swap de motor ou na remontagem do coletor de admissão.

Como as fichas da cablagem do motor para o **Sensor de Temperatura do Ar de Admissão (IAT)** (ou do Solenoide de Controlo de Purga / EVAP) e para a **Válvula de Controlo do Ralenti (IACV)** partilham o mesmo tipo de ficha e localização física, são facilmente trocadas.

* **A Ficha da IACV** fornece uma alimentação constante de +12V, com a ECU a comutar o lado de massa (terra) via duty cycle para controlar a válvula.

* **A Ficha do IAT** é um circuito de referência de sensor de 5V vindo da ECU.

* **A Ficha do PCS (Solenoide de Controlo de Purga)** também é um circuito comutado de 12V.

Se ligar por engano a ficha de alimentação de +12V ao sensor IAT (que é um termístor de baixa resistência) ou se trocar as fichas da IACV e do IAT, a corrente elevada é direcionada diretamente para as linhas de retorno/massa de baixa tensão do sensor da ECU, queimando instantaneamente o transistor em **Q21** and os resistores de polarização em **R58** e **R59**.

> [!WARNING]
> **Não ligue uma ECU reparada ou nova até ter verificado as fichas da cablagem do motor!** Se as fichas continuarem trocadas, os novos componentes queimarão no exato momento em que a ignição for ligada.

---

## Identificação de Componentes & Especificações

Para corrigir este problema, deve inspecionar e substituir os seguintes componentes na placa de circuito da ECU (normalmente localizados perto dos conectores principais da cablagem):

| Componente | Localização na Placa | Função | Peça OEM / Especificação | Substituto Comum / Equivalente |
| :--- | :---: | :--- | :--- | :--- |
| **Q21** | Transistor | Driver de massa do lado de baixa para o solenoide da IACV | NEC `01594` (2SD1594) NPN Power Darlington | `2SD1594`, `2SD1998` (D1998), `2SD1020` ou `2SD1415` |
| **R58** | Resistor | Resistor de polarização/limitação de corrente | película de carvão 1k Ohm, 1/4 W (ou 1/2 W) | Resistor de 1k Ohm (tolerância de 5%) |
| **R59** | Resistor | Resistor de polarização/limitação de corrente | película de carvão 1k Ohm, 1/4 W (ou 1/2 W) | Resistor de 1k Ohm (tolerância de 5%) |
| **R61** | Resistor | Resistor de polarização do circuito do driver | película de carvão 1.2k Ohm, 1/4 W | Resistor de 1.2k Ohm (tolerância de 5%) |

*Nota: Nas ECUs JDM de montagem em superfície (SMD) (por exemplo, JDM P30, P08), estes componentes podem ser peças SMD. Certifique-se de verificar a versão do layout da sua placa (por exemplo, placas impressas `11F0`, `1720`, `1980`).*

---

## Procedimento de Reparação

### Passo 1: Verificar & Corrigir a Cablagem do Motor

Antes de abrir a ECU, verifique as fichas da cablagem no motor:
1. Verifique as cores dos fios na ficha da IACV. Nas cablagens USDM, a ficha da IACV deve ter um fio **Amarelo/Preto** (alimentação +12V) e um fio **Azul Claro** ou **Azul/Amarelo** (controlo no Pin A9 da ECU).
2. Verifique a ficha do IAT. Esta tem tipicamente um fio **Vermelho/Amarelo** (sinal de 5V) e um fio **Verde/Branco** (Massa do Sensor).
3. Substitua o sensor IAT caso tenha sido submetido a +12V, pois é provável que esteja derretido ou danificado internamente.

### Passo 2: Extrair a ECU e Inspecionar a Placa

1. Remova a ECU do painel lateral do lado do passageiro (kick panel).
2. Remova as tampas superior e inferior (usando uma chave de fendas Phillips).
3. Procure o transistor **Q21** (montado num pequeno dissipador de calor ou diretamente na placa) e os resistores **R58** e **R59** próximos.
4. Inspecione visualmente se existem resíduos pretos, corpos de resistores carbonizados ou rachaduras no invólucro do transistor.

### Passo 3: Dessoldagem e Substituição de Componentes

1. Utilizando um ferro de soldar de alta qualidade e uma bomba de dessoldar ou malha de dessoldagem, dessolde cuidadosamente os pinos dos componentes queimados.
2. Limpe a área da placa com álcool isopropílico. Verifique se as pistas de cobre da placa de circuito estão levantadas ou queimadas. Se estiverem, precisará de fazer uma ponte (jumper) usando um fio de ligação fino.
3. Instale os novos componentes (prestando atenção à orientação do transistor Q21, que deve ficar voltado para o mesmo lado do original).
4. Solde e corte as pontas excedentes dos terminais.

---

## Artigos Relacionados

- [Referência da Válvula de Controlo do Ralenti (IACV)](/cars/sensors/idle-air-control-valve)
- [Sensor de Temperatura do Ar de Admissão (IAT)](/cars/sensors/intake-air-temperature-sensor)
- [Referência de Aquisição de Componentes de ECU Honda](/cars/ecu/parts-for-ec-us)
- [Famílias de ECUs OBD1 Civic/Integra](/cars/diagnostics/obd1-civic-integra-ec-us)
