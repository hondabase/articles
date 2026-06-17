---
summary: 'Guia de referência de hardware e software para a ECU PR3 DOHC VTEC OBD0 e OBD1 usada nos modelos Integra e Civic equipados com motores B16A.'
applies_to:
  obd: [0, 1]
complexity: intermediate
tags:
  - ecu
  - vtec
  - reference
sources:
  - name: 'pgmfi.org wiki'
    title: PR3
    url: /pgmfi/wiki/library/pr3
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Guia de Referência da ECU Honda PR3

A Unidade de Controlo do Motor (ECU) PR3 é uma unidade de controlo proeminente da Honda equipada em veículos B16A DOHC VTEC entre 1989 e 1993. 

> [!IMPORTANT]
> Existem duas gerações completamente diferentes de ECUs designadas como **PR3** (OBD0 e OBD1). Apresentam carcaças físicas de hardware, microprocessadores e pinagens de ligações inteiramente diferentes, e **não são compatíveis** de forma alguma.

---

## Identificação OBD0 vs. OBD1 PR3

### OBD0 PR3 (1989–1991)

- **Aplicação:** Proveniente de modelos JDM B16A de primeira geração (Civic EF9, CRX EF8, Integra DA6).
- **Hardware:** Apresenta o microcontrolador OKI M66x301 e placa dupla de sensor de detonação (knock sensor). Utiliza a mesma estrutura de código que a [ECU PW0](/cars/sensors/pw0).
- **Jumper de Caixa Automática/Manual:** Verifique o esquema da placa para identificação do jumper de transmissão:
 [Scan de Identificação do Jumper Auto/Manual do OBD0 PR3](OBD0_pr3-auto-manual.jpg)

### OBD1 PR3 (1992–1993)

- **Aplicação:** Proveniente de modelos JDM Integra RSi e XSi de 1992–1993 (segunda geração B16A).
- **Hardware:** Construída na mesma placa-mãe padronizada das ECUs [P28](/cars/sensors/p28) e [P30](/cars/sensors/p30) (normalmente com o número de peça de placa de circuito `02D01720-1500`).
- **Scan do Esquema:** [Scan do Esquema da Placa OBD1 PR3](https://web.archive.org/web/http://pgmfi.org/resources/FAQ/scans/PR3-OBD1.jpg)

---

## Mapa de Endereços da ROM OBD0 PR3

Abaixo encontram-se os desvios (offsets) de endereços hexadecimais no chip EEPROM de 28 pinos para a versão OBD0 da ECU PR3:

| Localização | Bytes | Descrição | Notas |
| :--- | :---: | :--- | :--- |
| **31D8** | 1 | Limitador de Rotação de Came Baixo | Corte de combustível por RPM do motor em came baixo (usa a fórmula de RPM de 8 bits OBD0) |
| **31DE** | 1 | Limitador de Rotação de Came Alto | Corte de combustível por RPM do motor quente/VTEC (usa a fórmula de RPM de 8 bits OBD0) |
| **31E0** | 1 | Recuperação de Rotação de Came Alto | Rotação (RPM) onde o corte de combustível do VTEC recupera |
| **3418** | 1 | Velocidade de Desativação do VTEC | Limiar de velocidade mínima de desativação do VTEC (usa a fórmula VTEC OBD0) |
| **3419** | 1 | Velocidade de Ativação do VTEC | Limiar de velocidade de ativação do VTEC |
| **3BE6** | 255 | Mapa de Ignição de Came Baixo | Mapa de avanço de ignição de came baixo 15x17 (usa a fórmula de Ignição OBD0) |
| **3CE5** | 255 | Mapa de Ignição de Came Alto | Mapa de avanço de ignição VTEC 15x17 (a primeira linha é tipicamente preenchimento vazio) |
| **3DE4** | 255 | Tabela de Combustível de Came Baixo | Mapa de consulta base de combustível 15x17 (usa a fórmula de Combustível OBD0) |
| **3EE3** | 15 | Multiplicadores de Came Baixo | Coeficientes multiplicadores de coluna para o mapa de combustível 1 |
| **3EF2** | 255 | Tabela de Combustível de Came Alto | Mapa de consulta de combustível VTEC 15x17 (usa a fórmula de Combustível OBD0) |
| **3FF1** | 15 | Multiplicadores de Came Alto | Coeficientes multiplicadores de coluna para o mapa de combustível VTEC |

> [!TIP]
> A ECU OBD0 PR3 aplica multiplicadores de coluna aos mapas de combustível para dimensionar os valores brutos de 8 bits das células. Consulte o [guia de Compreensão de Mapas](/cars/fueling/understanding-maps) para obter informações sobre as fórmulas de multiplicador de carga.

---

## Esquemas de Placa de Circuito da ECU

Consulte os seguintes scans de placa de alta resolução para diagnóstico e reparação da PR3:

![JDM PR3 J01 OBD0 ECU top board view](pr3-j01-1.JPG)
*Vista superior dos componentes da placa da ECU JDM PR3 `J01`.*

![JDM PR3 J51 top board view showing microchip locations](pr3-j51top.jpg)
*Vista superior dos componentes da placa da ECU JDM PR3 `J51`.*

![JDM PR3 J51 bottom solder trace view](pr3-j51bottom.jpg)
*Vista das pistas de solda no lado inferior da placa da PR3 `J51`.*
