---
summary: 'Remover a deteção de detonação é simples: Voltar a soldar R118 e R119 em R142, 143. Em seguida, remover R101 (opcional).'
tags: [hardware, education, ecu, tuning, rom, sensors, reference]
applies_to:
  brand: Honda
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Remove A Knock Sensor'
    url: /pgmfi/wiki/library/remove-a-knock-sensor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Remover um Sensor de Detonação

Remover a deteção de detonação (knock detection) é simples: Solde novamente `R118` e `R119` em `R142` e `R143`. Em seguida, remova `R101` (opcional). Por fim, remova a própria placa de detonação (knock board).

- no_knock.jpg: 
 ![no_knock.jpg](no_knock.jpg)

Aqui está o aspeto de uma P14 sem detonação (knockless): [Clique Aqui!](/pgmfi/wiki/media/library/P14/euro_p14_manual_board_no_ks_356.jpg) **Publicado originalmente por prelude-driver** aqui está como funciona: `R101` é um limitador de corrente para o sinal no KS (knock sensor), é necessário com o KS mas pode deixá-lo porque não vai para mais lado nenhum. `R118`/119 são limitadores de corrente nos sinais de clock e dados para o KS; se remover o KS, deve removê-los por causa das resistências seguintes. `R142`/143 são resistências de pullup para as linhas de clock e dados, não se utilizam se tiver um KS porque existem pullups no próprio KS, mas se o KS for removido, deve instalá-las para evitar que as linhas fiquem flutuantes (floating). São de 10k, já agora.
