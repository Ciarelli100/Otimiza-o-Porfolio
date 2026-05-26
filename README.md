# Otimização de Carteiras: Algoritmo Genético vs. Markowitz

#### Aluno: [Rafael Ciarelli](https://github.com/Ciarelli100)
#### Orientadora: [Carolina Abreu]

---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

- [Link para o código](https://github.com/Ciarelli100/Otimiza-o-Porfolio).

---

### Resumo

Este trabalho propõe um modelo de otimização de portfólio multi-asset utilizando o Algoritmo Genético NSGA-II, comparando seus resultados ao modelo clássico de Markowitz (Média-Variância). O estudo utiliza 11 benchmarks do mercado brasileiro e internacional — incluindo renda fixa, ações, câmbio e ativos reais — com dados históricos do período de 2011 a 2025. O objetivo é avaliar se a abordagem evolucionária consegue gerar carteiras com melhor relação risco-retorno do que a fronteira eficiente tradicional, mantendo restrições práticas de alocação. Os resultados demonstram que o Algoritmo Genético produziu carteiras superiores em todos os três critérios analisados (mínima variância, melhor Sharpe e maior retorno), com acumulado de até 547% no período frente a 358% do Markowitz clássico.

### Abstract

This work proposes a multi-asset portfolio optimization model using the NSGA-II Genetic Algorithm, benchmarking its results against the classical Markowitz Mean-Variance model. The study covers 11 Brazilian and international market benchmarks — including fixed income, equities, foreign exchange, and real assets — with historical data from 2011 to 2025. The goal is to assess whether the evolutionary approach can generate portfolios with a better risk-return trade-off than the traditional efficient frontier, while respecting practical allocation constraints. Results show that the Genetic Algorithm outperformed Markowitz across all three criteria evaluated (minimum variance, best Sharpe, and maximum return), with a cumulative return of up to 547% over the period, compared to 358% for the classical model.

### 1. Introdução

A seleção eficiente de carteiras de investimento é um dos problemas centrais das finanças modernas. O modelo proposto por Markowitz em 1952 formalizou matematicamente o conceito de diversificação, estabelecendo a fronteira eficiente como o conjunto de portfólios que maximizam o retorno esperado para um dado nível de risco. Apesar de sua solidez teórica, o modelo clássico apresenta limitações práticas relevantes: sensibilidade extrema aos parâmetros de entrada (médias e covariâncias), tendência a concentrar alocações em poucos ativos e dificuldade em lidar com restrições complexas.

Com o avanço da computação, os algoritmos evolutivos emergiram como uma alternativa viável para problemas de otimização multi-objetivo. O NSGA-II (Non-dominated Sorting Genetic Algorithm II) é um algoritmo genético de segunda geração amplamente utilizado em problemas de otimização com múltiplos objetivos conflitantes, como a maximização simultânea de retorno e minimização de risco em carteiras de investimento.

Este trabalho aplica o NSGA-II para otimizar portfólios compostos por 11 benchmarks representativos do mercado brasileiro e internacional, cobrindo as principais classes de ativos disponíveis ao investidor local, e compara os resultados obtidos com as soluções da fronteira eficiente de Markowitz sobre o mesmo universo e período histórico (2011–2025).

### 2. Modelagem

**Universo de Ativos**

O estudo utiliza 11 benchmarks como classes de ativos:

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
| Ouro (XAU) | Proteção e diversificação |

Os dados históricos foram obtidos junto à ANBIMA e à B3, cobrindo o período de janeiro de 2011 a dezembro de 2025.

**Modelo de Markowitz**

A otimização clássica minimiza a variância do portfólio sujeita a uma meta de retorno esperado, com restrições de que os pesos somam 1 e são não negativos (sem venda a descoberto). A fronteira eficiente é traçada variando sistematicamente o nível de retorno alvo. A implementação utilizou a biblioteca SciPy com o método SLSQP.

**Algoritmo Genético (NSGA-II)**

O NSGA-II foi implementado com a biblioteca DEAP. Cada indivíduo representa um vetor de pesos normalizados para os 11 ativos. Os objetivos de otimização são simultâneos: minimizar a volatilidade anualizada e maximizar o retorno esperado anualizado. O algoritmo evolui a população ao longo de gerações por meio de seleção por dominância de Pareto, cruzamento e mutação, produzindo uma fronteira de soluções não-dominadas.

**Tecnologias utilizadas:**
- Python 3.x
- DEAP (algoritmo genético NSGA-II)
- SciPy (otimização Markowitz)
- Pandas / NumPy (tratamento de dados)
- Plotly / Matplotlib / Seaborn (visualizações)

**Estrutura do repositório:**
```
portfolio-otimizacao/
├── data/
│   └── base_benchmarks.xlsx   # Dados históricos dos benchmarks
├── notebooks/
│   └── projeto_final_estrategia.ipynb
├── requirements.txt
└── README.md
```

**Como reproduzir:**
```bash
# 1. Clone o repositório
git clone https://github.com/Ciarelli100/Otimiza-o-Porfolio.git

# 2. Instale as dependências
pip install -r requirements.txt

# 3. Adicione o arquivo de dados em data/
# (base_benchmarks.xlsx — fonte: ANBIMA / B3)

# 4. Abra o notebook
jupyter notebook notebooks/projeto_final_estrategia.ipynb
```

### 3. Resultados

As carteiras otimizadas pelo Algoritmo Genético foram comparadas à solução de Markowitz em três pontos representativos da fronteira eficiente:

| Carteira | Retorno Esperado (a.a.) | Volatilidade (a.a.) | Acumulado 2011–2025 | % do CDI Acumulado |
|----------|------------------------|---------------------|---------------------|--------------------|
| Min. Variância (AG) | 10,9% | 2,88% | 369,8% | 123,1% |
| Melhor Sharpe (AG) | ~12,0% | ~5,0% | 473,9% | 157,7% |
| Maior Retorno (AG) | 13,5% | 8,10% | 547,0% | 182,0% |
| Markowitz | 10,7% | 2,84% | 358,1% | 119,2% |

Em todos os cenários, o Algoritmo Genético apresentou retorno acumulado superior ao modelo de Markowitz. A carteira de melhor Sharpe do NSGA-II entregou 473,9% acumulados no período — 32,2 pontos percentuais acima do CDI e 115,8 pontos acima da solução clássica. A carteira de maior retorno chegou a 547%, representando 182% do CDI acumulado.

A fronteira de Pareto gerada pelo NSGA-II mostrou-se mais diversificada em termos de alocação entre classes de ativos, com menor concentração em ativos individuais comparada à solução de Markowitz, que tendeu a concentrar pesos em renda fixa de baixo risco.

### 4. Conclusões

O trabalho demonstrou que o Algoritmo Genético NSGA-II é uma alternativa eficaz e competitiva ao modelo clássico de Markowitz para a otimização de carteiras multi-asset no contexto do mercado brasileiro.

Os resultados indicam que a abordagem evolucionária oferece três vantagens práticas relevantes: (i) capacidade de explorar de forma mais ampla o espaço de soluções sem depender de gradientes ou convexidade da função objetivo; (ii) maior flexibilidade para incorporar restrições complexas sem reformulação matemática; e (iii) geração de múltiplas soluções não-dominadas em uma única execução, permitindo ao investidor escolher o ponto da fronteira mais alinhado ao seu perfil de risco.

As limitações do estudo incluem o uso de dados históricos sem garantia de repetibilidade futura, a ausência de custos de transação e a sensibilidade dos resultados do algoritmo genético à escolha dos hiperparâmetros. Como trabalhos futuros, sugere-se a incorporação de custos de transação, a aplicação em janelas de tempo móveis (*rolling window*) e a comparação com outros algoritmos evolutivos como o MOEA/D.

---

Matrícula: [232100412]

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
