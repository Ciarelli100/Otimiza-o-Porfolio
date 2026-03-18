# Otimização de Carteiras: Algoritmo Genético vs. Markowitz

## Sobre o Trabalho
TCC do curso de BI MASTER — Puc Rio, 2023.

Desenvolvimento de um modelo de otimização de portfólio multi-asset 
utilizando Algoritmo Genético (NSGA-II) comparado ao modelo clássico 
de Markowitz, aplicado a 11 benchmarks do mercado brasileiro e 
internacional no período 2011–2025.

## Benchmarks Utilizados
| Ativo | Descrição |
|-------|-----------|
| CDI | Renda fixa pós-fixada |
| IDA-DI | Crédito privado pós-fixado |
| IMA-B / IMA-B 5+ | Renda fixa atrelada ao IPCA |
| IRF-M | Renda fixa prefixada |
| IHFA | Fundos multimercado |
| IFIX | Fundos imobiliários |
| Ibovespa | Ações brasileiras |
| S&P 500 | Ações americanas |
| Dólar | Exposição cambial |
| Ouro (XAU) | Proteção/diversificação |

## Principais Resultados
| Carteira | Retorno Esp. | Volatilidade | Acum. 2011–2025 | % CDI Acum. |
|----------|-------------|--------------|-----------------|-------------|
| Min Variância (AG) | 10,9% | 2,88% | 369,8% | 123,1% |
| Melhor Sharpe (AG) | ~12,0% | ~5,0% | 473,9% | 157,7% |
| Maior Retorno (AG) | 13,5% | 8,10% | 547,0% | 182,0% |
| Markowitz | 10,7% | 2,84% | 358,1% | 119,2% |

## Estrutura do Repositório
portfolio-otimizacao/
├── data/
│   └── base_benchmarks.xlsx   # Dados históricos dos benchmarks
├── notebooks/
│   └── projeto_final_estrategia.ipynb
├── requirements.txt
└── README.md

## Como Reproduzir
# 1. Clone o repositório
git clone https://github.com/seu-usuario/seu-repo.git

# 2. Instale as dependências
pip install -r requirements.txt

# 3. Adicione o arquivo de dados em data/
# (base_benchmarks.xlsx — fonte: ANBIMA / B3)

# 4. Abra o notebook
jupyter notebook notebooks/projeto_final_estrategia.ipynb

## Tecnologias
- Python 3.x
- DEAP (algoritmo genético)
- SciPy (otimização Markowitz)
- Pandas / NumPy
- Plotly / Matplotlib / Seaborn

## Autor
Rafael Ciarelli — https://www.linkedin.com/in/rafael-ciarelli-71319248/ — rafaciarelli@hotmail.com
Orientador: Prof. Nome do Orientador
