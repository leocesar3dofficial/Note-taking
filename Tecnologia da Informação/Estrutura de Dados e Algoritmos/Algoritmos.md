# Algoritmos

## Conceito

- Conjunto de operações executadas passo a passo para executar uma tarefa.
- Pode ser visto como um processo ou um conjunto de instruções.

## Objetivos

- Resolver um ou mais problemas de forma eficaz e eficiente.
- Realizar um tipo específico de cálculo.

## Complexidade (medida de eficiência)

### Tipos

1. **De tempo:**
   - Mede a quantidade de tempo necessária para executar o código.
   - Fatores que impactam o tempo de execução:
     - O número de operações.
     - A velocidade do dispositivo.
     - A velocidade de transferência de dados, caso esteja em uma rede.
2. **De espaço:**
   - Mede a quantidade de espaço (uso de memória) necessária para executar o código.
   - Espaço Auxiliar: espaço extra usado no programa além da estrutura de dados de entrada.

### Notação assintótica ou "f está em Ο(g)"

#### Conceito

- Ferramenta matemática que calcula o tempo necessário de execução.
- Considera o tamanho de entrada e não requer a execução do código.

#### Tipos

- **Notação Big-O (Ο):** Descreve o pior cenário possível (mais usado de todos).
  - Melhor (constante): O(1).
  - Bom (Logarítmica): O(log(N)).
  - Razoável (linear): O(N).
  - Ruim (N log de N): O(N \* log(N)).
  - Pior: O(N!), O(c^N), O(N^c).
    - Quadrático: O(N^2).
    - Cúbico: O(N^3).
- **Notação Omega (Ω):** Descreve o melhor cenário.
- **Notação Theta (θ):** Representa a complexidade média de um algoritmo.

## Tipos

1. **Força Bruta**
   - Abordagem mais simples.
2. **Recursivo**
   - O problema é dividido em várias subpartes.
   - Chama-se a mesma função repetidas vezes.
3. **Backtracking**
   - Constrói a solução pesquisando entre todas as soluções possíveis.
   - Se uma solução falha, rastreia-se o ponto de falha e constrói-se a próxima solução.
   - Continua esse processo até encontrar a solução ou todas as soluções possíveis.
4. **Busca**
   - **Características:**
     - Busca elementos ou grupos de elementos de uma determinada estrutura de dados.
     - Podem ser de tipos diferentes.
   - **Tipos (do mais lento ao mais rápido):**
     1. **Linear Search**
        - **Características**
          - Percorre cada elemento sequencialmente até encontrar o elemento desejado ou atingir o final da lista.
          - Recomendado para um dataset pequeno.
        - **Complexidade:**
          - Tempo: O(N) (Linear).
          - Espaço: O(1) (Constante).
     2. **Sentinel Linear Search**
        - **Características**
          - Similar à busca linear, mas com um elemento extra (sentinela) no final da lista, o que elimina a necessidade de verificar o final da lista durante a busca.
        - **Complexidade:**
          - Tempo: O(n) (Linear).
          - Espaço: O(1) (Constante).
     3. **Binary Search**
        - **Características**
          - Requer que a lista esteja ordenada.
          - Divide repetidamente a lista ao meio e compara o elemento alvo com o elemento no meio, eliminando metade da lista em cada iteração.
        - **Complexidade:**
          - Tempo: O(log n) (Logarítmica).
          - Espaço: O(1) (Constante).
     4. **Ternary Search**
        - **Características**
          - Semelhante à busca binária, mas divide a lista em três partes iguais em vez de duas.
          - Compara com o elemento alvo, elimina uma parte da lista a cada iteração.
        - **Complexidade:**
          - Tempo: O(log3 n) (Logarítmica na base 3).
          - Espaço: O(1) (Constante).
     5. **Interpolation Search**
        - **Características**
          - Também exige que a lista esteja ordenada.
          - Calcula uma estimativa da posição do elemento alvo com base na distribuição dos valores na lista e ajusta a posição de busca.
        - **Complexidade:**
          - Tempo: O(n) (Linear).
          - Espaço: O(1) (Constante).
