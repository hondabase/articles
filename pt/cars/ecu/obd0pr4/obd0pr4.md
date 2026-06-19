---
summary: 'Visão geral técnica das variações de hardware, sensores barométricos e configurações de E/S exclusivas da ECU PR4 OBD0 do Acura Integra.'
tags: [ecu, reference]
applies_to:
  brand: Acura
  ecus: [PR4]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: OBD0PR4
    url: /pgmfi/wiki/library/obd0pr4
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Visão Geral da ECU PR4 OBD0 do Acura Integra

A ECU PR4 OBD0 é a unidade de controlo do motor de fábrica para o Acura Integra de 1990–1991 (equipado com o motor 1.8L DOHC B18A1). Embora a PR4 partilhe a arquitetura geral com outras ECUs OBD0 de injeção multiponto (MPFI) da sua época (como a PM6), apresenta várias configurações de hardware exclusivas e particularidades no manuseamento de sensores.

---

## 1. Sensores Barométricos / Pressão Atmosférica (PA)

O layout da placa da PR4 suporta duas configurações distintas de sensores barométricos, que correspondem geralmente à divisão entre os anos de modelo 1990 e 1991:

* **Sensor PA Interno:** Algumas revisões montam o sensor de pressão barométrica/atmosférica diretamente na própria placa de circuito da ECU.

* **Sensor PA Externo:** Outras revisões são configuradas através de jumpers para ler a partir de um sensor PA externo montado na zona dos pés (kick panel) do veículo ou na parede de fogo (firewall) do compartimento do motor. 

---

## 2. Reatribuição de Pinos e Particularidades de E/S

A PR4 encaminha vários pinos de cablagem padrão de forma diferente em comparação com a PM6 do Civic/CRX:

### Compensação de Ralenti da Direção Assistida (Pino ELD)

No Civic PM6, o pino **`B14`** é dedicado ao sensor Electrical Load Detector (ELD). Na Integra PR4, este mesmo pino de entrada é reatribuído para monitorizar o interruptor de pressão da direção assistida. Quando a bomba da direção assistida coloca carga no motor ao ralenti (como durante manobras de estacionamento apertadas), o interruptor é acionado, dizendo à ECU para aumentar ligeiramente a velocidade de ralenti para evitar que o motor vá abaixo ou falhe.

### Integração Externa de Controlo de A/C

Na maioria dos modelos padrão da Honda, a ECU aciona diretamente o relé da embraiagem do A/C. O Integra OBD0, no entanto, utiliza um módulo de controlo de A/C montado externamente (localizado atrás do porta-luvas). A ECU PR4 faz interface com este módulo para compensação de ralenti, em vez de controlar o relé da embraiagem diretamente.

### Termopar de Temperatura do Óleo

Os blocos de motor B18A1 possuem um interruptor/termopar de temperatura do óleo de fábrica. Este sensor é encaminhado para o módulo externo de controlo do A/C e da ventoinha do radiador (que rege o funcionamento da ventoinha com base nas temperaturas ambiente, do líquido de refrigeração e do óleo), em vez de ser processado diretamente pelos mapas de combustível ou ignição da ECU.
