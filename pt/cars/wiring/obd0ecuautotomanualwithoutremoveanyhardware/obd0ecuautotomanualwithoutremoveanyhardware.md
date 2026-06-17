---
summary: 'Truque de hardware para contornar a verificação do solenoide de bloqueio (lock-up) da transmissão automática em ECUs Honda OBD0 usando uma resistência de 220 ohms.'
applies_to:
  obd: [0]
complexity: advanced
tags:
  - ecu
  - rom
  - conversion
sources:
  - name: 'pgmfi.org wiki'
    title: OBD0ECUAUTOTOMANUALWITHOUTREMOVEANYHARDWARE
    url: /pgmfi/wiki/library/obd0ecuautotomanualwithoutremoveanyhardware
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Conversão de ECU OBD0 de Automática para Manual

Ao utilizar uma ECU OBD0 automática (como uma PM6 de um Civic/CRX EX ou LX) num veículo com transmissão manual, a rotina de controlo da transmissão da ECU verifica a presença do solenoide de bloqueio (lock-up) automático. Se este solenoide não for detetado, a ECU ativa a Luz de Verificação do Motor (CEL) correspondente ao **Código 19** (Solenoide de Controlo de Bloqueio da Transmissão Automática).

Embora o método padrão para converter uma ECU envolva dessoldar jumpers internos (como RP1/RP2) ou modificar a placa de circuito, este guia detalha uma modificação simples na cablagem externa desenvolvida pelo membro da comunidade *defensio*. Ao simular a carga do solenoide usando uma resistência na cablagem, pode utilizar uma ECU automática num carro manual sem abrir a caixa da ECU.

---

## O Truque da Resistência de 220 Ohms

Para contornar a verificação do Código 19, deve ligar uma **resistência de 220&Omega;** entre o pino de saída do solenoide de bloqueio da ECU e a massa (terra). Isto simula a resistência elétrica da bobina do solenoide original, satisfazendo o circuito de monitorização de consumo de corrente da ECU.

### Especificação da Cablagem
* **Pino Alvo 1 (Saída)**: Pino **`A8`** (Saída do Solenoide de Bloqueio Automático em ECUs automáticas OBD0).
* **Pino Alvo 2 (Massa/Terra)**: Pino **`A2`** (Massa de Alimentação da ECU).
* **Resistência**: **220&Omega;** (uma resistência de 1/4 Watt ou 1/2 Watt é suficiente).

### Passos para Modificação da Cablagem

1. Localize os fios correspondentes aos Pinos **`A2`** (Massa) e **`A8`** (Solenoide de Bloqueio) nas fichas da sua cablagem OBD0.
2. Descarne uma pequena secção de isolamento de ambos os fios perto do conector.
3. Solde uma resistência de 220&Omega; em linha entre os dois fios, ligando-os em ponte.
4. Isole as juntas de soldadura expostas usando fita isoladora ou manga termorretrátil para evitar curto-circuitos.

---

## Demonstração Passo a Passo da Montagem (Guia Visual)

```carousel
![Expor o Pino A2 na Ficha da Cablagem](DSCF1531.JPG)
<!-- slide -->
![Pino A8 Unido e Soldado](DSCF1533.JPG)
<!-- slide -->
![Ligação Soldada com uma Resistência de 220 Ohms](DSCF1534.JPG)
<!-- slide -->
![Adicionar um Interruptor de Seleção de Modo](DSCF1535.JPG)
<!-- slide -->
![Juntas de Soldadura Protegidas com Manga Termorretrátil e Agrupadas](DSCF1536.JPG)
<!-- slide -->
![Vista traseira das fichas da cablagem concluídas](DSCF1537.JPG)
<!-- slide -->
![Perfil lateral mostrando o isolamento limpo da cablagem](DSCF1538.JPG)
<!-- slide -->
![Cablagem concluída pronta para ligar à ECU](DSCF1539.JPG)
```

---

## Aplicação Avançada: Reutilização do Solenoide VTEC em OBD0

Este truque de cablagem é muito popular para **conversões VTEC OBD0** (como utilizar um motor JDM B16A com uma ECU USDM PM6 automática). 

Nas ECUs VTEC OBD0 JDM (como a PW0 ou PR3), o Pino **`A8`** é o pino de controlo nativo para o Solenoide VTEC. Como as ECUs USDM PM6 automáticas também utilizam o Pino `A8` para acionar o solenoide de bloqueio automático, pode gravar software VTEC JDM numa ECU automática USDM com chip (reprogramada), e o Pino `A8` funcionará perfeitamente como a saída do solenoide VTEC.

### Utilizar um Interruptor de Seleção de Modo
Ao ligar um interruptor unipolar de duas vias (SPDT) entre o Pino `A8` da ECU, a resistência de 220&Omega; (ligada à Massa/Terra) e o fio do solenoide VTEC do motor, pode criar uma cablagem comutável:
* **Modo Manual / VTEC**: Liga o Pino `A8` diretamente ao Solenoide VTEC.
* **Modo Bypass de Verificação Auto**: Liga o Pino `A8` à resistência de 220&Omega; para contornar o teste de diagnóstico da transmissão automática.
