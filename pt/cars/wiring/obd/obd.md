---
summary: 'Uma visão geral das gerações de Diagnóstico de Bordo da Honda (OBD0, OBD1, OBD2a, OBD2b). Saiba as suas diferenças, layouts de conectores e compatibilidade.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - obd
  - reference
  - wiring
sources:
  - name: 'pgmfi.org wiki'
    title: OBD
    url: /pgmfi/wiki/library/obd
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Guia de Gerações OBD da Honda (OBD0, OBD1, OBD2a, OBD2b)

Os sistemas de Diagnóstico de Bordo (OBD) foram introduzidos para monitorizar os sistemas de controlo de emissões e notificar os condutores sobre falhas elétricas ou mecânicas. A Honda desenvolveu várias gerações dos seus sistemas de diagnóstico de Injeção Programada de Combustível (PGM-FI) para cumprir com as diretivas de redução de emissões poluentes. Para entusiastas e mecânicos Honda, compreender as diferenças entre estas gerações é fundamental ao diagnosticar avarias, realizar swaps de motor ou preparar ECUs (colocação de sockets) para reprogramações personalizadas.

---

## 1. Honda OBD0 (1988–1991)

O sistema OBD0 da Honda representa a primeira geração de diagnósticos de injeção eletrónica de combustível, equipando veículos como o Civic de 4ª geração (EF), CRX, e Integra de 2ª geração (DA).

### Principais Características

- **Monitorização de Sensores:** Verificações muito básicas de limites de tensão alta/baixa. A ECU não consegue detetar a degradação lenta de componentes, apenas falhas totais dos sensores (tais como curto-circuitos ou fios cortados).
- **Design do Distribuidor:** Os primeiros modelos usavam mecanismos de distribuidor com avanço de vácuo, transitando para avanço eletrónico nos anos seguintes.
- **Sensor de Oxigénio (Sonda Lambda):** Utiliza um sensor de oxigénio simples de 1 fio sem aquecimento ou configurações antigas de 4 fios com aquecimento, dependendo do motor.

### Ler Códigos de Avaria

As ECUs OBD0 não acendem a Luz de Verificação do Motor (CEL) no painel de instrumentos para piscar códigos de diagnóstico. Em vez disso:
1. Localize a ECU sob a carpete do poço dos pés do passageiro ou sob o banco.
2. Rode a chave de ignição para a posição ON (ligado).
3. Olhe através da janela de visualização na caixa metálica da ECU.
4. Conte as piscadelas do LED vermelho na placa de circuito (ex: 9 flashes indicam uma falha no sensor de posição do cilindro).

---

## 2. Honda OBD1 (1992–1995)

O OBD1 é amplamente considerado a era de ouro para modificações e reprogramações personalizadas de motores Honda. Equipando veículos como o Civic de 5ª geração (EG) e o Integra de 3ª geração (DC), estas ECUs partilham arquiteturas de placa principal padronizadas, tornando-as altamente versáteis para a instalação de sockets de reprogramação.

### Principais Características

- **Verificações de Racionalidade:** O programa da ECU monitoriza os valores de entrada para garantir que são lógicos (racionais) em relação às condições do motor, em vez de apenas verificar se o circuito está aberto ou fechado.
- **Sensores de O2 de 4 Fios com Aquecimento:** Os padrões mudaram para sensores de oxigénio aquecidos para fazer com que o ciclo de controlo de emissões (closed loop) entre em funcionamento mais rapidamente após arranques a frio.
- **Conector de Serviço (SCS):** Um conector de 2 pinos usado para contornar os controlos de avanço de ignição e fazer piscar os códigos de diagnóstico.

### Ler Códigos de Avaria

1. Localize o conector SCS de 2 pinos, normalmente envolto em fita azul atrás do painel lateral do lado do passageiro ou do porta-luvas.
2. Faça um chunt (ligue em ponte) nos dois pinos usando um clipe ou um fio de serviço.
3. Rode a chave de ignição para la posição ON.
4. Conte as piscadelas da Luz de Verificação do Motor (CEL) no painel de instrumentos:
 - **Flashes longos** (1.0 segundo) indicam o dígito das dezenas.
 - **Flashes curtos** (0.5 segundos) indicam o dígito das unidades.
 - Por exemplo, dois flashes longos seguidos por três flashes curtos indicam o Código 23 (Sensor de Detonação/Knock Sensor).

---

