
# ![DataScienceInProduction](https://github.com/erickfog/DataScienceInProduction/blob/main/img/rossman_image.jpg)
## 1. Problema de Negócio

O CEO da rede de farmácia Rossman precisa saber qual a previsão de vendas de cada loja para os próximos meses com intuto de tomar decisões de negócios mais acertivas. O objetivo principal deste projeto é fornecer insights de negócios e construir um modelo capaz de fazer previsão de vendas da rede de farmácias. 

### Lista de Atributos
Atributo | Descrição
---------|----------
Store    | ID único para cada loja.
Sales    | Volume de vendas(variável target). 
Customers| Número de clientes em determinado dia.
Open       | Um indicador para saber se a loja estava aberta; (0 = fechada, 1 = aberta)
StateHoliday | Indica um feriado estadual. (a = feriado, b = feriado da Páscoa, c = Natal, 0 = Nenhum)
SchoolHoliday | Indica se foi afetado pelo fechamento de escolas públicas.
StoreType | Tipos de lojas diferentes. São 4 modelos de loja diferentes: a, b, c e d. 
Assortment | Descreve um nível de estoque. (a = básico, b = extra e c = estendido)
CompetitionDistance | Distância, em metros, do competidor mais proximo.
CompetitionOpenSince[Month/Year] | Ano e mês aproximados os quais o concorrente mais próximo foi aberto.
Promo | Indica se uma loja está fazendo uma promoção naquele dia.
Promo2 | Promo2 é uma promoção contínua e consecutiva para algumas lojas; (0 = Loja não está participando, 1 = Loja participando)
Promo2Since[Year/Week] | Descreve o ano e a semana em que a loja começou a participar da Promo2.
PromoInterval | Descreve os intervalos consecutivos de início da Promo2, nomeando os meses em que a promoção é iniciada novamente.

## 2. Planejamento da Solução

### 2.1 Ferramentas Utilizadas

### 2.2 Implementação da Solução

**Descrição dos Dados:**  Nesta etapa busquei verificar os tipos de dados envolvidos no problema de negócio, bem como identificar valores faltantes e tratar tais valores, nesta etapa busquei identificar ainda os atributos categoricos e numéricos.

**Feature Engineering:** Nesta etapa construi um mapa mental de hipóteses de negócio, apartir de tal mapa mental pude derivar novas fetures bem como verificar a disponibilidade de dados para as hipóteses construidas. O principal objetivo desta etapa foi derivar novos atributos a partir dos já disponíveis.

**Filtragem dos Dados:** Etapa a qual filtrei valores do meu dataset, ou seja, eliminei variáveis que não mais utilizaria na modelagem ou por já terem sido utilizadas na etapa anterior ou por não estarem dentro do escopo de negócio.

**Análise Exploratória dos Dados:** Etapa fundamental do projeto, nesta etapa pude desenvolver a análise univariada, bivariada e multivariada. Nesta etapa, utilizei ferramentas estatísticas para encontrar insights de negócio e entender o impacto das variáveis para a construção do modelo. 

**Preparação dos Dados:** Etapa a qual fiz normalizações, rescaling e encoding das variáveis que necessitavam. Essa etapa é essencial para que os algortimos de machine learning captem o real comportamento das dos atributos e suas relações sem dar um peso maior para variáveis que não necessitam de tal peso.

**Seleção de atributos:** Etapa que utilizei o algortimo boruta para selecionar as variáveis de maior importância para a criação do modelo.

**Machine Learning Modelling:** Etapa em que treinei diversos algortimos de aprendizado de máquina, nesta etapa utilizei os hiperparâmetros default.


**Hyperparameter Fine Tunning:** Nesta etapa, após calcular as performances dos algortimos na etapa anteriores utilizei o algortimos que teve menor RMSE(root mean squared error) para otimizar seus hiperparâmetros, neste etapa utilizei a técnica de random search para otimizar tais valores.


**Conversão do desempenho do modelo em valores de negócios:** Nesta etapa, utilzei o modelo criado para fazer predições e mostrar os cenários possíveis da utilização do modelo em produção, ou seja, converti os resultados das previções em valores financeiros.


## 3. Top Insights

## 4. Modelos de Machine Learning Aplicados

### Avarege Model (Baseline)
### Linear Regression Model
### Linear Regression Regularized Model (LASSO)
### Random Forest Regressor
### XGBoost Regressor

## 5. Machine Learning Model Performance

### Single Performance
Model Name |	MAE |	MAPE |	RMSE |
-----------|------|------|-------|
Random Forest Regressor |	686.639751 | 0.100088 |	1028.114082
Average Model	| 1354.800353 |	0.455051 |	1835.135542
Linear Regression |	1867.023022 |	0.292948 |	2671.800114
Linear Regression Regularized - Lasso	| 1867.577799 |	0.290483 | 2684.030214
XGBoost Regressor |	6682.880735 |	0.949409 |	7329.962032

### Real Performance

Model Name	| MAE CV	| MAPE CV	 | RMSE CV
0	Random Forest Regressor	| 828.67 +/- 193.75 |	0.12 +/- 0.02 |	1242.95 +/- 291.2
0	Linear Regression	| 2046.02 +/- 261.86 |	0.3 +/- 0.01 |	2908.89 +/- 392.31
0	Lasso |	2049.6 +/- 274.99 |	0.29 +/- 0.01	| 2931.24 +/- 409.79
0	XGBoost Regressor |	7049.17 +/- 589.69 |	0.95 +/- 0.0 |	7715.34 +/- 690.4

## 6. Convertendo o Desempenho do Modelo em Resultados de Negócio

## 7. Conclusão
