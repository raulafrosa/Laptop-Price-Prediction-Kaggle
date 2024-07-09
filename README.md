# Quanto custa esse notebook?

</br>
<div align="center">
    <img src="images/notebook.jpg" alt="note">
</div>

## Introdução

Diversos fatores influenciam o preço dos computadores portáteis, incluindo a reputação da marca, os recursos inclusos, a capacidade de memória e a velocidade do processador. 
Marcas renomadas costumam cobrar mais do que suas contrapartes genéricas, principalmente devido ao reconhecimento do nome e à percepção de confiabilidade, em vez de uma superioridade real do produto. 
Os notebooks de marcas conhecidas geralmente vêm com melhores garantias, incentivando os consumidores a pagar pela garantia de suporte pós-compra.

A funcionalidade impacta significativamente os preços dos notebooks, com memória e armazenamento maiores eleva-se os custos devido ao seu desempenho e longevidade aprimorados. 
Além disso, a inclusão de drivers de vídeo e outros dispositivos pode influenciar ainda mais o preço. 
O software pré-instalado também desempenha um papel, especialmente quando envolve publicadores bem conhecidos; no entanto, muitos desses programas podem ser apenas versões de teste, exigindo compras adicionais para funcionalidade completa.

Alguns fabricantes apelam à estética oferecendo notebooks com designs elegantes e em várias cores, atendendo aos consumidores que priorizam a aparência dos seus dispositivos. 
Em última análise, uma combinação desses fatores determina o preço final de um notebook, com cada elemento contribuindo para o valor e o apelo geral do produto.

Para a previsão do preço dos notebooks utilizamos três modelos de Regressão Linear, incluindo Ridge e Lasso, e três de Regressão não Linear, tais como Random Forest, Gradiente e XG Boosting.

Neste projeto, as seguintes etapas são realizadas para regressão e previsão:

<ul>
  <li>Análise Exploratória de Dados</li>
  <li>Regressão linear com Grid search</li>
  <li>Regressão não linear com Grid search</li>
  <li>Feature Selection</li>
  <li>Nova regressão</li>
</ul>

## Análise Exploratória de Dados (EDA)

Utilizamos o conjunto de dados chamado _Laptop Price Prediction using specifications_ do _[Kaggle](https://www.kaggle.com/datasets/jacksondivakarr/laptop-price-prediction-dataset)_. Consiste em 1302 notebooks com 13 atributos. Os diversos atributos incluem:

1)	**Manufacturer**: A empresa fabricante.
2)	**Model Name**: O nome do modelo.
3)	**Category**: Dividida em 6 define a categoria do notenook.
4)	**Screen Size**: Tamanho em polegadas da tela.
5)	**Screen**: Resolução em pixels da tela.
6)	**CPU**: Modelo do processador.
7)	**RAM**: capacidade em GB da memória RAM.
8)	**Storage**: Modelo e tamanho da unidade de armazenagem.
9)	**GPU**: Modelo da placa de vídeo.
10)	**Operating System**: Nome de sistema operacional.
11)	**Operating System Version**: Versão do sistema operacional.
12)	**Weight**: Peso do notebook em Kg.
13)	**Price**: Preço do notebook.

A atributo _Price_ é o único número, todos os outros são categóricos. Para utilizar esses dados eles foram manipulados para assumir valores numéricos. Após essa manipulação o número de atributos aumentou para 26.

A correlação dos atributos com _Price_ mostra quais estão mais relacionados com o alvo

RAM                            0.680511
ssd                            0.656844
CPU                            0.641928
Pixels                         0.527864
Category_Gaming                0.363366
GPU                            0.361630
Category_Ultrabook             0.307240
Operating System_Windows       0.294067
Ips                            0.279304
Category_Workstation           0.206992
Touchscreen                    0.191583
Weight                         0.151697
Manufacturer                   0.139306
Operating System_Mac OS        0.093617
Category_2 in 1 Convertible    0.090014
Screen Size                    0.038563
hybrid                         0.022731
flash                         -0.050915
Operating System_Android      -0.052136
hdd                           -0.099978
Category_Netbook              -0.146426
Operating System_Linux        -0.177671
Operating System_Chrome OS    -0.180921
Operating System_No OS        -0.215422
Category_Notebook             -0.565783
