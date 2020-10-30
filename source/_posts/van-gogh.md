---
title: Vicent van Gogh
categories:
- [replicadores]
---

![Vincent van Gogh - Noite Estrelada, 1889](/resources/images/van_gogh/van-gogh-noite-estrelada-d.jpg)

**Vincent van Gogh** (1853-1890) foi um pintor holandês que durante sua vida produziu mais de 2000 obras. Considerado como um dos maiores expoentes da pintura pos-impressionista. Gostava de pintar ao ar livre e boa parte de suas obras foram pintadas nos seus últimos anos de vida. Tinha uma personalidade peculiar e sofria de problemas psiquiátricos chegando a se internar numa clínica onde pintou _A noite estrelada_ um de seus quadros mais famosos. Apesar do reconhecimento que recebe nos dias de hoje durante a vida vendeu apenas uma de suas obras.[[1]](https://www.ebiografia.com/van_gogh/)[[2]](https://brasilescola.uol.com.br/biografia/vincent-van-gogh.htm)


<!-- more -->

## Primeiros passos
O Van Gogh produziu diversas obras durante sua vida dentre estas obras a sua pincelada se tornou algo inconfundível para poder recriar qualquer obra do artista seria importante tentar reproduzir este estilo de pincelada. Foi escolhida a obra _A noite estrelada_ e então tentou-se recriar as pinceladas do autor de maneira a reproduzir a noite estrelada.

## Especificação

### Cores

Para realizar a reprodução da _A noite estrelada_ foi necessário definir as cores para reprodução, foram utilizadas 3 cores bases para a composição **_azul_**, **_amarelo_** e **_branco_**.

### Classes 
Diferente de outros exemplos já demonstradas para a reprodução da composição do Van Gogh foi utilizado o conceito de classes de objetos. As duas principais classes são **_estrela_** e **_igreja_**.

#### Estrelas
Uma classe utilizada para definir as estrelas que aparecem no céu do quadro que contém três atribuitos dois para sua localização na composição e o terceiro para o seu tamanho.

#### Igreja
Classe utilizada para fazer a reprodução da torre que recebe destaque na obra de Van Gogh, durante a especificação foi nomeado como igreja, mas pode ser considerada como uma árvore ou arbusto.

### Composição
A composição foi separada em duas partes: **_céu_** e **_chão_** sendo estas utilizadas para a coloração adequada das partes e também para distribuição adequada de elementos que compõe a obra original.

## O Algoritmo
O algoritmo para desenvolver esta reprodução tem um conceito muito simples, esta baseado na rotação de linhas ou semicírculos que combinados geram um efeito próximo as pinceladas do pintor.

### Implementação
A implementação foi divida em três etapas:

- **Etapa 1**:
    Definição de traços de pinceladas do Van Gogh - foi criado um algoritmo que renderiza diversas linhas em diferentes rotações por todo o espaço disponível da composição. Ao encontrar um resultado satisfátorio de quantidade de interaçãoes e grossura destas linhas foi finalizada esta etapa;
- **Etapa 2**:
    Separação do espaço de composição - Nesta etapa foi construída as diferenças da composição, separando a etapa anterior em dois diferentes tipos. Iniciando com a renderização das pinceladas equivalentes ao **_céu_** e em sequência as que seriam correspondentes ao **_chão_**. Foi dividido o _canva_ de 800x800 em duas partes sendo que a correspondente ao céu ocupada 75% da composição e o chão os outros 25% restantes;    
- **Etapa 3**:
    Adicionando itens da composição: Nesta etapa foram adicionas os outros itens importantes para a composição. Ao fazer a configuração para execução são configuradas a localização e a quantidade de estrelas a serem inseridas na composição. Durante a criação da composição no momento de renderização do céu verifica-se se naquela posição (combinação de coordenadas) existe uma estrela, caso exista, será mudada a cor para a cor de uma estrela - o tom amarelo - finalizando assim a etapa de criação base da composição. Ao final do processo é adicionado a igreja que sobrepõe todos os outros itens da composição.

##### Código

|                                                                     |                                                                     |
|---------------------------------------------------------------------|---------------------------------------------------------------------|
| ![Criação da composição](/resources/images/van_gogh/composicao.png) | ![Criação de auxiliares](/resources/images/van_gogh/auxiliares.png) |

## Resultados

![1](/resources/images/van_gogh/van_gogh.gif)
![2](/resources/images/van_gogh/van2.png)