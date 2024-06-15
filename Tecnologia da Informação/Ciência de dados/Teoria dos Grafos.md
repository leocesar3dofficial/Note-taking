# Teoria dos Grafos

## Definição
É uma estrutura que formaliza relações de interdependência existentes entre os elementos de um conjunto.

## História
- **1736, Problema das Sete Pontes de Königsberg, Leonhard Euler:**
  - Não seria possível passar por todas as pontes sem repetição.
  - Caminho euleriano: passar por cada aresta somente uma vez.
    - Vértices possuem grau par.
    - Semi-euleriano: grafo não cíclico.
      - Dois vértices com grau ímpar e os demais com grau par.

- **1859, William Rowan Hamilton:**
  - Caminho hamiltoniano: passar por cada vértice somente uma vez.
    - Semi-hamiltoniano: grafo não cíclico.
  - Jogo icosiano.

- **1878, foi cunhado o termo grafo.**
- **1930, Kazimierz Kuratowski:**
  - Definiu a condição para a planaridade do grafo, com arestas que não se cruzam.
- **1936, primeiro livro didático sobre grafos, Dénes König.**
- **1962, teoria dos fluxos em redes.**

## Elementos
- **Vértices ou nós**
- **Arestas ou arcos**

## Conceitos
Pode representar:
- Estrutura de uma molécula
- Rotas de transporte rodoviário
  - Problema do caixeiro-viajante ou TSP (Travelling Salesman Problem)
    - NP-Completo ou difícil de resolver
    - NP: classe de problemas que podem ser resolvidos em tempo polinomial
    - Métodos de solução
      - Exato (alto custo de tempo real de processamento)
      - Heurístico (aproximado)
        - Termina o processo em tempo hábil
      - Busca gulosa (aproximado)
        1. Sempre se escolhe a aresta de menor custo para atravessar.
        2. Sucessivamente até que todos os vértices tenham sido alcançados.
        3. Até a única opção seja retornar ao vértice origem.
- Redes de comunicação/computadores
- Redes de eletricidade e sua robustez
- Redes sociais
- Tubulações em geral
- Alocação de professores e disciplinas

**Ordem:** quantidade de vértices  
**Dimensão:** quantidade de arestas  
**Incidência:** conexão das pontas da aresta em um (forma um laço) ou dois vértices  
**Adjacência:** duas arestas conectadas a um mesmo vértice  
**Vizinhança:** conjunto de vértices adjacentes
  - **Fechada:** inclui o próprio vértice de referência

**Grau**
- Vértice: quantidade de arestas conectadas a ele
- Grafo: somatório do grau de todos os seus vértices ou o dobro do total de suas arestas (A*2)
  - Grau máximo: igual ao maior grau de um de seus vértices
  - Grau mínimo: igual ao menor grau de um de seus vértices

**Caminho ou passeio:** sequência de vértices conectados
- Cíclico ou ciclo: o caminho começa e termina no mesmo vértice
  - Simples ou elementar
  - Triângulo: tamanho igual a 3
- Tamanho: somatório das arestas do caminho
- Distância: menor tamanho entre dois vértices
- Excentricidade: distância máxima entre dois vértices
- Trajeto: caminho sem arestas repetidas
- Simples: caminho sem vértices repetidas
- Origem: primeiro vértice

**Isomorfo:** igualdade geométrica entre dois grafos
- Não existe um algoritmo eficiente para o problema geral do isomorfismo

**Subgrafo**
- Parcial
- Corte de vértices gera novos subconjuntos

## Tipos
**Rotulado**
- Vértices e arestas com rótulos

**Quanto a densidade**
- **Esparso:** bem abaixo de $ |A| < |V|^2 $
- **Denso:** próximo de $ |A| = |V|^2 $

**Simples**
- **Básico**
  - Não possui arestas paralelas: duas arestas conectadas aos mesmos vértices
  - Não possui laço: aresta com suas duas pontas ligadas ao mesmo vértice
- **Regular**
  - Vértices com o mesmo número de arestas conectadas
- **Completo**
  - Possui arestas entre todos os seus vértices
  - Kn, onde n é igual ao número de vértices do grafo
  - Todo grafo completo é um grafo regular
