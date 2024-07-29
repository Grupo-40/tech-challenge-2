# **Projeto - Previsão IBOVESPA**
---

**Grupo 40** - Autores:<br>
André Lima Inácio<br>
Bruna Afonso dos Santos<br>
Charles Ringenberg<br>
Jheniffer Dias Pereira<br>
Pâmela Cristine Amorim Joanas


**Proposta do Projeto**
---
Realizar um modelo preditivo com dados da IBOVESPA(Bolsa de valores) para criar uma série temporal e prever diariamente o fechamento da base.

**Contexto**
---

Neste projeto, analisamos e previmos o fechamento do IBOVESPA, o principal índice de desempenho das ações negociadas na B3, a bolsa de valores oficial do Brasil, utilizando dados de 2005 a 2024.

Dividimos os dados em período anual para compreender o cenário total da base, posteriormente, em intervalos diários, para identificar padrões e tendências de mercado. Aplicamos modelos de previsão para intervalos de 3, 5 a 10 dias, com o objetivo de melhorar a precisão e entender as variações de curto prazo. Esta abordagem detalhada visa aprimorar a tomada de decisão em investimentos financeiros.

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

Para a análise, foram coletados dados de preços, incluindo máximos, mínimos, aberturas e fechamentos, conforme ilustrado no gráfico abaixo. Destaca-se que a base histórica apresenta oscilações ao longo do período, com quedas significativas no fechamento do IBOVESPA em 2009, 2016 e 2020. Essas quedas estão relacionadas à crise imobiliária global iniciada nos Estados Unidos, à crise política no Brasil e à pandemia de COVID-19, respectivamente.

![](figure/fechamento_hist.png)

* **Modelos Arima e Prophet**

Após os tratamentos pertinentes na base foi realizada a divisão dos dados entre treino e teste. Sendo utilizado 80% para treino e 20% para teste. 

![](figure/fechamento_hist_treino_teste.png)


* **Realizando as previsões com o Modelo Arima**
  
Aplicou-se o modelo ARIMA com os termos “p”, “d” e “q” com os valores 1, 1 e 1 respectivamente. Assim obteve-se um RMSE (Root Mean Squared Error) de 11%. A determinação dos valores dos termos pode não ser exata, dado que depende da análise do observador, assim, podendo ser incorreta. Entendendo esta dificuldade, utilizou-se a função **pmd.arima.auto_arima**. Está foi projetada para selecionar o modelo ARIMA ideal. 

Para realizar predição, considerou-se 15 dias para teste e 5 para previsão futura, para isso utilizou-se a base histórica (base de treino (03-01-2005 - 01/07/2024)). Obtendo-se um RMSE (Root Mean Squared Error) de 1,3%. 

![](figure/base_hist_completa_15_dias_arima.png)


O modelo Arima apresentou bons resultados quando utilizado para prever poucos dias.


* **Realizando as previsões com o Modelo Prophet**

Inicialmente, com o objetivo de entender o comportamento do modelo utilizou-se 80% treino e 20% teste. Este apresentou um RMSE de 16%. 

![](figure/base_hist_80_20_15_dias_prophet.png)


Posteriormente, utilizou-se os mesmos dados, mas com ajuste na proporção entre treino e teste para 95% e 5%, respectivamente. Sendo 5% dos dados para teste e previsão futura de 5 dias. Essa abordagem resultou em um RMSE de 6%.

![](figure/base_hist_completa_15_dias_prophet.png)


O modelo Prophet apresentou resultados medianos, sendo mais eficaz em previsões de curto a médio prazo. No entanto, o mercado de ações é altamente volátil e influenciado por fatores imprevisíveis, como notícias, eventos políticos e mudanças econômicas, o que dificulta a previsão precisa. Além disso, muitas ações seguem padrões complexos que os modelos lineares não conseguem capturar adequadamente, evidenciando a necessidade de abordagens mais sofisticadas para previsões de longo prazo.

* **Resultados da Previsão Futura Arima e Prophet**

Abaixo estão os resultados dos modelos utilizados para prever o fechamento da bolsa nos 5 dias seguintes ao último dado da base, que abrangem o período de 17/07 a 23/07. O modelo Auto ARIMA apresentou previsões mais próximas dos fechamentos reais do IBOVESPA, embora ainda não tão preciso. Em comparação com o modelo Prophet, o modelo Auto ARIMA se mostrou mais efetivo em capturar os movimentos de oscilação dos dados no futuro.

|               | Modelo Arima      | Modelo Prophet    |
|---------------|-------------------|-------------------|                 
| 2024-07-17    | 128466.96         | 116201.06         | 
| 2024-07-18    | 129451.42         | 116275.63         | 
| 2024-07-19    | 129460.74         | 116364.82         | 
| 2024-07-22    | 130204.63         | 116508.02         | 
| 2024-07-23    | 130370.51         | 116542.33         | 

**Conclusões**
---


**Referências Bibliográficas**
---
SILVEIRA, P. H. M. (2019). O que move o preço da ação? Um estudo sobre as maiores variações diárias do Ibovespa na década de 2010.<br>
IBOVESPA(IBOV).Inventing.com, 2024. Disponível: < https://br.investing.com/indices/bovespa-historical-data >. Acesso em: 16 de jul. de 2024.

