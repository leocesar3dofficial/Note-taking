# Estruturas de Dados

## Características

### Definição

- Forma de processar, armazenar, recuperar e organizar dados.
- Busca estabelecer acesso e atualização eficientes desses dados.

### Conceitos

- **Traversing**

  - Visitar um elemento de forma sistemática.
  - Usa-se loops.

### Vantagens

- Melhor organização de dados e eficiência de armazenamento.
- Recuperação e manipulação de dados mais rápidas.
- Facilita o design de algoritmos para resolver problemas complexos.
- Facilita a tarefa de atualização e manutenção dos dados.
- Fornece uma melhor compreensão das relações entre os elementos de dados.

### Desvantagens

- Aumento da sobrecarga computacional e de memória.
- Dificuldade em projetar e implementar estruturas de dados complexas.
- Escalabilidade e flexibilidade limitadas.
- Complexidade na depuração e teste.
- Dificuldade em modificar estruturas de dados existentes.

## Classificação

### Tipos de Dados Primitivos

- Inteiro (Integer).
- Ponto Flutuante (Float).
- Character.
- Boolean.
- Double.
- Void.

### Estrutura de Dados (Tipos de Dados Não Primitivos)

#### Linear (Organizados Sequencialmente)

1. Estática (Tamanho Fixo de Memória)

   - Lista (Array)

     - **Características**

       - Coleção de dados do mesmo tipo.
       - Indexados sequencialmente (Índice inicial: 0).
       - Pode ter duas ou mais dimensões.
       - Usado para implementar outras estruturas de dados (Stacks, Queues, Heaps, Hash tables, etc.).

     - **Operações**

       - Inicializar.
       - Procurar (Search): Algoritmos Linear ou Binário.
       - Ordenar (Sort): de forma ascendente ou descendente (Algoritmos Bubble, Insertion ou Quick sort).
       - Inserir (Insert): o valor pode ser inserido em um índice arbitrário.
       - Traverse: visitar valores de forma ordenada.
       - Inverter (Reverse).
       - Atualizar (Update).
       - Deletar (Excluir).

     - **Aplicações**

       - Resolver problemas matriciais.
       - Registros em banco de dados.
       - Criar outras estruturas de dados.
       - Tabelas de consulta (Lookup table).
       - Processamento de imagem e áudio.

2. Dinâmica

   - Fila (Queue)

     - **Características**

       - As operações seguem uma ordem: FIFO (First In First Out).

     - **Aplicações**

       - Tráfego de Websites.
       - Controle de interrupções e tarefas em Sistemas Operacionais.

     - **Operações**

       - Enqueue: adicionar um novo elemento no fim da fila.
       - Dequeue: remover um elemento no início da fila.
       - Peek: acessar o elemento no início da fila sem removê-lo.
       - IsEmpty.
       - Size.

   - Pilha (Stack)

     - **Características**

       - As operações seguem uma ordem: LIFO (Last In First Out).
       - Inserir (push) e remover (pop) um elemento apenas pelo topo da pilha.
       - Usado para implementar algoritmos como o Tower of Hanoi, tree traversal, recursion, etc.
       - Implementado via lista ou linked list.
       - O tamanho da pilha é fixo na inicialização. Ao tentar inserir um elemento adicional, gera-se o erro: stack overflow.

     - **Aplicações**

       - Expressões aritméticas.
       - Recursão.
       - Processar chamadas de função em um software.
       - Usado em máquinas virtuais.

     - **Operações**

       - Push: adicionar um elemento no topo da pilha.
       - Pop: remover o elemento no topo da pilha.
       - Shift (Javascript): remove o primeiro elemento e o retorna como resultado.
       - Peek: acessar o elemento no topo da pilha.
       - IsEmpty: checar se a pilha está vazia.
       - Size: tamanho da pilha.

   - Linked List

     - **Características**

       - Elementos guardados de forma não contígua na memória.
       - Os elementos são unidos (link/ligados/encadeados) por ponteiros (pointers).
       - Usa memória extra para guardar os links.
       - Não é necessário saber o tamanho da lista na inicialização.
       - Usado para implementar outras estruturas de dados como Stacks, Queues, Graphs, etc.
       - O primeiro nó (node) é chamado de cabeça (Head).
       - O ponteiro do último nó será sempre igual a NULL.
       - Uma lista encadeada está vazia se o elemento inicial aponta para nulo ou NULL.
       - Pode crescer ou diminuir.
       - Um elemento pode ser excluído quando está no meio da lista.

     - **Operações**

       - As mesmas de uma lista, mas em vez de usar um índice usa-se os ponteiros.

     - **Tipos**

       - Singly.
       - Doubly.
       - Circular.
       - Doubly Circular.

     - **Aplicações**

       - Representação de matrizes esparsas.
       - Gerenciamento de memória.
       - Undo/Redo history.

