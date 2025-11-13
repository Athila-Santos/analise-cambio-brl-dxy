# Análise da Dinâmica do Câmbio: BRL, DXY e Moedas Globais

Este repositório contém uma análise de dados em Python sobre a taxa de câmbio do Real Brasileiro (`BRLUSD=X` e `USDBRL=X`), investigando seu comportamento histórico e seu contexto frente ao Índice Dólar (DXY) e outras moedas.

A análise foi dividida em duas partes principais, espelhando os posts do LinkedIn.

O notebook completo com todo o código está em: `analise_cambio_brl.ipynb`

---

## Análise 1: Dinâmica Histórica do BRL/USD (2007-2025)

Esta seção foca no desempenho histórico do Real (`BRLUSD=X`), analisando volatilidade, retorno e trajetórias anuais.

### 1.1 Volatilidade e Retorno (Comparação YTD)

Para uma comparação justa, os dados de todos os anos foram filtrados para incluir apenas o período de 1º de Janeiro até o dia atual do ano que a análise foi realizada (12 de Novembro).

![Volatilidade e Retorno YTD](results\post1_bars.png)

### 1.2 Análise de Risco vs. Retorno (Jan-Nov)

Este gráfico plota o Risco (Volatilidade Anualizada) contra o Retorno Acumulado no período. Vemos 2025 posicionado em relação aos anos de crise (alta vol) e anos de calmaria.

![Risco vs Retorno](results\post1_scatter.png)

### 1.3 Trajetória dos Melhores, Piores e Ano Atual

Usando dias de pregão sequenciais como eixo, podemos comparar a trajetória de 2025 (em azul) contra os 3 melhores (verde), os 3 piores (vermelho) e todos os outros anos (cinza).

![Melhores e Piores Anos com Ano Atual](results\post1_best_worst_atual.png)

---

## Análise 2: Contexto Global (BRL vs. DXY e Pares)

Esta seção analisa se os movimentos do BRL são isolados ou seguem a tendência global de força (ou fraqueza) do Dólar (DXY).

### 2.1 Correlação de Tendência (BRL vs. DXY)

Este gráfico compara a tendência (média móvel de 22 dias) do `USDBRL=X` com o Índice Dólar (`DXY`). Fica claro que as tendências são altamente correlacionadas (Coef. de 0.865).

![BRL vs DXY (Eixo Duplo)](results\post2_brl_dxy.png)

### 2.2 Comparação de Magnitude (BRL vs. DXY - Base 100)

Embora as *tendências* sejam correlacionadas, este gráfico (Base 100 em 2007) mostra que a *magnitude* da desvalorização do Real (azul) foi drasticamente maior que a valorização do Dólar (vermelho) no longo prazo.

![BRL vs DXY (Índice 100)](results\post2_brl_dxy_indice.png)

### 2.3 Análise 2025: BRL vs. Moedas Globais

Dando zoom em 2025, o BRL é comparado a uma cesta de 10 moedas globais contra o USD (Índice Base 100). Isso posiciona o desempenho recente do Real em um contexto global mais amplo.

![Moedas Globais 2025](results\post2_global_2025.png)

---

## Metodologia e Tickers

* **Dados:** Obtidos via biblioteca `yfinance`.
* **Ferramentas:** Python (Pandas, Numpy, Matplotlib, Seaborn).
* **Tickers Principais:**
    * `BRLUSD=X` (Real por Dólar - Usado na Análise 1)
    * `USDBRL=X` (Dólar por Real - Usado na Análise 2)
    * `DX-Y.NYB` (Índice Dólar)
    * *Outros:* `EURUSD=X`, `MXN=X`, `USDARS=X`, `GBPUSD=X`, `AUDUSD=X`, `CNY=X`, `JPY=X`, `CAD=X`, `INR=X`
* **Padronização de Moedas (Gráfico 2.3):** Para comparar todas as moedas em relação ao USD, tickers como `USDBRL=X` foram invertidos (`1/USDBRL`) para representar a "força" da moeda local, alinhando-se a tickers como `EURUSD=X`.