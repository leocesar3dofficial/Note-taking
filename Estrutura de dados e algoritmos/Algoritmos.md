# Algoritmos

## Conceito

Conjunto de operações executadas passo a passo para executar uma tarefa. Pode ser visto como um processo ou conjunto de instruções.

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
     - A velocidade de transferência de dados, caso em rede.
2. **De espaço:**
   - Mede a quantidade de espaço necessária para executar o código.
   - Espaço Auxiliar: espaço extra usado no programa além da estrutura de dados de entrada.

### Notação assintótica ou "f está em Ο(g)"

#### Conceito

Ferramenta matemática que calcula o tempo necessário de execução. Considera o tamanho de entrada e não requer a execução do código.

#### Tipos

- **Notação Big-O (Ο):** Descreve o pior cenário possível (mais usado de todos).
  - Ruim (N log de N): O(N \* log(N)).
  - Pior: O(N!), O(c^N), O(N^c).
    - Quadrático: O(N^2).
    - Cúbico: O(N^3).
  - Razoável (linear): O(N).
  - Bom (logaritímica): O(log(N)).
  - Melhor (constante): O(1).
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
   - Busca elementos ou grupos de elementos de uma determinada estrutura de dados.
   - Podem ser de tipos diferentes.
5. **Ordenação/Classificação**
   - **Características:**
     - Organizar dados de uma maneira particular.
     - Classificar dados de maneira crescente ou decrescente.
   - **Tipos (do mais lento ao mais rápido):**
     1. **Bubble Sort**
        - **Características:**
          - O mais simples dos algoritmos de ordenação.
          - Não é adequado para grandes conjuntos de dados.
        - **Etapas:**
          1. Atravessa da esquerda e compara os elementos adjacentes e o mais alto é colocado no lado direito.
          2. O maior elemento é movido primeiro para a extremidade mais à direita.
        - **Complexidade:**
          - Tempo: O(N^2) (Pior).
          - Espaço: O(1) (Constante).
     2. **Selection Sort**
        - **Características:**
          - Simples e eficiente.
        - **Etapas:**
          1. Seleciona repetidamente o menor (ou maior) elemento da parte não classificada.
          2. Troca o elemento para a parte classificada da lista.
        - **Complexidade:**
          - Tempo: O(N^2) (Pior).
          - Espaço: O(1) (Constante).
     3. **Insertion Sort**
        - **Características:**
          - Funciona como classificar cartas em um baralho.
        - **Etapas:**
          1. A matriz é virtualmente dividida em uma parte classificada e outra não classificada.
          2. Os valores da parte não classificada são selecionados e colocados na posição correta na parte classificada.
        - **Complexidade:**
          - Tempo: O(N^2) (Pior).
          - Espaço: O(N) (Linear).
        - **Implementação (Python):**
          ```python
          def insertion_sort(lista):
              for i in range(1, len(lista)):
                  chave = lista[i]
                  k = i
                  while k > 0 and chave < lista[k - 1]:
                      lista[k] = lista[k - 1]
                      k -= 1
                  lista[k] = chave
          ```
     4. **Quick Sort**
        - **Características:**
          - Usa a abordagem Dividir e Conquistar (ineficiente em sua complexidade de tempo).
        - **Etapas:**
          1. Escolhe um pivô e o coloca em sua posição correta no array.
          2. Classifica e particiona os elementos menores à sua esquerda e os maiores à sua direita.
        - **Complexidade:**
          - Tempo: O(N \* log(N)) (Ruim).
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
