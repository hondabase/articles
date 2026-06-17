---
summary: 'Guia para utilizar e modificar ferros de dessoldar de pera económicos para chipping de ECU e remoção de solda em furos passantes (through-hole).'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - hardware
  - education
sources:
  - name: 'pgmfi.org wiki'
    title: 'Desoldering Iron'
    url: /pgmfi/wiki/library/desoldering-iron
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Guia para Ferros de Dessoldar de Pera

Um ferro de dessoldar é uma ferramenta económica que combina uma ponta oca aquecida com um mecanismo de vácuo manual — geralmente uma pera de borracha. Serve como um meio-termo entre usar um ferro de soldar e uma bomba manual separados, e comprar uma estação de dessoldar profissional dispendiosa ([desoldering station](/cars/ecu/desoldering-station)).

---

## 1. Instruções de Funcionamento

Para utilizar um ferro de dessoldar de pera padrão:

1. **Comprimir a Pera:** Aperte a pera de borracha completamente antes de aplicar calor na placa.
2. **Aquecer a Junta:** Coloque a ponta oca aquecida de forma plana sobre o pino do componente. Aguarde 1–2 segundos para que a solda derreta completamente.
3. **Soltar para Sucção:** Solte a pera de borracha para criar sucção por vácuo. Isto suga a solda derretida através da ponta para a câmara de recolha.
4. **Limpar a Ponta:** Aperte a pera sobre uma bandeja resistente ao calor para expelir os resíduos de solda antes de passar para o pino seguinte.

> [!CAUTION]
> Apertar a pera enquanto o ferro está perto da placa é desajeitado. Se a ponta escorregar, pode riscar a máscara da placa ou destruir pistas de cobre. Comprima sempre a pera *antes

* de tocar no pino.

---

## 2. Modificação de Vácuo com Aspirador (DIY)

Utilizar a pera manual pode ser frustrante, pois a sucção é breve e muitas vezes não consegue limpar o furo passante completamente à primeira tentativa. Uma modificação comum entre entusiastas converte o ferro manual numa ferramenta de vácuo contínuo:

1. Remova a pera de borracha do tubo de sucção metálico do ferro.
2. Ligue uma mangueira de silicone flexível de alta temperatura ao tubo metálico do ferro.
3. Ligue a outra extremidade da mangueira a um tubo de aspirador doméstico padrão utilizando fita adesiva e um redutor de borracha.
4. Ligar o aspirador fornece uma sucção contínua e de alto volume. Quando a ponta aquecida derrete a solda, o vácuo limpa instantaneamente todo o furo passante.

### Desvantagens da Modificação com Aspirador:

* **Arrefecimento Rápido da Ponta:** O elevado volume de ar aspirado através da ponta arrefece o elemento de aquecimento rapidamente. Deve utilizar um ferro de maior potência (pelo menos 45W) para evitar que a ponta fique presa (congelada) à placa.

* **Ruído Acústico:** Ter um aspirador doméstico a funcionar durante uma longa sessão de dessoldagem é barulhento.

* **Choque Térmico:** Puxar grandes volumes de ar à temperatura ambiente sobre o pad quente da PCB pode empenar a placa ou levantar os pads se a ponta for mantida no local por demasiado tempo.

---

## 3. Ferramentas Alternativas Económicas

Se uma estação de dessoldar estiver fora do seu orçamento e o ferro de pera for demasiado desajeitado, considere utilizar uma bomba de solda manual de alta qualidade (como a **Engineer SS-02**, que possui uma ponta de silicone flexível que sela contra a junta) em combinação com um ferro de soldar padrão.