#### Não Linear

1. Hash Tables (Tabelas de Dispersão)

   - Permitem o mapeamento eficiente de chaves para valores.
   - Usam uma função de hash para calcular o índice onde os valores associados a uma chave são armazenados.
   - Permite a recuperação rápida de valores com base em suas chaves
     - Tempo médio de acesso constante O(1), desde que a função de hash seja bem projetada.
   - Podem ocorrer colisões quando duas chaves são mapeadas para o mesmo índice.
     - Estratégias de tratamento de colisões são usadas para resolver esse problema.
   - A ordem dos elementos não é definida com base nas chaves.
     - Não há garantia de que os elementos serão armazenados em sequência na memória.

2. Árvore (Tree)

   - **Características**

     - Estrutura hierárquica
       - Com um nó raiz que se ramifica em diferentes níveis de subárvores.
       - Implementadas usando estruturas de dados como arrays, listas encadeadas ou estruturas de nós.
       - Nó inicial chama-se raiz (Root).
       - Nós ligados por arestas (Edge).
       - Possui altura (Height), níveis (Levels) e grau/profundidade (Depth).
     - Relação de parentesco (parent/child).
     - É uma estrutura de dados recursiva.
       - Permite que um problema seja dividido em subproblemas menores.
       - Envolve os nós filhos de um nó pai específico.

   - **Tipos**

     - Binary Tree

       - Árvores binárias são aquelas em que cada nó tem, no máximo, dois filhos: um à esquerda e outro à direita.
       - São utilizadas em algoritmos de busca e ordenação.

     - Heaps

       - Usadas para implementar filas de prioridade.
       - São uma árvore binária especial.
       - Cada nó pai tem um valor menor ou igual aos valores de seus filhos.
       - Garante que o nó raiz contenha o menor valor na árvore.
       - Usados para realizar operações de inserção e remoção do elemento de maior ou menor prioridade.
       - Possui tempo logarítmico.
       - Estratégias de ordenação: Pré-ordem, Intra-ordem e Pós-ordem.

     - Binary Search Tree (BST)

       - Para cada nó, os valores dos nós na subárvore à esquerda são menores e os valores na subárvore à direita são maiores.
       - Facilitam operações de busca, inserção e remoção.
       - Filas de Prioridades
         - É uma estrutura de dados que mantém uma coleção de elementos associados a prioridades.
         - Os elementos de maior prioridade são processados primeiro.
       - Implementações: B-Tree e variações.

     - Árvores Balanceadas

       - A diferença de altura entre as subárvores esquerda e direita de cada nó é limitada.
       - Exemplos incluem árvores AVL e árvores Rubro-negras.
       - Essa propriedade garante tempos de busca, inserção e remoção eficientes.

   - **Aplicações**

     - Priority queues.
     - Indexação de banco de dados com B-Tree and B+.
     - Compiler design.
     - Space partitioning.
     - Redes de computadores.

   - **Operações Específicas**

     - Traversal: Pre-order (Pré-ordem), In-order (Intra-ordem) and Post-order (Pós-ordem).
     - Height: conta-se o número de arestas do nó raiz até o nó folha mais distante.
     - Depth: conta-se o número de arestas do nó raiz até o nó atual.
     - Balancing: garante a menor altura e distribui os nós de forma uniforme.

3. Grafo (Graph)

   - **Características**

     - Possui vértices/nós e arestas finitos.
     - A ligação entre os nós forma um caminho.
     - Eccentricity: a distância máxima de um vértice a todos os outros vértices.
     - Ponto central do grafo: o vértice com menor excentricidade.
     - Raio: o valor mínimo de excentricidade de todos os vértices.

   - **Aplicações**

     - Representar o fluxo de computação.
     - Modelagem de sistemas, mapas e redes.
     - O sistema operacional usa grafo de alocação de recursos.
     - Páginas da Web representam os nós da Internet.

   - **Operações Específicas**

     - Add or remove a vertex or edge.
     - Depth-First Search (DFS): visitar vértices pela profundidade.
     - Breadth-First Search (BFS): visitar os vértices pela largura.
     - Shortest Path: usa-se o algoritmo de Dijkstra ou o algoritmo A\* para encontrar o caminho mais curto entre dois vértices.
     - Componentes conectados: conjuntos de vértices que estão conectados uns aos outros, mas não a quaisquer outros vértices no grafo.
     - Cycle Detection: verificar as arestas traseiras durante uma pesquisa em profundidade.
