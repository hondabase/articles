---
summary: 'Referência técnica e guia de localização para os Conectores de Ligação de Dados (DLC) Honda de 3 pinos e OBD2 de 16 pinos.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - diagnostics
  - wiring
  - serial
sources:
  - name: 'pgmfi.org wiki'
    title: DLC
    url: /pgmfi/wiki/library/dlc
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Referência do Conector de Ligação de Dados (DLC) Honda

O **Conector de Ligação de Dados (DLC - Data Link Connector)** é a porta de interface de diagnóstico usada para comunicar com as Unidades de Controlo do Motor (ECU) da Honda. Dependendo do ano do modelo do veículo e da geração do diagnóstico a bordo (OBD), a Honda utiliza um conector proprietário antigo de 3 pinos ou o conector padronizado SAE J1962 de 16 pinos.

---

## Conector de Ligação de Dados Proprietário de 3 Pinos (OBD0 / OBD1)

Nos veículos OBD0 e OBD1 (aproximadamente de 1988–1995), a Honda utilizou uma porta **DLC de 3 pinos** proprietária para transmitir dados de diagnóstico por linha K série. 

* **Configuração de 2 Fios vs. 3 Fios**: Dependendo do modelo e nível de equipamento específicos, este conector pode estar preenchido com dois ou três fios:
 * **Modelos de 3 Fios**: Fornecem uma linha de alimentação constante de +12V, Terra e uma linha de Dados Série. Isto permite que os scanners de diagnóstico (como o Vetronix Mastertech de nível de concessionário) se alimentem diretamente a partir da porta.
 * **Modelos de 2 Fios**: Apenas contêm as linhas de Terra e Dados Série. Ao utilizar uma ferramenta de diagnóstico nestes modelos, o scanner deve ser ligado a uma fonte de alimentação externa de 12V (como a tomada do isqueiro ou pinças de bateria).
* **Conector de Verificação de Serviço (SCS)**: O DLC de 3 pinos está sempre localizado diretamente adjacente a um **conector azul de 2 pinos** separado. Este é o Conector de Verificação de Serviço (SCS - Service Check Connector) ou porta do Sinal de Verificação de Serviço, que é curto-circuitado com um "shunt" (jumper) ou clipe de papel para ler os códigos de erro intermitentes da luz de verificação do motor (CEL) no painel de instrumentos.

### Localizações do Conector de 3 Pinos

* **Borda Inferior Direita do Painel do Passageiro**:
 * Accord (L4) de 1994–1995
 

* Civic de 1992–1995
 * Civic del Sol de 1993–1995

* **Atrás da Parte Frontal da Consola Central**:
 * Honda Prelude de 1992–1995 *(Nota: Geralmente uma configuração de 2 fios que requer alimentação externa para a ferramenta).*
* **Atrás do Porta-Luvas do Passageiro**:
 * Honda Odyssey de 1995

* **Painel Lateral Esquerdo do Condutor (Kick Panel)**:
 * Honda Passport de 1994–1995.5

### Vistas do Hardware do DLC de 3 Pinos

![Localização do Conector DLC de 3 Pinos (Civic/Accord)](dlc1.jpg)
*Conector DLC azul de 3 pinos proprietário (à direita) e conector SCS azul de 2 pinos (à esquerda) num Civic de 1992–1995.*

![Conjunto de Conectores DLC de 3 Pinos e SCS](dlc2.jpg)
*Grande plano do suporte integrado da porta de diagnóstico.*

---

## Conector de Ligação de Dados Padronizado de 16 Pinos (OBD2)

A partir do Accord V6 em 1995, e como padrão em todos os veículos do mercado norte-americano (USDM) a partir de 1996, a Honda adotou o conector padronizado **OBD2 DLC de 16 pinos** (SAE J1962). 

* **Protocolo de Comunicação**: A Honda utiliza o protocolo **ISO 9141-2** para comunicações OBD2. Os pinos 7 (Linha K) e 15 (Linha L) são utilizados para comunicação.

* **Configuração de Pinos**: Dos 16 pinos, a Honda preenche até 7 pinos para diagnósticos padrão de emissões. Os restantes pinos são usados para sistemas proprietários da Honda (ABS, SRS, etc.).

### Localizações do OBD2 DLC de 16 Pinos

Como a norma OBD2 padronizou o conector mas não a sua localização exata no habitáculo, a Honda utilizou várias localizações dependendo da arquitetura do chassis:

````carousel
![Borda Inferior Esquerda do Painel de Instrumentos (Apontando para Baixo)](dlc3.jpg)
<!-- slide -->
![Atrás do Cinzeiro da Consola Central](dlc4.jpg)
<!-- slide -->
![Atrás da Tampa de Acesso Frontal da Consola Central](dlc5.jpg)
<!-- slide -->
![Atrás da Consola Central - Sem Tampa](dlc6.jpg)
<!-- slide -->
![Atrás do Porta-Copos da Consola Central](dlc7.jpg)
````

### Guia de Localização por Modelo

* **Sob o Painel de Instrumentos do Lado do Condutor (Apontando para Baixo)**:
 * Accord de 1998–2002
 

* Civic de 1996–2000
 * Passport de 1996–1997

* **Atrás do Cinzeiro da Consola Central**:
 * Accord V6 de 1995–1997
 

* Accord L4 de 1996–1997
* **Atrás da Tampa de Acesso da Consola Central**:
 * Odyssey de 1996–1997

* **Atrás do Acabamento Frontal da Consola Central**:
 * Civic del Sol de 1996–1997
 

* CR-V de 1997–2001
* **Atrás do Painel de Acabamento Removível da Consola Central**:
 * Prelude de 1997–2001
