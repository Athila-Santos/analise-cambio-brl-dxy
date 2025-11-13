# Análise da Dinâmica do Câmbio: BRL, DXY e Moedas Globais

Este repositório contém uma análise de dados em Python sobre a taxa de câmbio do Real Brasileiro (`BRLUSD=X` e `USDBRL=X`), investigando seu comportamento histórico e seu contexto frente ao Índice Dólar (DXY) e outras moedas.

A análise foi dividida em duas partes principais, espelhando os posts do LinkedIn planejados.

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

## Metodologia e Tickers

* **Dados:** Obtidos via biblioteca `yfinance`.
* **Ferramentas:** Python (Pandas, Numpy, Matplotlib, Seaborn).
* **Tickers Principais:**
    * `BRLUSD=X` (Real por Dólar - Usado na Análise 1)

* **Padronização de Moedas (Gráfico 2.3):** Para comparar todas as moedas em relação ao USD, tickers como `USDBRL=X` foram invertidos (`1/USDBRL`) para representar a "força" da moeda local.