- **Complementar**
  - União de dois grafos que se tornam um grafo completo
- **Conexo**
  - Todos os vértices são conectados e são atravessáveis/atingíveis/alcançáveis
  - Caso contrário, se torna um grafo desconexo
    - Totalmente desconexo: todos os vértices possuem grau zero
- **Cíclico**
  - É possível caminhar de um vértice a vértices adjacentes até retornar à origem
- **Árvore**
  - Conexo e não cíclico
  - Folha: vértice com grau menor ou igual a um
    - Não possui filhos
  - Interior: vértice com grau maior que um
  - Nível: quantidade de vértices entre a raiz da árvore até o vértice de referência
  - Ancestral: pode ser pai
  - Descendente: pode ser filho
  - Irmãos: mesmo pai e mesmo nível
  - Altura da árvore: igual ao vértice de maior nível
- **Floresta**
  - União disjunta de árvores
  - Não conexo e não cíclico
- **Bipartido**
  - Pode ser separado em dois subconjuntos de vértices não conectados entre si
  - Pode ser completo entre os dois subconjuntos

**Complexo**
- **Pseudografo**
  - Possui laço
- **Multigrafo**
  - Possui uma ou mais arestas paralelas
- **Dígrafo, orientado ou direcionado**
  - Suas arestas possuem direção
  - Seus vértices possuem grau de entrada e saída
  - Fonte: vértice com grau nulo de entrada (só entrega)
  - Sumidouro: vértice com grau nulo de saída (só recebe)
  - Raiz: vértice que se conecta na direção de todos os outros vértices
  - Fortemente ou fracamente conexo
- **Ponderado ou valorado**
  - Suas arestas possuem pesos
  - Pode ser orientado
- **Nulo:** Kn = 0
- **Trivial:** Kn = 1

**Euleriano**

## Representação computacional
- **Lista de adjacências**
  - Uma lista para cada vértice
  - Em cada lista, tem-se outra lista com os vértices adjacentes
  - Em um grafo orientado ou dígrafo, as referências são diferentes
- **Matriz de adjacências**
  - Matriz que relaciona seus vértices por adjacência
  - Valor 0 para não adjacente e valor 1 para adjacente
  - Sua matriz é igual à sua transposta
  - Ideal para grafos densos
  - Em um grafo direcionado, a matriz não é igual à sua transposta
- **Matriz de incidências**
  - Matriz que relaciona a incidência entre vértices e arestas
  - Valor 0 para não incidente e valor 1 para incidente
  - Em um dígrafo: valor -1 para saída e 1 para entrada

## Algoritmos de busca
- Em profundidade
- Em largura
- Árvore Geradora Mínima
  - Minimum Spanning Tree (MST)
  - Gera grafos completos
  - Pode ser dirigido com custos/ponderado -> gerar o grafo de menor custo
    - Algoritmos: Kruskal, Prim, Dijkstra
    - Caminho mínimo: soma dos pesos nas arestas possui o menor valor

## Teoremas
**Cíclico**
- O grau de todo vértice é, pelo menos, dois

**Euleriano**
- O grau de todo vértice é par

**Ore**
- Um grafo que contém uma quantidade suficiente de arestas é hamiltoniano

**Dirac**
- É um grafo hamiltoniano se o grau de todo vértice é maior ou igual a n/2

**Whitney**
- Dois grafos são isomorfos (iguais) somente se a representação em grafo de suas arestas também são isomorfas

## Problemas em Grafos
**Clique**
- **Definição**
  - Subconjunto de vértices ou subgrafo, onde todos são conectados dois a dois
- **Emparelhamento máximo**
  - Contém o maior número de arestas possível
- **Maximal**
  - Conjunto de vértices adjacentes entre si não contidos em outra clique
  - Pode haver mais de um clique maximal

**Coberturas**
- Sobreposição de um grafo sobre outro
- Problema da cobertura de arestas mínima

**Planaridade:** arestas que não se cruzam
- **Teoremas**
  - Fórmula de Euler (1750)
  - Kuratowsk: condição para um grafo ser planar

**Coloração de vértices**
- Teorema 3: grafo conexo requer cores = n
- Brooks (1941)
- Quatro Cores, Appel e Haken