5. **Ordenação/Classificação**
   - **Características:**
     - Organizar dados de uma maneira particular.
     - Classificar dados de maneira crescente ou decrescente.
   - **Tipos (do mais lento ao mais rápido):**
     1. **Bubble Sort**
        - **Características:**
          - O mais simples, e um dos mais ineficientes, dos algoritmos de ordenação.
          - Utilizado apenas para fins didáticos.
          - Não é adequado para grandes conjuntos de dados.
          - É estável, ou seja, não altera a ordem relativa dos elementos que possuem o mesmo valor de chave de ordenação.
          - Percorre repetidamente a lista a ser ordenada, comparando o elemento corrente com o seguinte e, se necessário, trocando os seus valores.
          - O maior elemento (ou o menor, dependendo da direção da ordenação) "sobe" gradualmente até a posição correta, como uma bolha na superfície da água.
          - A cada iteração, o maior elemento "flutua" para a última posição não ordenada.
        - **Etapas:**
          1. Atravessa da esquerda e compara os elementos adjacentes e o mais alto é colocado no lado direito.
          2. O maior elemento é movido primeiro para a extremidade mais à direita.
        - **Complexidade:**
          - Tempo: O(n^2) (Pior).
          - Espaço: O(1) (Constante).
     2. **Selection Sort**
        - **Características:**
          - Simples e eficiente.
          - Encontra o menor elemento e o coloca na primeira posição, depois o segundo menor e o coloca na segunda posição, e assim por diante.
          - Divide a lista a ser ordenada em duas partes:
            - Sublista ordenada de elementos.
              - Vazia no início.
              - É construída da esquerda para a direita (ordem crescente).
            - Sublista referente aos elementos não ordenados.
        - **Etapas:**
          1. Seleciona repetidamente o menor (ou maior) elemento da parte não classificada.
          2. Troca o elemento para a parte classificada da lista.
        - **Complexidade:**
          - Tempo: O(n^2) (Pior).
          - Espaço: O(1) (Constante).
     3. **Insertion Sort**
        - **Características:**
          - Funciona como classificar cartas em um baralho.
          - É estável.
          - Percorre o vetor da esquerda para a direita, deixando os elementos à esquerda ordenados.
        - **Etapas:**
          1. A matriz é virtualmente dividida em uma parte classificada e outra não classificada.
          2. Os valores da parte não classificada são selecionados e colocados na posição correta na parte classificada.
        - **Complexidade:**
          - Tempo: O(n^2) (Pior).
          - Espaço: O(n) (Linear).
     4. **Quick Sort**
        - **Características:**
          - Usa a abordagem Dividir e Conquistar (ineficiente em sua complexidade de tempo).
        - **Etapas:**
          1. Escolhe um pivô e o coloca em sua posição correta no array ou matriz.
          2. Classifica e particiona os elementos menores à sua esquerda e os maiores à sua direita.
        - **Complexidade:**
          - Tempo: O(n \* log(n)) (Ruim).
          - Espaço: O(1) (Constante).
6. **Hash**
   - Semelhante ao algoritmo de busca.
   - Contém um índice com um ID de chave.
   - Uma chave é atribuída a dados específicos.
7. **Dividir e Conquistar**
   - **Etapas:**
     1. Dividir: divide um problema em subproblemas.
     2. Resolver: resolve um único subproblema.
     3. Combinar: mescla as soluções para obter a solução final.
8. **Greedy**
   - A solução é construída parte a parte.
   - A solução que oferece o maior benefício será escolhida como a solução para a próxima parte.
9. **Programação Dinâmica**
   - Divide o problema em subproblemas sobrepostos menores e os resolve.
   - Usa a solução já encontrada para evitar o cálculo repetitivo da mesma parte do problema.
10. **Randomizado**
    - Usa um número aleatório para que dê um benefício imediato.
    - O número aleatório ajuda a decidir o resultado esperado.
