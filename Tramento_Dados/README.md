<h1 align ="center">Resumo do Tratamento de Dados</h1>

Realizei o tratamento de dados utilizando majoritariamente a biblioteca pandas. Realizei a leitura e obtive informações básicas quanto a tipo de dados, classificação quanto a dados qualitativas e quantitativos. Fiz o tratamento dos valores faltantes criando colunas informativas quanto a ausência ou presença dos dados e alterei valores faltantes seguindo padrões diferentes para cada feature. Retirei duplicatas, alterei nomes de valores nas features, então observei valores Outliers e salvei os dados para utilização na análise exploratória e criação do modelo de classificação.

<h1 align ="center">Discussão dos Resultados</h1>

O tratamento de dados foi um processo de buscar inconsitências e preparar os dados para utilizar na análise exploratória e criação do modelo de classificação.

<h2 align= "Left"> 1 . Leitura e obtenção de informação</h2>

Utilizando biblioteca *Pandas* li os dados em formado json, e utilizei método *info* para obter informações básicas como: tipo de dados, valores faltantes, análise univariadas para saber como estão os dados. 

<h2 align= "Left"> 2 . Valores Faltantes</h2>

Para solucionar o problema de dados faltantes foram feitos os seguintes passos: 
1. Criei uma coluna extra que informa se o dado de determinada feature era faltante ou não.
2. Alterei o valor faltante de features quantitativas para o valor da mediana, pois assim não seria afetado por distribuição não normal.
3. Alterei o valor faltante da features qualitativa "entrega de documento 2" para 0, informando que não houve entrega de documento.
4. Exclui o valor faltante da feature qualitativa "país", pois eram menos de 1% dos dados.
   
<h2 align= "Left"> 3 . Retirar duplicatas e renomear valores</h2>

Após retirar valores duplicados com pandas, renomeei valores da feature "entrega de documento 2" de Y e N para 1 e 0, assim informando numéricamento a ausência ou presença do documento.

<h2 align= "Left"> 4 . Observar Outliers e Salvar dados</h2>

Fiz uma observação dos outliers no DataFrame. Todas as features apresentavam outliers e não se mostraram dados errados, por este motivos os mantive nos DataFrame para não perder informação importante de fraude. 
Contei a quantidade de valores únicos nas features produto e categorias de produto, para obter informação quanto a cardinalidade. 
Salvei os dados tratados para uso na análise exploratória e criação do modelo de classificação.






