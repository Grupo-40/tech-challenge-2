# **Projeto - Previsão IBOVESPA**

**Proposta do Projeto**
---
Realizar um modelo preditivo com dados da IBOVESPA(Bolsa de valores) para criar uma série temporal e prever diariamente o fechamento da base.

**Contexto**
---
O Índice Bovespa, ou Ibovespa, é o principal indicador de desempenho das ações negociadas na B3, a bolsa de valores oficial do Brasil. Criado em 1968, o índice reúne as empresas mais importantes do país, e consolidou-se ao longo dos anos como a referência do mercado de capitais brasileiro para investidores locais e estrangeiros (SILVEIRA, 2010).

**Fonte de Dados:** [Site da Investing](https://br.investing.com/indices/bovespa-historical-data). 

Neste projeto, analisamos e previmos investimentos utilizando dados de 2005 a 2024. Dividimos os dados em períodos anuais e, posteriormente, em intervalos de 180 dias, para identificar padrões e tendências de mercado. Aplicamos modelos de previsão para intervalos de 3 e 5 dias, com o objetivo de melhorar a precisão e entender as variações de curto prazo. Esta abordagem detalhada visa aprimorar a tomada de decisão em investimentos financeiros.

**Modelos Testados**
---

* Arima
* Prophet
* Sarima
* Naive
  
**Resultados**
---
No gráfico abaixo é possível ver que a base histórica possui oscilações ao longo do período. Sendo possível vizualizar quedas significativas no fechamento do IBOVESPA em 2009, 2016 e 2019. Essas quedas estão relacionadas com a crise imobiliária mundial iniciada nos Estados Unidos, a  crise na política brasileira e a pandemia do COVID-19, respectivamente.
(figure/fechamento_hist.png)





Prophet : (inserir índice)
Arima : (inserir índice)
Ambos com baixa assertividade. 

Principais motivos : 
1) Complexidade do mercado de ações : O mercado de ações é altamente volátil e influenciado por fatores imprevisíveis, como notícias, eventos políticos e mudanças econômicas.
2) Limitações de tendência linear : Os modelos assumem uma tendência de crescimento não linear, mas muitas ações têm padrões mais complexos. A tendência linear pode não se ajustar bem a esses dados.
3) Previsões de longo prazo : Os modelos são mais adequados para previsões de curto a médio prazo. 

**Conclusões**
---


**Referências Bibliográficas**
---
SILVEIRA, P. H. M. (2019). O que move o preço da ação? Um estudo sobre as maiores variações diárias do Ibovespa na década de 2010.

