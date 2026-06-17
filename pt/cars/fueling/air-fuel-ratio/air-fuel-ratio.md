---
summary: 'Uma introdução à relação ar-combustível (AFR) em motores de combustão interna, explicando alvos estequiométricos, misturas ricas vs. pobres e escalas de sensores.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - combustível
  - tuning
  - sensor
sources:
  - name: 'pgmfi.org wiki'
    title: 'Relação Ar-Combustível'
    url: /pgmfi/wiki/library/air-fuel-ratio
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Guia de Relação Ar-Combustível (AFR) para Tuning Honda

A Relação Ar-Combustível (AFR - Air-Fuel Ratio) é a proporção em massa de ar para combustível presente na câmara de combustão de um motor. É uma das variáveis mais críticas na gestão do motor, ditando diretamente a segurança da combustão, a eficiência térmica, as emissões de escape e a potência de saída.

Compreender como calibrar os mapas de combustível para atingir valores específicos de AFR é a base da reprogramação (tuning) personalizada de ECUs Honda.

---

## 1. Estequiometria, Misturas Ricas e Pobres

O comportamento da mistura ar-combustível é classificado em relação ao seu ponto estequiométrico:

- **Relação Estequiométrica (14,7:1 para gasolina):** A relação quimicamente ideal onde todo o oxigénio e combustível são completamente consumidos durante a combustão. Este é o alvo para cruzeiro e ralenti, permitindo que o catalisador limpe os gases de escape com a máxima eficiência.
- **Mistura Rica (AFR < 14,7):** Contém excesso de combustível. As misturas ricas ardem a temperaturas mais baixas e mais lentamente, agindo como um agente de arrefecimento químico para os pistões e válvulas. A potência máxima em motores a gasolina naturalmente aspirados é tipicamente alcançada num intervalo ligeiramente rico entre **12,8:1 e 13,2:1**.
- **Mistura Pobre (AFR > 14,7):** Contém excesso de ar. As misturas pobres ardem a temperaturas mais elevadas e mais rapidamente. As faixas de cruzeiro podem, por vezes, funcionar de forma ligeiramente pobre (até 15,2:1) para maximizar a economia de combustível, mas funcionar com mistura pobre sob carga pesada causará rapidamente detonação (knock/grilar) e derreterá pistões ou válvulas de escape.

---

## 2. Guia de AFR Alvo por Zona de Carga

Ao calibrar os mapas de consulta de combustível, aponte para estes valores alvo de AFR, dependendo da carga do motor (pressão do coletor) e RPM:

| Tipo de Motor / Zona de Carga | Pressão do Coletor | Intervalo de AFR Alvo | Objetivo de Calibração |
| :--- | :--- | :---: | :--- |
| **Ralenti e Cruzeiro Ligeiro** | Vácuo Alto (colunas 1-5) | **14,7:1** | Economia de combustível em closed-loop e baixas emissões |
| **Atmosférico WOT (Acelerador a Fundo)** | Atmosférica / 0 psi | **12,8:1 - 13,2:1** | Entrega de binário e potência máxima |
| **Indução Forçada (Baixa Pressão)** | 0 a 5 psi | **12,0:1 - 12,5:1** | Transição segura para carga sob pressão |
| **Indução Forçada (Média Pressão)** | 5 a 10 psi | **11,5:1 - 12,0:1** | Arrefecimento do ar de admissão e prevenção de detonação |
| **Indução Forçada (Alta Pressão)** | > 10 psi | **11,0:1 - 11,5:1** | Margem máxima de segurança de combustão |

---

## 3. Coordenar o Enriquecimento de Combustível com o Atraso de Ignição (Step-Retard)

À medida que a pressão no coletor sobe num motor turbocomprimido ou sobrealimentado (supercharged), as pressões e temperaturas nos cilindros sobem exponencialmente. Para manter o motor seguro, o afinador (tuner) deve coordenar o enriquecimento de combustível com o atraso do ponto de ignição:

### Arrefecimento da Carga de Admissão

Baixar o AFR alvo de 12,5 para 11,0 à medida que a pressão de sobrealimentação (boost) sobe injeta combustível em excesso no cilindro. Este combustível líquido não queimado vaporiza-se na câmara, absorvendo calor e baixando as temperaturas da carga de admissão, o que suprime a detonação.

### Velocidade de Combustão

Misturas mais ricas ardem mais lentamente. Para evitar que a pressão máxima ocorra demasiado tarde, ou para prevenir a pré-ignição, o ponto de ignição deve ser atrasado numa curva progressiva (um "step-retard") correspondente à curva de enriquecimento de combustível. For example, atrasar a ignição em 0,5° por cada psi de boost abaixo de 5 psi, e aumentar para 1,0° por cada psi de boost acima de 10 psi, garante que a faísca seja disparada no ângulo de cambota ideal para segurança.

Consulte o [guia de calibração do ponto de ignição](/cars/ignition/tuning-timing) para obter detalhes sobre o cálculo do avanço total da ignição.

## Artigos Relacionados

- [Introdução ao Tuning de ECU](/cars/fueling/ecu-tuning)
- [Como Calibrar o Ponto de Ignição](/cars/ignition/tuning-timing)
- [Integrar um Controlador de O2 Wideband](/cars/fueling/wide-band-o2)
