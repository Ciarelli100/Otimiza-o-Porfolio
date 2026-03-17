# Otimização de Carteiras com Algoritmo Genético vs. Markowitz

## Objetivo
Comparar o desempenho de um algoritmo genético (NSGA-II) com o modelo 
clássico de Markowitz na otimização de portfólios multi-asset no 
mercado brasileiro.

## Benchmarks Utilizados
CDI, Dólar, IDA-DI, IFIX, IHFA, IMA-B, IMA-B 5+, IRF-M, 
Ibovespa, Ouro (XAU), S&P 500 — período 2011–2025.

## Principais Resultados
| Carteira           | Retorno | Volatilidade | Acumulado |
|--------------------|---------|--------------|-----------|
| Min Variância (AG) | 10,9%   | 2,88%        | 369,8%    |
| Melhor Sharpe (AG) | ~12%    | ~5%          | 473,9%    |
| Maior Retorno (AG) | 13,5%   | 8,1%         | 547,0%    |
| Markowitz          | 10,7%   | 2,84%        | 358,1%    |

## Como Rodar
pip install -r requirements.txt
jupyter notebook notebooks/projeto_final_estrategia.ipynb
