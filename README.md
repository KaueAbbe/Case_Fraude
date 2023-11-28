<h1 align="center"> Bem vinda(o) ao Case de Fraude😊 </h1>

![Badge em Desenvolvimento](https://img.shields.io/static/v1?label=STATUS&message=DESENVOLVIMENTO&color=<COLOR>)

<h1 align ="center"> Objetivo do Case🤔</h1>

Utilizar conhecimentos de ciência de dados para compreender a atual situação de uma empresa quanto a fraude, adquirindo conhecimentos a respeito de classificações de fraude ou não fraude dada por um modelo já existente da empresa, e criar um modelo classificador novo que performe melhor. Para este projeto vou utilizar a linguagem Python e as bibliotecas pertinentes. 


<h1 align ="center"> Compreensão do Negócio</h1>

Fraudes são transações que ameação a empresa, e merecem atenção já que é uma prática que pode levar a empresa a falência por perda de dinheiro e produto. Detectar o comportamento de fraudes não é uma tarefas simples, pois além de levar tempo para coletar os dados de determinada compra ser ou não ser fraude há necessidade precisão de cautela enquanto analisa e avalia dados e modelo de classificação. 

Neste projeto há algumas KPIs importantes: 
1. Taxa de Fraude
2. Taxa de aprovação final
   
Em contexto de métrica de avaliação do modelo tem:
1. Recall
2. Perda de Dinheiro por fraude
3. Ganho de Dinheiro Geral


<h1 align ="center"> Resumos das Etapas</h1>

<h2 align ="left"> Tratamento dos Dados</h2>

Realizei tratamento dos dados. Este processo contou as etapas de leitura dos dados, obtenção de informações básicas do dataset, buscando inconsistênicias como valores duplicados e faltantes. Correções foram feitas nas inconsitências encontradas, criando colunas que informam a existência de valores faltantes para levar para Análise Exploratória e para o Modelo de Classificação.

* Leitura, organização e compreensão dos dados.
* Análise de tipo de dados.
* Procura e correção das inconsistências.
* Criação de Novas colunas que informam se os dados eras faltantes.
* Avaliar e retirar duplicatas.
* Renomear valores de Y e N (Yes e No) para 1 e 0.
* Criação de novo arquivo para uso futuro.

<h2 align ="left"> Análise Exploratória e Explanatória</h2>

Realizei análise estatística descritiva univariadas, além de calcular KPIs importantes que descrevem o atual momento da empresa. Calculei prejuízos, lucros e comportamento do modelo de classificação antigo. Também realizei análise bivariada, separando os dados em grupos de compras fraudulentas e não fraudulentas, realizando nesta etapa estatística inferencial com uso de teste de hipóteses não paramétricos. Com as informações adquiridas realizei curta datavisualization, e utilizei modelos para ajudar a compreender o papel de cada feature com relação a target. Desta informações testei uma regra específica para diminuir a fraude na empresa, a qual criei simulação para verificar a consequência da regra. 

* Análise da variável target, visualização de distribuição
* Análise de dados qualitativos e quantitativos
* Análise bivariada entre grupos da variável target
* Data visualization
* Testes de hipóteses
* Storytelling
* Criação e teste de regra de Bussines
  
<h3 align ="left"> Resultados KPIs atuais e Modelo</h3>

![modelo_antigo](https://github.com/KaueAbbe/Case_Fraude/assets/68445400/e3056402-a123-4fcf-a60d-13f7a735e0e0)


* Taxa de Fraude: 5%
* Aprovação: 62.5%
* Recall: 73.76%
* Valor Aprovado em Fraudes: $110954.23


Vemos no gráfico um problema do modelo atual: sobreposição da distribuição dos scores para os grupos fraude e não fraude. A sobreposição significa que o modelo não está conseguindo diferenciar o comportamento de cada grupo, e assim não realizar classificações separando os dois grupos. Este é um resultado que mudarei, trazendo mais especificidade no momento de classificar.  

<h3 align ="left"> Resultados Regras Duras</h3>

Sem utilizar o machine learning busquei criar regras para otimizar os valores das KPIs, principalmente o aumento do lucro da empresa. 

**A regra criada foi:** Como documento e valor aparecem como importantes então uma regra poderia ser: Se o valor atingido for um desvio padrão acima da média de não fraude, E não aprensentar documento 1 e 3 então barre a compra.

* **Prós:**
  
1. Aumenta o uso de documentações para realizar compras com preços maiores. Precisando ter pelo menos 2 documentos.

2. Faz uso conjunto do preço média de compra com documentações.

3. Usando o desvio padrão para baixo pegamos uma boa parcela de compras fraudadas com preço mais baixo que a média.

* **Contras:**

1. Não fraudadores que queiram fazer compras mais caras precisão apresentar duas documentações, e 50% dos não fraudadores não apresentam o documento 3.

2. Usando o desvio padrão para baixo pegamos uma boa parcela de compras não fraudadas com preço mais alto que a média de não fraude.

Criei uma simulação que realiza o seguinte passo-a-passo: 

1. Pega uma linha no dataset aleatoriamente
2. Verificar se o valor está dentro da área de perigo (Acima da metade da mediana)
3. Se estiver na área de perigo: verificar os documentos - Para verificar os documentos vou apenas olhar a coluna do
4. Calcule o resultado: Se é barrado ou não.
5. Anotar o valor de compra, se foi barrado ou não, e o valor da coluna fraude da linha selecionada.
6. Devolver a linha ao dataset e fazer um Loop do processo.
   
**Resultado:** Apesar de diminuir a taxa de fraude de 5% para 4.8%, houve também diminuição do ganho de dinheiro da empresa. Por este motivo esta regra não poder implementada. 
 
<h2 align ="left"> Criação do Modelo Classificação</h2>



* Pré-Processamento dos Dados
* Sepração dados treino, teste e validação
* Definição de Recall e Métrica de Bussines para avaliação
* Criação de um modelo Dummy e LogisticRegresion como Baseline
* Criação de seis modelos de machine learning
* Otimização por Hiperparâmetros do melhor modelo

  
<h3 align ="left">Modelo Novo</h3>

![modelo_novo](https://github.com/KaueAbbe/Case_Fraude/assets/68445400/d5c14840-16e3-4bfc-954b-34623bc069ec)


<h2 align ="center"> Quais bibliotecas usei durante o Challenge?</h2>

1. Tratamento: Pandas 🐼|
2. Análise Exploratória: Pandas, Numpy, scipy, StatsModels, Plotly |
3. Criação do Modelo: Pandas, Numpy, Sklearn, YellowBrick, Pickle, seaborn, matplotlib |

   ## Detalhes do projeto


Os dados deste case foram retirados do P.E.D, e você pode acessar o P.E.D [aqui](https://www.renatabiaggi.com/ped)



<h2 align ="center">Autor 🚀</h2>
<a>
<img style = "border-radius: 50%;" src = https://github.com/KaueAbbe/Analise_ChurnRate/assets/68445400/bd4b5b79-4826-4d72-91e4-5fc7532ac19b width="250px;" alt=""/>

 <sub><b></b></sub></a> 

<h4> Feito com 💙 por Kaue Hermann Abbehausen 👋🏽 
<br/> 
 
 1. Formado em Física na Universidade Federal de Uberlândia
 
 2. Mestrando em Física Estatística na Universidade de Brasília
    
 3. Aprofundando como Cientista de Dados</h4>
<h4> Entre em contato por</h4>
<div align = "center"> 

 
   <a href="https://www.linkedin.com/in/kaue-abbehausen-5b1922165/" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a> 
  <a href="https://www.instagram.com/cienciaeanimacao/" target="_blank"><img src="https://img.shields.io/badge/-Instagram-%23E4405F?style=for-the-badge&logo=instagram&logoColor=white" target="_blank"></a>
  <a href = "mailto:kaueabbehausen@hotmail.com"><img src="https://img.shields.io/badge/Microsoft_Outlook-0078D4?style=for-the-badge&logo=microsoft-outlook&logoColor=white" target="_blank"></a>
</div>
