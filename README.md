# **Projeto - Previsão IBOVESPA**

**Proposta do Projeto**
---
Realizar um modelo preditivo com dados da IBOVESPA(Bolsa de valores) para criar uma série temporal e prever diariamente o fechamento da base.

**Contexto**
---

Neste projeto, analisamos e previmos o fechamento do IBOVESPA, o principal índice de desempenho das ações negociadas na B3, a bolsa de valores oficial do Brasil, utilizando dados de 2005 a 2024.

Dividimos os dados em períodos anuais para entender o cenário total, posteriormente, em intervalos diários, para identificar padrões e tendências de mercado. Aplicamos modelos de previsão para intervalos de 3 a 15 dias, com o objetivo de melhorar a precisão e entender as variações de curto prazo. Esta abordagem detalhada visa aprimorar a tomada de decisão em investimentos financeiros.

**Arquivos .ipynb**
---
Todo o desenvolvimento e resultados obtidos estão disponíveis em: [Resultados](https://github.com/Grupo-40/tech-challenge-2/tree/main/eda)


**Modelos Testados**
---

* Arima
* Prophet
* Sarima
* Naive
  
**Resultados**
---

Para a análise foram coletados dados de preços (máximos, mínimos, aberturas e fechamentos) em  periodicidades diárias, conforme pode-se observar no gráfico. Destaca-se que a base histórica possui oscilações ao longo do período. Sendo identificadas quedas significativas no fechamento da IBOVESPA em 2009, 2016 e 2020. Essas quedas estão relacionadas com a crise imobiliária mundial iniciada nos Estados Unidos, a  crise na política brasileira e a pandemia do COVID-19, respectivamente.

![](figure/fechamento_hist.png)

* **Modelos Arima e Prophet**

Após os tratamentos pertinentes na base  foi realizada a divisão dos dados entre treino e teste. Sendo que foi utilizado 80% para treino e 20% para teste. 

![](figure/fechamento_hist_treino_teste.png)


* **Realizando as previsões com o Modelo Arima**
  
Aplicou-se o modelo ARIMA com os termos “p”, “d” e “q” com os valores 1, 1 e 1 respectivamente. Assim obteve-se um RMSE (Root Mean Squared Error) de 11%. A determinação dos valores dos termos pode não ser exata, dado que depende da análise do observador, assim, podendo ser incorreta. Entendendo esta dificuldade, utilizou-se a função **pmd.arima.auto_arima**. Está foi projetada para selecionar o modelo ARIMA ideal. 

Para realizar predição futura para os próximos 15 dias em que utilizou-se a base histórica (base de treino (03-01-2005 - 01/07/2024)). Obtendo-se um RMSE (Root Mean Squared Error) de 1,3%. 

![](figure/base_hist_completa_15_dias_arima.png)


O modelo Arima apresentou bons resultados quando utilizado para prever poucos dias.


* **Realizando as previsões com o Modelo Prophet**

Inicialmente utilizou-se a predição para os próximos 15 dias (utilizando 80% treino e 20% teste). Este apresentou um RMSE de 16%. 

![](figure/base_hist_80_20_15_dias_prophet.png)


Posteriormente, realizando predição para os próximos 15 dias (utilizando 95% treino e 5% teste). Obtendo-se um RMSE de 6%. 

![](figure/base_hist_completa_15_dias_prophet.png)


O modelo Prophet apresentou resultados medianos, sendo que os melhores resultados podem ser observados em poucos dias.

Previsão Futura - Foram preditos o fechamento da bolsa nos próximos 5 dias.

|               | Modelo Arima      | Modelo Prophet    |
|---------------|-------------------|-------------------|                 
| 2024-07-17    | 128466.96         | 116201.06         | 
| 2024-07-18    | 129451.42         | 116275.63         | 
| 2024-07-19    | 129460.74         | 116364.82         | 
| 2024-07-22    | 130204.63         | 116508.02         | 
| 2024-07-23    | 130370.51         | 116542.33         | 



Principais motivos : 
1) Complexidade do mercado de ações : O mercado de ações é altamente volátil e influenciado por fatores imprevisíveis, como notícias, eventos políticos e mudanças econômicas.
2) Limitações de tendência linear : Os modelos assumem uma tendência de crescimento não linear, mas muitas ações têm padrões mais complexos. A tendência linear pode não se ajustar bem a esses dados.
3) Previsões de longo prazo : Os modelos são mais adequados para previsões de curto a médio prazo. 

**Conclusões**
---


**Referências Bibliográficas**
---
SILVEIRA, P. H. M. (2019). O que move o preço da ação? Um estudo sobre as maiores variações diárias do Ibovespa na década de 2010.<br>
IBOVESPA(IBOV).Inventing.com, 2024. Disponível: < https://br.investing.com/indices/bovespa-historical-data >. Acesso em: 16 de jul. de 2024.

