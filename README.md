# Benchmark e Análise de Complexidade de Algoritmos

Este projeto consiste em um estudo prático e comparativo de **Estrutura de Dados e Algoritmos**, focado na análise de desempenho de **10 algoritmos de ordenação** (Sorting Algorithms).

O objetivo é confrontar a teoria da complexidade assintótica ($Big-O$) com o tempo de execução real em Python, utilizando grandes volumes de dados e diferentes cenários de ordenação (casos médios aleatórios e piores casos inversamente ordenados).

-----

##  Como Executar este Projeto

Para reproduzir as análises e gráficos em sua máquina local, siga os passos abaixo:

### 1\. Pré-requisitos

Certifique-se de ter o **Python 3.x** instalado e um ambiente para rodar Jupyter Notebooks (VS Code, Jupyter Lab ou Anaconda).

### 2\. Instalação das Dependências

Abra seu terminal e instale as bibliotecas necessárias:

```bash
pip install numpy pandas matplotlib notebook
```

### 3\. Executando os Arquivos

A execução é dividida em duas etapas: geração de dados e visualização.

1.  **Clone ou baixe o repositório.**
2.  **Geração dos Dados:**
      * Acesse a pasta `array archive`.
      * Execute o notebook **`arrays.ipynb`**.
      * *O que ele faz:* Implementa os algoritmos, executa os testes de estresse e salva os tempos brutos em arquivos `.npy` dentro desta mesma pasta.
3.  **Análise e Gráficos:**
      * Volte para a raiz do repositório.
      * Execute o notebook **`sort_benchmark.ipynb`**.
      * *O que ele faz:* Lê os arquivos `.npy` gerados anteriormente, compila os dados em DataFrames e plota os gráficos comparativos finais.

-----

## Tecnologias Utilizadas

  * **Linguagem:** Python 3.12+
  * **Processamento Numérico:** NumPy
  * **Análise de Dados:** Pandas
  * **Visualização de Dados:** Matplotlib
  * **Ambiente de Desenvolvimento:** Jupyter Notebook

-----

##  Algoritmos Implementados

O estudo cobre três categorias de complexidade, permitindo visualizar o "salto" de performance entre diferentes abordagens lógicas.

### 1\. Algoritmos Quadráticos — $O(n^2)$

  * **Bubble Sort**
  * **Selection Sort**
  * **Insertion Sort**
  * **Shell Sort** (Otimizado com estratégia de *gap*, mas agrupado aqui pela performance em pequenos conjuntos).

### 2\. Algoritmos Log-Lineares — $O(n \log n)$

  * **Quick Sort** (Estratégia de pivô: último elemento).
  * **Merge Sort** (Divisão e Conquista).
  * **Heap Sort** (Estrutura de Heap Binária).

### 3\. Algoritmos Lineares / Distribuição — $O(n+k)$

  * **Bucket Sort**
  * **Counting Sort**
  * **Radix Sort**

-----

##  Estrutura do Repositório

```text
├── array archive/              # Módulo de Processamento e Dados Brutos
│   ├── arrays.ipynb            # Implementação dos algoritmos e script de teste
│   ├── list_*.npy              # Arquivos binários com os tempos de execução salvos
│   └── ...
├── resultados_medias.csv       # Tabela consolidada dos testes de Caso Médio
├── resultados_piores_casos.csv # Tabela consolidada dos testes de Pior Caso
├── sort_benchmark.ipynb        # Notebook de Visualização, Gráficos e Conclusões
├── .gitignore
└── README.md
```

-----

## Principais Insights e Resultados

A análise visual dos dados (disponível em `sort_benchmark.ipynb`) revelou conclusões importantes:

### 1\. O Abismo de Desempenho

Em escala logarítmica, a diferença entre as classes de algoritmos é brutal. Enquanto o **Bubble Sort** leva mais de 700 segundos para ordenar 50k elementos no pior caso, algoritmos como **Radix Sort** realizam a mesma tarefa em frações de segundo (0.09s).

### 2\. A Instabilidade do Quick Sort

Apesar de ser extremamente rápido no **Caso Médio** (dados aleatórios), o Quick Sort com pivô fixo degradou para uma performance quadrática $O(n^2)$ no **Pior Caso** (lista invertida), comportando-se de maneira semelhante aos algoritmos mais lentos.

### 3\. Robustez do Merge e Heap Sort

Estes algoritmos demonstraram consistência absoluta. As curvas de tempo para dados aleatórios e dados invertidos foram praticamente idênticas, confirmando a estabilidade de $O(n \log n)$ independente da desordem da entrada.

### 4\. A Supremacia dos Algoritmos Lineares

Os algoritmos de distribuição (**Counting, Radix, Bucket**) superaram todos os outros. O gráfico de "Caso Médio" mostra suas linhas praticamente coladas ao eixo X (tempo próximo de zero), validando a complexidade $O(n+k)$ para ordenação de inteiros.

-----
