---
summary: 'Referência técnica sobre as bobinas de ignição internas e externas da Honda PGM-FI, incluindo procedimentos de teste, especificações e conversão de configurações de bobina interna para externa.'
tags: [ignição, hardware, diagnóstico]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Bobina de Ignição'
    url: /pgmfi/wiki/library/ignition-coil
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Bobina de Ignição

A bobina de ignição é um transformador elétrico que eleva a baixa tensão da bateria (12V) para a alta tensão (20.000V a mais de 40.000V) necessária para saltar a folga da vela de ignição e iniciar a combustão nos motores Honda PGM-FI.

## Visão Geral

Na maioria dos veículos Honda das eras OBD0, OBD1 e OBD2a/2b, a bobina de ignição está alojada diretamente dentro da tampa do distribuidor (conhecida como **bobina interna**). Esta disposição compacta integra a bobina, o Módulo de Controlo de Ignição (ICM ou ignitor) e o rotor/tampa do distribuidor numa única unidade.

Embora conveniente para o acondicionamento, as bobinas internas aquecem muito devido aos limites de dissipação de calor dentro do alojamento selado do distribuidor. Sob alta carga do motor, elevadas RPM ou alta sobrealimentação (boost), este calor pode degradar o isolamento dos enrolamentos da bobina, levando a curto-circuitos internos e falhas de ignição.

Alguns modelos (como os OBD1 Accord, Prelude e alguns modelos Civic) utilizavam uma **bobina externa** montada na parede corta-fogo ou no bloco do motor, que funciona a temperaturas mais baixas e é mais fiável.

---

## Especificações

Ao diagnosticar falhas de ignição ou uma condição de "não arranca", verificar a resistência elétrica dos enrolamentos primário e secundário é o primeiro passo de diagnóstico. Abaixo estão as especificações originais (OEM) para as bobinas de ignição Honda/TEC mais comuns (medidas a 20°C / 68°F).

### Especificações da Bobina Interna (ex. TEC TC-08A / TC-05A)

* **Resistência do Enrolamento Primário:** `0,63 – 0,77 ohms` (medida entre os parafusos do terminal positivo (+) e negativo (-)).

* **Resistência do Enrolamento Secundário:** `12,8 – 19,2 k-ohms` (medida entre o terminal de parafuso positivo (+) e a torre de saída de alta tensão).

### Especificações da Bobina Externa (ex. TEC TC-07A)

* **Resistência do Enrolamento Primário:** `0,4 – 0,6 ohms`.

* **Resistência do Enrolamento Secundário:** `12,0 – 18,0 k-ohms`.

---

## Procedimento de Teste

Para verificar se a sua bobina de ignição falhou, utilize um multímetro digital (DVOM) para medir a resistência dos enrolamentos internos.

### Passos para Testar:

1. **Segurança Primeiro:** Certifique-se de que a ignição está desligada (OFF). Desligue o terminal negativo da bateria.
2. **Aceder à Bobina:** Remova a tampa do distribuidor e a cobertura de proteção (proteção contra poeiras) para expor a bobina de ignição.
3. **Identificar os Terminais:** Note a localização do parafuso do terminal positivo (+) (geralmente tem um fio preto/amarelo) e do parafuso do terminal negativo (-) (geralmente tem um fio azul). Desligue os fios dos terminais para evitar retorno de corrente.
4. **Testar o Enrolamento Primário:**
 * Defina o seu multímetro para a gama de resistência mais baixa (ex. 200 ohms).
 

* Toque com uma ponta de prova no terminal positivo (+) e com a outra no terminal negativo (-).
 * Subtraia a resistência das pontas de prova do seu multímetro (tocando com as pontas de prova uma na outra) da leitura obtida.
 

* O resultado deve estar entre **0,6 – 0,8 ohms** para uma bobina interna. Se ler `0` (curto-circuito) ou `OL` (circuito aberto), a bobina está defeituosa.
5. **Testar o Enrolamento Secundário:**
 * Defina o seu multímetro para a gama de kilohms (ex. 20k ou 200k ohms).
 

* Toque com uma ponta de prova no terminal positivo (+) e com a outra ponta de prova na torre de saída de alta tensão (onde o contacto de mola encontra a tampa do distribuidor).
 * O resultado deve estar entre **12,8k – 19,2k ohms**. Um circuito aberto (`OL`) indica um enrolamento partido no interior da carcaça da bobina.

---

## Conversão de Bobina Interna para Externa

Converter o seu distribuidor de uma bobina interna para uma bobina externa (como uma MSD Blaster SS ou uma bobina externa original/OEM) aumenta a energia da faísca e isola a bobina do calor do distribuidor. Esta modificação é altamente recomendada para projetos turbocomprimidos ou de altas RPM.

### Requisitos:

* Uma bobina de ignição externa (ex. MSD-8207 ou Honda TC-07A).

* Uma tampa de distribuidor para bobina externa (possui uma tomada para cabo externo em vez de um contacto de tampa sólido).
* Cabo de vela de ignição de alta secção (para ligar a tampa à bobina externa).

* Conectores elétricos, manga termoretrátil e solda.

### Esquema de Cablagem e Ligações:

Dentro do distribuidor, deve encaminhar os fios que originalmente iam para a bobina interna para a nova bobina externa.

| Fio Original dentro do Distribuidor | Função | Ligação à Bobina Externa |
| :--- | :--- | :--- |
| **Preto/Amarelo** | Alimentação +12V Comutada | Terminal Positivo (+) da Bobina Externa |
| **Azul** | Sinal de Controlo de Ignição (do ICM/Ignitor) | Terminal Negativo (-) da Bobina Externa |

### Procedimento:

1. **Remover a Bobina Interna:** Remova a tampa do distribuidor, o rotor e a proteção interna contra poeiras. Desaparafuse e remova a bobina interna de fábrica.
2. **Modificar o Alojamento:** Faça um pequeno furo na parte inferior do alojamento do distribuidor. Insira um passa-fios de borracha para proteger os fios contra o desgaste.
3. **Passar os Fios de Saída:** Solde extensões ao fio Preto/Amarelo interno (alimentação +12V) e ao fio Azul (sinal de acionamento do ICM). Passe estes fios para fora através do passa-fios.
4. **Instalar a Tampa Externa:** Instale a tampa do distribuidor de estilo externo modificada e o rotor.
5. **Montar a Bobina Externa:** Fixe a nova bobina na parede corta-fogo ou no bloco do motor, longe do calor direto dos coletores de escape (headers).
6. **Ligar os Fios:** Ligue o fio Preto/Amarelo ao terminal positivo (+) da bobina externa, e o fio Azul ao terminal negativo (-).
7. **Ligar a Saída Secundária:** Ligue um cabo de vela com comprimento personalizado da torre de alta tensão da bobina externa à torre central da nova tampa do distribuidor.
8. **Teste de Funcionamento:** Ligue o motor e verifique se o ralenti está estável. Verifique o alinhamento do ponto de ignição com uma pistola de ponto (timing light) se o alojamento do distribuidor tiver sido rodado.

---

## Relacionado

- [Sensor de posição da cambota](/cars/ignition/crankshaft-position-sensor)
- [Sensor de posição do cilindro](/cars/sensors/cylinder-position-sensor)
- [Introdução à reprogramação/chipping de ECU](/cars/rom/introduction-to-ecu-chipping)
