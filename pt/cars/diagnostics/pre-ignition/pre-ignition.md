---
summary: 'Explica os mecanismos físicos, diferenças, causas e métodos de prevenção para a pré-ignição e detonação do motor (knock).'
tags: [tuning, diagnostics]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: Pré-Ignição
    url: /pgmfi/wiki/library/pre-ignition
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Pré-Ignição e Detonação (Engine Knock)

Compreender a instabilidade de combustão é um dos aspetos mais críticos na afinação de motores (tuning). Embora termos como "pré-ignição", "detonação" e "knocking" sejam frequentemente usados de forma intercambiável para descrever a batida de pinos, eles referem-se a fenómenos físicos diferentes. Ambos, no entanto, podem destruir rapidamente um motor sob carga.

---

## 1. Diferenciar Pré-Ignição vs. Detonação

### Detonação (Knock)

A detonação ocorre **depois** de a vela de ignição disparar. 

À medida que a vela incendeia a mistura ar-combustível, uma frente de chama expande-se para o exterior, comprimindo e aquecendo a restante mistura ar-combustível não queimada (o "end-gas") no cilindro. Se a temperatura e a pressão excederem o limiar de autoignição do combustível, o "end-gas" entra em combustão espontânea numa explosão rápida e descontrolada. Isto cria ondas de choque de alta velocidade que embatem contra o pistão e as paredes do cilindro, produzindo o característico som metálico de "grilar".

### Pré-Ignição

A pré-ignição ocorre **antes** de a vela de ignição disparar.

Isto acontece quando um ponto quente dentro da câmara de combustão — como um depósito de carvão incandescente, um elétrodo de vela sobreaquecido ou uma aresta afiada numa válvula — incendeia prematuramente a mistura ar-combustível. Dado que o pistão ainda está a subir, comprimindo a mistura que já se encontra a queimar, as pressões e temperaturas no cilindro sobem para níveis extremos. A pré-ignição é silenciosa e pode derreter um pistão em segundos.

---

## 2. Causas Comuns de Instabilidade de Combustão

As anomalias de combustão são geralmente causadas por uma combinação de altas temperaturas no cilindro, pressão excessiva ou estabilidade insuficiente do combustível (octanas):

* **Mistura Ar-Combustível Pobre (AFR):** Misturas pobres queimam a temperaturas mais elevadas. Sob pressão (boost) ou carga pesada, uma AFR pobre eleva as temperaturas do cilindro para além do limiar de detonação.

* **Avanço de Ignição Excessivo:** O disparo demasiado cedo aumenta o pico de pressão no cilindro antes de o pistão atingir o Ponto Morto Superior (PMS/TDC), propiciando a detonação.

* **Alta Taxa de Compressão:** Taxas de compressão mais elevadas aumentam naturalmente a pressão e a temperatura no cilindro durante o curso de compressão.

* **Octanagem Insuficiente:** O combustível de baixa octanagem tem menor resistência à autoignição sob calor e pressão.

* **Temperatura do Ar de Admissão Excessiva (IAT):** O ar de admissão quente (frequentemente devido a acumulação de calor/heat soak ou a um intercooler ineficiente em configurações turbo) eleva a temperatura base de combustão.

---

## 3. Mitigação e Prevenção

* **Atrasar o Ponto (Pulling Timing):** As ECUs Honda de fábrica utilizam uma [placa de knock](/cars/sensors/knock-board) para detetar a frequência específica da detonação. Se for detetado knock, a ECU atrasa temporariamente o ponto de ignição para reduzir o pico de pressão no cilindro.

* **Misturas Ar-Combustível Ricas:** Sob pressão de turbo, utilizar uma AFR rica (por exemplo, 11.5:1 com gasolina de bomba) arrefece a câmara de combustão, uma vez que o excesso de combustível absorve o calor durante a vaporização.

* **Escalonamento por Octanagem:** Ajuste o seu ponto de ignição pretendido à octanagem do combustível. Utilizar mapas de ponto agressivos exige combustível premium de alta octanagem (gasolina de 98 octanas, E85 ou gasolina de corrida) para suprimir a detonação.