## 3. Honda OBD2 (1996–2001)

A partir de 1996, a EPA dos Estados Unidos impôs o protocolo padronizado OBD2. A Honda redesenhou os seus sistemas de gestão de motor para incorporar um Conector de Ligação de Dados (DLC) de 16 pinos e Códigos de Diagnóstico de Avaria (DTCs) padronizados, tais como `P0420` para a eficiência do catalisador.

### Principais Características

- **Monitorização do Catalisador:** Apresenta um sensor de oxigénio secundário (pós-catalisador) localizado atrás do catalisador para comparar os níveis de oxigénio dos gases de escape com o sensor primário (pré-catalisador).
- **Monitores de Racionalidade e Funcionalidade:** Executa diagnósticos contínuos em tempo de execução, incluindo monitorização de falhas de ignição (misfire - detetando flutuações na velocidade da cambota) e testes de fuga no fluxo de purga do EVAP.
- **Memória Flash:** Deixou de usar EPROMs com socket, limitando os métodos tradicionais de modificação com chip em placas OBD2 de fábrica.

### Subgerações OBD2 da Honda

A Honda dividiu os seus sistemas OBD2 em duas configurações distintas de cablagem e fichas de ECU:
- **OBD2a (1996–1998):** Usado nos primeiros Civic de 6ª geração (EK), modelos Integra a meio do ciclo de produção (DC2) e modelos Accord/Prelude desta época.
- **OBD2b (1999–2001):** Apresenta um layout de fichas de ECU redesenhado e mais compacto. Usado nos modelos Civic mais recentes (incluindo o Civic Si EM1 de 1999–2000), Integras e Preludes mais recentes.

> [!NOTE]
> Como as ECUs OBD2 não podem ser facilmente equipadas com socket ou afinadas com emulador, os entusiastas que realizam swaps de motor ou reprogramam configurações de alto rendimento usam normalmente uma **cablagem de conversão** (adapter harness) para ligar uma ECU OBD1 mais antiga com socket (como uma [P28](/cars/sensors/p28) ou [P30](/cars/sensors/p30)) diretamente à cablagem do chassis OBD2.

---

## 4. Caixa e Tradução da Terminologia

Com a introdução dos padrões OBD2, o protocolo J1930 da Society of Automotive Engineers (SAE) padronizou os nomes dos componentes de controlo do motor. A Honda modificou a sua terminologia tradicional para corresponder a estes padrões:

| Nome Antigo da Honda | Nome Padrão SAE | Descrição |
| :--- | :--- | :--- |
| **Sensor TW** (Temperature of Water) | **Sensor ECT** | Sensor de temperatura do líquido de refrigeração do motor |
| **Sensor TA** (Temperature of Air) | **Sensor IAT** | Sensor de temperatura do ar de admissão |
| **EACV** (Electronic Air Control Valve) | **Válvula IAC** | Válvula de controlo de ar do ralenti |
| **Sensor PA** (Pressure of Air) | **Sensor BARO** | Sensor de pressão barométrica |
| **TPS** (Throttle Position Sensor) | **Sensor TP** | Sensor de posição da borboleta |
| **ECU** (Electronic Control Unit) | **ECM / PCM** | Módulo de controlo do motor / grupo motopropulsor |

---

## 5. Compatibilidade de Conversão OBD

Ao converter um Honda entre gerações de OBD durante um swap de motor ou conversão para reprogramação, tenha em mente as seguintes diferenças de hardware:

- **Distribuidores:** Os distribuidores OBD0, OBD1 e OBD2 usam formatos de fichas e sensores internos diferentes. Cablagens de conversão ou alteração de pinagem de fichas são necessárias ao misturar gerações.
- **Injetores de Combustível:** Os injetores OBD0 são de baixa impedância (exigindo uma caixa de resistências/resistor box), enquanto os injetores OBD1 e OBD2 são de alta impedância (saturados, não exigindo caixa de resistências).
- **Alternadores:** As fichas do alternador diferem entre OBD0 (ficha redonda), OBD1 (ficha redonda) e OBD2 (ficha retangular).
- **Sensors de Posição do Distribuidor:** Garanta que a ECU está configurada para corresponder aos sinais dos sensores do distribuidor (CYP, CKP, TDC) provenientes do bloco do motor. Consulte o [guia do sensor de posição do cilindro](/cars/sensors/cylinder-position-sensor) para diagnósticos detalhados dos sensores.
