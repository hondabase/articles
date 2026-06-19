---
summary: 'Guia técnico para o uso de estações de dessoldagem profissionais na remoção de chips DIP de múltiplos pinos de placas de ECU de dupla face sem danificar as pistas.'
tags: [hardware, education]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Estação de Dessoldagem'
    url: /pgmfi/wiki/library/desoldering-station
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Guia de Estações de Dessoldagem para Trabalho em ECU

Uma estação de dessoldagem é a ferramenta mais eficaz para dessoldar componentes de múltiplos pinos de placas de circuito complexas. Ao contrário dos sugadores de solda manuais ou da malha de dessoldagem, uma estação de dessoldagem combina um ferro de soldar com ponta oca e temperatura controlada com uma bomba de vácuo elétrica integrada. 

Quando colocada sobre o pino de um componente, a ponta derrete a solda e a bomba de vácuo suga instantaneamente o metal líquido para uma câmara de recolha, deixando o pino e o orifício de passagem (through-hole) completamente desimpedidos.

---

## 1. Por que uma Estação é Crítica para a Modificação de ECUs (Chipping)

As ECUs Honda originais OBD0 e OBD1 utilizam PCBs de dupla face e multicamadas. As pistas dos planos de massa nestas placas são espessas e funcionam como dissipadores de calor, afastando o calor das juntas de solda.

Se tentar dessoldar o chip ROM original de 28 pinos usando um ferro de soldar padrão e uma bomba manual:
* Terá de aplicar calor repetidamente a cada pino individual.

* Os planos de massa da PCB irão dissipar rapidamente o calor, tentando-o a deixar o ferro no local por mais tempo ou a aumentar a temperatura.
* A exposição excessiva ao calor (mais de 4–5 segundos) frequentemente vaporiza o adesivo que une a pista de cobre à placa, fazendo com que ela se "levante".

* É fácil arrancar a manga interna de cobre do orifício (metalização das vias/via-hole plating) ao puxar os pinos do chip, cortando permanentemente a ligação entre o lado superior e inferior da PCB.

Uma estação de dessoldagem derrete a solda dentro de todo o orifício de passagem e evacua-a num único segundo, minimizando o stress térmico e protegendo as delicadas pistas da placa.

---

## 2. Operação e Técnica

Para obter os melhores resultados ao dessoldar componentes da ECU:

1. **Prepare a Junta:** Aplique flux de resina fresco ou do tipo "no-clean" em todos os 28 pinos. Adicionar uma pequena quantidade de solda nova com chumbo ajuda a transferir o calor para a junta de solda antiga.
2. **Defina a Temperatura:** Ajuste a estação entre **350°C e 380°C** (660°F a 715°F). Os pontos de massa espessos podem exigir um pouco mais de calor, mas não exceda os 390°C.
3. **Posicione a Ponta:** Encaixe a ponta oca completamente sobre o pino do componente, fazendo um contacto plano com a pista da PCB.
4. **Rode e Sugue:** Aguarde 1–2 segundos para que a solda derreta. Mova suavemente a ponta num pequeno movimento circular para garantir que o pino se move livremente dentro do orifício (indicando que toda a solda está derretida) e, em seguida, pressione o gatilho de vácuo.
5. **Limpe a Ponta:** Mantenha o vácuo a funcionar durante um segundo após levantar o ferro para garantir que toda a solda derretida é puxada para o reservatório do filtro e não solidifica dentro do bocal.

---

## 3. Recomendações de Marcas

* **Hakko:** A Hakko **FR-301** (pistola portátil) e a **FM-203** (estação de bancada) são os padrões da indústria para reprogramação e eletrónica automóvel. Apresentam excelente recuperação térmica e bocais de substituição amplamente disponíveis.

* **Pace / Metcal:** Equipamento profissional de nível industrial. Muito caro, mas oferece uma estabilidade de temperatura incomparável.

* **Weller:** Estações de bancada altamente fiáveis (linhas profissionais), embora as pontas de substituição possam ser caras.

* **Xytronic:** Excelentes opções de valor de gama média para entusiastas que dessoldam ocasionalmente.
