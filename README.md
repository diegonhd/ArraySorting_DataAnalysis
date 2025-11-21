🚀 Projeto de Benchmark de Algoritmos de Ordenação

Análise de Desempenho e Complexidade de Algoritmos Clássicos em Python (1k a 50k Elementos)

Este projeto de Análise de Algoritmos implementa 10 algoritmos de ordenação em Python para realizar um benchmark completo, medindo e comparando a performance em diferentes escalas (até 50.000 elementos) e cenários (aleatório e pior caso). O objetivo é validar empiricamente as complexidades temporais teóricas ($O(n^2)$, $O(n \log n)$, $O(n+k)$).

💻 Como Executar

Para rodar este benchmark, você precisará do Python 3 e das bibliotecas listadas abaixo.

Instalação de Dependências:

pip install numpy pandas matplotlib


Geração de Dados: Execute todas as células no notebook arrays.ipynb.

Atenção: Esta etapa pode levar alguns minutos, especialmente para os algoritmos de complexidade quadrática ($O(n^2)$).

Análise e Visualização: Após a conclusão, execute todas as células no notebook sort_benchmark.ipynb para processar os dados e gerar os gráficos.

🎯 Algoritmos Implementados e Analisados

O projeto cobre as principais classes de complexidade assintótica, oferecendo uma visão holística sobre a eficiência em ordenação:

Classe de Complexidade

Algoritmos Implementados

Implementação Notável

Quadrática

Bubble Sort, Selection Sort, Insertion Sort

Implementação simples e direta.

Log-Linear

Quick Sort, Merge Sort, Heap Sort

Quick Sort com pivô no último elemento (lista[n-1]).

Linear (Counting)

Counting Sort, Radix Sort, Bucket Sort

Ideal para dados com range (k) limitado.

Intermediário

Shell Sort

Estratégia de gap inicial = n // 2.

📈 Análise e Principais Conclusões

A análise quantitativa, ilustrada por gráficos de desempenho com escala logarítmica, revela uma clara subdivisão de performance e as nuances de cada algoritmo.

1. O Ponto de Ruptura: Complexidade Quadrática ($O(n^2)$)

Os algoritmos de complexidade quadrática (Bubble Sort, Selection Sort e Insertion Sort) demonstraram o pior desempenho, com tempos de execução na escala de $10^2$ segundos para $N=50k$. O crescimento de suas curvas é exponencial no gráfico logarítmico, confirmando a inviabilidade para grandes volumes de dados.

2. Robustez Log-Linear ($O(n \log n)$)

Merge Sort (Estabilidade Garantida): Este algoritmo provou ser o mais estável e previsível. Seu desempenho é $O(n \log n)$ em todos os cenários, com as linhas de Caso Médio e Pior Caso quase sobrepostas. Essa estabilidade tem o custo de $O(n)$ de espaço extra na memória (para cópias de subarrays), validando o trade-off de tempo vs. espaço.

Heap Sort (Estabilidade Teórica): Assim como o Merge Sort, o Heap Sort garante uma performance $O(n \log n)$ no pior caso. Suas curvas escalam de forma eficiente, comprovando sua robustez em situações de dados imprevisíveis.

Shell Sort (Intermediário Prático): Embora sua complexidade teórica (com a sequência n // 2) tenda a $O(n^2)$, o desempenho prático foi significativamente superior aos demais $O(n^2)$ e próximo aos $O(n \log n)$ para a escala testada.

3. A Dicotomia do Quick Sort

Caso Médio (Otimizado): O Quick Sort foi o algoritmo de comparação mais rápido no caso médio, escalando de forma altamente eficiente.

Pior Caso (Vulnerável): A utilização ingênua do último elemento como pivô revelou sua fragilidade. No pior cenário testado (arrays inversamente ordenados), o desempenho se degradou para $O(n^2)$, o que é claramente visível no gráfico "Comparação dos Piores Casos" quando sua linha "salta" para o grupo dos algoritmos lentos.

4. Ultra Velocidade: Ordenação Linear ($O(n+k)$)

Counting Sort e Radix Sort: Estes algoritmos não-comparativos foram, de longe, os mais rápidos no benchmark. Suas curvas são praticamente horizontais (crescimento $O(n)$), pois o overhead é dominado pelo tamanho da lista ($N$) e não pela complexidade logarítmica. Este resultado demonstra a extrema eficiência desses métodos para problemas com um range de valores (k) fixo e pequeno.

📂 Estrutura do Projeto

Arquivo/Item

Função

Resultados Gerados

arrays.ipynb

Implementação dos 10 algoritmos e execução dos testes de tempo (benchmarking).

Arquivos binários .npy (ex: list_bs.npy) contendo todos os dados de tempo brutos.

sort_benchmark.ipynb

Processamento de dados brutos e organização em DataFrames. Criação de todas as visualizações (gráficos logarítmicos).

Arquivos CSV (resultados_medias.csv e resultados_piores_casos.csv) com os tempos resumidos.

Gráficos (Matplotlib)

Ilustração visual da escalabilidade e complexidade de cada algoritmo.

Imagens de comparação de Caso Médio e Pior Caso (escala logarítmica).

🛠️ Habilidades Demonstradas

Análise de Algoritmos: Implementação e validação empírica das complexidades $O(n^2)$, $O(n \log n)$, e $O(n+k)$.

Programação Python Científica: Uso eficiente de numpy e pandas para manipulação e processamento de dados em larga escala.

Visualização de Dados: Geração de gráficos claros e informativos (matplotlib), incluindo a interpretação de escalas logarítmicas.

Engenharia de Software: Benchmarking e testes de estresse de diferentes lógicas de implementação.