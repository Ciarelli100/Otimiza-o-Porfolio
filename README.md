# 📊 Otimização de Portfólio com Algoritmos Evolutivos e Modelo de Markowitz

## 📌 Descrição

Este repositório contém o código desenvolvido para o Trabalho de Conclusão de Curso (TCC), cujo objetivo é aplicar técnicas de **otimização de portfólio** para identificar diferentes estratégias de alocação entre benchmarks do mercado financeiro.

O projeto compara duas abordagens de otimização:

* **Modelo clássico de Markowitz (Mean-Variance)**
* **Algoritmo Evolutivo**

A partir dessas metodologias, são geradas diferentes carteiras ótimas considerando critérios de **retorno, risco e índice de Sharpe**, permitindo avaliar o desempenho das soluções encontradas por cada método.

---

## 🎯 Objetivo do Trabalho

O objetivo deste trabalho é aplicar técnicas de **otimização de portfólio** utilizando algoritmos evolutivos e comparar os resultados com o modelo clássico de **Markowitz (Mean-Variance)**.

Além disso, o estudo busca investigar se **algoritmos evolutivos são capazes de gerar soluções eficientes para o problema de alocação de ativos**, considerando que ainda existem relativamente **poucos trabalhos aplicando esse tipo de abordagem no contexto de portfólios financeiros**.

Dessa forma, o trabalho pretende:

* Simular diferentes combinações de portfólio
* Avaliar risco e retorno das carteiras
* Comparar os resultados entre **Algoritmos Evolutivos e o modelo de Markowitz**
* Identificar carteiras com diferentes perfis de risco e retorno
* Avaliar se o **algoritmo evolutivo consegue encontrar soluções competitivas** em relação ao método tradicional

---

## 📈 Benchmarks Utilizados

Os ativos utilizados na construção das carteiras representam diferentes classes de investimento:

* CDI
* Dólar
* IDA-DI
* IFIX
* IHFA
* IMA-B
* IMA-B 5+
* IRF-M
* Ibovespa
* Ouro (XAU)
* S&P 500

Essa diversificação permite analisar o comportamento do portfólio considerando diferentes segmentos do mercado financeiro, incluindo renda fixa, renda variável e ativos internacionais.

---

## 🧠 Metodologia

O projeto segue as seguintes etapas metodológicas:

1. Coleta dos dados históricos dos benchmarks
2. Cálculo dos retornos dos ativos
3. Construção da matriz de covariância
4. Simulação de diferentes combinações de portfólio
5. Aplicação de métodos de otimização
6. Avaliação das carteiras com base em métricas de risco e retorno

As principais métricas utilizadas são:

* **Retorno esperado do portfólio**
* **Volatilidade (risco)**
* **Índice de Sharpe**

---

## ⚙️ Métodos de Otimização

### Modelo de Markowitz

O modelo clássico de **Mean-Variance Optimization**, proposto por Harry Markowitz, busca encontrar a alocação ótima de ativos que minimize o risco para um determinado nível de retorno esperado. Esse modelo é amplamente utilizado na teoria moderna de portfólios.

### Algoritmo Evolutivo

O algoritmo evolutivo é utilizado como uma abordagem alternativa para o problema de otimização de portfólios. Esse método é inspirado no processo de evolução natural e utiliza operadores como:

* seleção
* recombinação
* mutação

Esses operadores permitem explorar diferentes soluções possíveis ao longo de várias gerações, buscando melhorar gradualmente a qualidade das carteiras geradas.

Neste trabalho, o algoritmo evolutivo é utilizado para investigar se essa abordagem é capaz de gerar **carteiras eficientes e competitivas em relação ao modelo clássico de Markowitz**.

---

## 📊 Carteiras Geradas

O modelo gera quatro carteiras principais para análise:

### Algoritmo Evolutivo

* Carteira de **menor risco**
* Carteira de **maior retorno**
* Carteira com **melhor Índice de Sharpe**

### Modelo de Markowitz

* Carteira ótima baseada na **fronteira eficiente**

Essas carteiras são utilizadas para comparar os resultados obtidos por cada método de otimização.

---

## ⚙️ Tecnologias Utilizadas

O projeto foi desenvolvido utilizando:

* Python
* Pandas
* NumPy
* Matplotlib
* Pymoo (biblioteca para algoritmos evolutivos)

---

## 📂 Estrutura do Projeto

```
tcc-portfolio-optimization/
│
├── src/                 # código fonte do projeto
│   ├── portfolio.py
│   ├── risk.py
│   ├── optimization.py
│   └── toolbox.py
│
├── notebooks/           # notebooks de análise
│   └── analise_portfolio.ipynb
│
├── data/                # dados utilizados nas análises
│
├── requirements.txt
└── README.md
```

---

## ▶️ Como Executar o Projeto

1. Clone o repositório:

```
git clone https://github.com/seuusuario/tcc-portfolio.git
```

2. Acesse a pasta do projeto:

```
cd tcc-portfolio
```

3. Instale as dependências:

```
pip install -r requirements.txt
```

4. Execute o notebook localizado em:

```
notebooks/analise_portfolio.ipynb
```

---

## 📊 Resultados

A execução do projeto permite visualizar:

* Simulações de diferentes combinações de portfólio
* A **fronteira eficiente**
* Comparação entre as carteiras geradas pelo **algoritmo evolutivo**
* Comparação com a solução obtida pelo **modelo de Markowitz**

Essas análises permitem avaliar se os métodos evolutivos conseguem encontrar **soluções eficientes e competitivas** no problema de alocação de ativos.

---

## ⚠️ Aviso Importante

Este projeto foi desenvolvido **exclusivamente para fins acadêmicos** como parte de um Trabalho de Conclusão de Curso.

Os resultados apresentados **não constituem recomendação de investimento**, nem devem ser utilizados como base para decisões financeiras.

---

## 👨‍💻 Autor

Rafael Xavier

