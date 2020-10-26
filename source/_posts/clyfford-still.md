---
title: Clyfford Still
categories:
- [replicadores]
---

![Clyfford Still - 1957-J No. 1 (PH-142), 1957](/resources/images/clyfford/clyfford.jpg)

**Clyfford Still** foi um pintor e uma das principais figuras da primeira geração de expressionistas abstratos. Ele é mais conhecido por suas pinturas que lembram fendas ou formas semelhantes a chamas. Inspirado pela paisagem varrida pelo vento da pradaria canadense, ele desenvolveu uma técnica de aplicar camadas grossas de tinta na tela usando uma espátula, criando reflexos irregulares de tons escuros contra áreas mais claras de amarelos, laranjas e vermelhos. “Quero que o espectador esteja sozinho diante das pinturas, e se ele encontrar nelas uma imagem desagradável, desagradável ou maligna, que olhe para o estado de sua própria alma.” [[1]](http://www.artnet.com/artists/clyfford-still)

<!-- more -->

## Primeiros passos

Tentar reproduzir a obra de um pintor que não seguia um padrão específico foi o primeiro desafio encontrado. Por ser um pintor abstrato que fazia combinação de cores e uma técnica específica de pintura sob a tela encontrar um padrão para um algoritmo que seria capaz de reproduzir o que o pintor queria transmitir foi através de experimentação e decisões de proximidade visual com as formas que estavam sendo dispostas sob o _canva_ ou a imagem obtida através da execução do algoritmo.

## Especificações
Para poder reproduzir as obras do pintor foi necessário fazer duas especificações a primeira seria as **cores** que ele costumava usar dentro de suas obras e a segunda seria os **padrões** a se utilizar para obter um resultado próximo ao do pintor.

#### **Cores**
Foram selecionados **oito cores** com base na avaliação de 10 obras do pintor, estas cores podem ser visualizadas na tabela abaixo.

![Tabela de cores](/resources/images/clyfford/tabela-cores.png)

Estas cores são selecionadas em grupos de **três** para a geração de uma _nova_ obra no estilo do pintor. Sempre tenta-se manter a cor **_preta_**, **_branca_** ou **_cinza_**, pois foi observado que estas são as cores base utilizadas nas obras.

##### _Variações nas cores_
Uma obra de arte pintada a mão no estilo do Clyfford Still não possui uma cor sólida, ou seja, é necessário fazer uma variação nas tonalidades base que foram selecionadas. Esta variação acontece com a aplicação de uma variação pequena na composição da cor no formato **RGB**, dada a iteração em que o algoritmo se encontra é aplicad0 um valor sob um dos três valores do **RGB** gerando assim uma nova tonalidade.

#### **Padrões**

Para realizar a composição de uma peça que fosse visualmente semelhante as de Still, optou-se por fazer uso de duas formas base que são dispostas sobre o canva de maneira que a sua sobreposição consecutiva de forma não aleatória gere os reflexos irregulares que são vistos nas obras originais do autor.

As formas escolhidas foram nomeadas de **_spine circle_** e **_wave circle_** respectivamente, a composição é feita primeiramente com **_spine circle_** e acima dele é adicionado o padrão **_wave circle_**. 

![Padrões de formas](/resources/images/clyfford/clyfford-patterns.png)


## O algoritmo
Não somente de decisões estéticas uma obra replicadora é criada, neste contexto para o desenvolvimento de um replicador no estilo do Clyfford Still além das especificações estéticas foi necessário fazer uso de um **Autômato Celular**, o qual é a base para toda lógica de criação das obras geradas.

#### **Autômato Celular**
Os Autômatos Celulares são sistemas evolutivos baseados em regras simples. Os Autômatos Celulares são formados por células "vivas", no qual cada célula possui um estado inicial que impacta posteriormente no estado de seus vizinhos, o estado de cada célula se altera sem nenhuma intervenção somente evoluindo de acordo com as regras definidas e com o estado em que seus vizinhos se encontram.[[2]](http://www.marceloramos.com.br/publicacao/16/automatos-celulares).

##### _Jogo da vida de John Horton Conway_
É um dos mais conhecidos Autômatos Celulares, foi publicado pela primeira vez na década de 1970. O jogo da vida, que não possuí um jogador, possui quatro regras básicas e atráves dessas regras o jogo se recria infinitas vezes. 

Ele inicia com uma configuração básica de células vivas que são geradas de forma aleatória, quando então na próxima iteração do algoritmo as regras genéticas definidas por Conway são aplicadas e assim temos uma nova visão do jogo(tabuleiro). Um exemplo de iterações do jogo da vida pode ser observado na imagem abaixo.

![Exemplo de jogo da vida](/resources/images/clyfford/GameOfLife_Glider_Animation.gif)[[3]](https://pt.wikipedia.org/wiki/Jogo_da_vida#/media/Ficheiro:GameOfLife_Glider_Animation.gif).

##### _Implementação_
Foi desenvolvido uma extensão das regras criadas por Conway no jogo da vida, onde cada célula possui 3 estados e estes estados vão influenciar não só a sua aparição, mas também a aparição dos seus vizinhos.

Cada célula recebe de forma aleatória um valor de 0 a 2 representanto este seu estado inicial sendo que 0 -> é uma célula viva, 1 -> é uma célula que irá morrer e 2-> é uma célula que já está morta. Seguindo esta lógica as regras aplicadas aqui são: 

Células vivas:
- Caso dois do seus vizinhos estejam em estado de pré-morte o seu próximo estado será de pré morte;
- Se os seus vizinhos não estão em estado de pré-morte a célula continua no seu estado atual;

Células em estado de pré morte:
- Morrem na próxima execução;

Células mortas:
- Revivem na próxima execução

Na imagem abaixo pode ser observada o método desenvolvido em Java com Processing para o cálculo dos estados das células deste autômata.

![Cálculo do novo estado da célula](/resources/images/clyfford/calcNextState.png)

Cada um destes estados irá adicionar algumas das formas padrões **_spine circle_** e **_wave circle_** com uma determinada cor previamente selecionada com uma variação de tonalidade, após essa execução obtém-se o resultado final da obra.

##### _Filtros_

Para melhorar e aproximar de uma pintura real após a criação da obra pelo computador são aplicados dois filtros, um filtro de pintura a óleo e um segundo filtro de ruído sob a tela.

![Comparação de imagens sem e com filtro](/resources/images/clyfford/filtros-clyfford.png)

# Resultados

|   |   |   |   |   |
|---|---|---|---|---|
| ![1](/resources/images/clyfford/clyfford1.png)  | ![2](/resources/images/clyfford/clyfford2.png) | | ![3](/resources/images/clyfford/clyfford4.png) | ![4](/resources/images/clyfford/clyfford5.png)  |

|   |   |   |   |   |
|---|---|---|---|---|
| ![5](/resources/images/clyfford/clyfford6.png)  | ![6](/resources/images/clyfford/clyfford7.png) | | ![7](/resources/images/clyfford/clyfford8.png) | ![8](/resources/images/clyfford/clyfford9.png)  |





