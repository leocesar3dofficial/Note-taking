# Inteligência Artificial

## Definições

### Conceitos

- **Inteligência:** faculdade de compreender e abstrair
- Sistema digital, artefato ou equipamento
- Manifesta habilidades psíquicas ligadas ao ambiente em que está inserido
- **Discretização:** transformar valores de um atributo/instância numa escala de 0 a 1

### Estratégias

- Emular o pensamento humano
  - Tomada de decisões
  - Resolução de problemas
  - Aprendizado
- Emular o pensamento racional

### Contribuições da Ciência

- **Filosofia**
  - A utilização de regras formais apresenta conclusões válidas?
  - Como se dá o desenvolvimento intelectual em um cérebro biológico?
  - Qual a origem do conhecimento?
  - Como o conhecimento está vinculado às ações?
- **Matemática**
  - Quais as regras formais para a obtenção de conclusões válidas?
  - Quais dados podem ser computados?
  - Como se dá o raciocínio através de dados incertos?
- **Economia**
  - Teoria da utilidade
    - Grau de satisfação e rentabilidade obtidos das coisas
    - Fatores emocionais são levados em consideração
  - Teoria dos jogos
    - Agentes podem adotar aspectos aleatórios na busca por melhorar seus resultados
  - Processo de decisão de Markov
    - Tratamento de incertezas com base em estudos probabilísticos e na teoria da utilidade
  - **Neurociência**
    - Representação matemática do funcionamento do cérebro
  - **Psicologia**
    - Behaviorismo
  - **Engenharia de computadores**
    - Aumento contínuo do poder de processamento
    - Teste de Turing
      - Definir se o agente é inteligente
      - Quando um ser humano não consegue dizer se está conversando com uma máquina
      - Dada uma pergunta, a resposta foi feita por uma pessoa?
    - Teoria de controle e cibernética
      - Maximizar uma função objetivo em relação ao tempo
      - Métodos estocásticos
        - Distribuição de soluções associadas a uma probabilidade
        - Os objetos não possuem estado e origem determinados
        - Não tem um controle pleno dos objetos e variáveis
    - **Linguística**
      - Processamento de linguagem natural

## História

- 1943, conceito de neurônio artificial
- 1956, IA como disciplina acadêmica
- 1966, Programa ELIZA, MIT, Joseph Weizenbaum: algoritmo de PNL
- 1993, Deep Blue da IBM derrotou o então campeão mundial de xadrez Garry Kasparov

## Agentes

### Tipos

- **Reativo simples**
  - Lógica proposicional (tabela-verdade, verdadeiro ou falso)
  - Modelo do mundo (memória parcial)
- **Baseado em objetivos**
  - Regras e estados
- **Baseado em utilidade**
  - Atingir objetivos com geração de utilidade (felicidade)

### Tomada de decisões

- **Simples**
  - Redes de decisão ou diagrama de influência
    - Utiliza as redes bayesianas
    - Estruturas básicas
      - Nós de acaso
      - Nós de decisão
      - Nós de utilidade
      - Ligações (estabelecem o fluxo)
    - Etapas em cada nó
      - Definição das variáveis de evidência
      - Definir o custo baseado no valor de cada possível resultado
        - Sub-etapas
          - Definição do nó de decisão
          - Definir a probabilidade de cada valor
          - Retornar a ação com nível de utilidade mais elevado
- **Regressão logística**
  - Modelo estatístico para prever a probabilidade de um evento
  - Criado usando um algoritmo que estima os parâmetros do modelo
    - Os parâmetros do modelo são as relações entre as variáveis independentes e a variável dependente
  - Utiliza variáveis independentes categóricas e/ou numéricas para prever uma variável dependente lógica ou booleana
  - As variáveis independentes são usadas para estimar a probabilidade da variável dependente ocorrer
  - A variável dependente em um modelo de regressão logística é sempre uma variável lógica ou booleana
    - Pode assumir apenas dois valores: verdadeiro ou falso, 1 ou 0, sim ou não
- **Complexa**
  - Problemas de decisão sequenciais
  - Estratégia de recompensas
    - Aditivas (maior valor)
    - Descontada (menor valor)
    - Média (valor médio ou a mediana)

## Ambiente

- Estático, Semi-estático, Dinâmico
- Discreto, Contínuo
- Conhecido, Desconhecido
- Com um ou mais agentes

## Teoria de grafos

- Relacionamento (aresta) entre objetos (pontos, nós ou nodes)

### Tipos

- Máquina de estados (state machine)
  - Fluxo de dados condicional de uma origem (estado 1) até um destino (estado 2)
- Grafos de planejamento
  - Algoritmo com pontos de decisão
  - Baseado no planejamento proposicional
  - Grafo direcionado ou direcional
  - Apresenta estimativas sobre as saídas
  - Regras heurísticas, aproximadas, solução viável

## Incerteza (lógica propositiva e de primeira ordem)

- Algoritmo Naive Bayes ou redes bayesianas

### Algoritmo de classificação

- Ferramenta de aprendizagem supervisionada
- Objetivo: identificar categorias com dados de treinamento

### Teorias fundamentais

- Utilidade (Economia)
- Probabilidade (Estatística)
- Decisão (Árvore de Decisão)

### Características

- Baseado no Teorema de Bayes: calcular probabilidades condicionais
- Grafo com N vértices de estados probabilísticos ou mundo
- Escalável linearmente
- Útil para dados de alta dimensão e classificação de texto
- Dados fornecidos em forma tabelas de frequência
- Classifica a observação em várias classes (grupos, rótulos ou categorias)
- Saída
  - Binária (sim, não, verdadeiro, falso)
  - Multiclasse (mais de dois resultados)
  - Desbalanceada (Imbalanced Classification)

### Usos

- Detecção de outliers
- Investigação de fraudes
- Filtrar spam
- Classificação de texto
- Análise de sentimentos
- Sistemas de recomendação
- Linguagem natural

### Modelo oculto de Markov

- **Conceito**
  - Modelo temporal
  - Estender modelos estáticos em dinâmicos
  - Tratamento de estados (um estado ativo por vez)
  - Variável única, aleatória e discreta

### Elementos ou matriz tabular

- Variável do modelo de transição (coluna)
  - Manter o estado de todos os resultados possíveis
- Variável do modelo de sensores (linha)
  - Verificar o estado atual
- Variável de mensagens (célula)

  - Movimentação entre as possibilidades
  - Resposta para cada estado

  ## Aprendizado de máquina (Machine Learning)

  ### Técnicas

  #### Classificação

  - Usadas para categorizar dados em classes ou categorias distintas
  - Objetivo de atribuir um rótulo ou classe a um conjunto de características com base em padrões identificados nos dados
  - Algoritmos:
    - Árvores de Decisão
    - Naive Bayes
    - Support Vector Machines (SVM)
    - Redes Neurais
  - Casos de uso: Detecção de spam, diagnóstico médico e classificação de imagens

  #### Regressão

  - Usadas para prever valores numéricos com base em dados históricos
  - Buscam estabelecer relações entre variáveis independentes e dependentes para fazer previsões
  - Algoritmos:
    - Linear
    - Logística
    - Floresta Aleatória
  - Casos de uso: Previsão de preços, análise de tendências e previsões de séries temporais

  #### Agrupamento

  - Visam dividir um conjunto de dados em grupos ou clusters
  - Itens dentro de cada grupo são mais semelhantes entre si do que com os itens em outros grupos
  - Algoritmos:
    - K-Means
    - DBSCAN
    - Hierarchical Clustering
  - Casos de uso: Segmentação de clientes, análise de redes sociais e compressão de dados

  #### Redução de Dimensionalidade

  - Usada para reduzir a quantidade de recursos em um conjunto de dados, mantendo as informações essenciais
  - Ajuda a simplificar a análise de dados, economizar recursos computacionais e melhorar o desempenho dos modelos de aprendizado de máquina
  - Técnicas:
    - Análise de Componentes Principais (PCA)
    - Seleção de Recursos

  #### Associação

  - Usadas para descobrir relações frequentes ou regras de associação em conjuntos de dados
  - Algoritmo Apriori é um exemplo notável de técnica de associação
  - Aplicado a dados transacionais, como históricos de compras, para identificar padrões de compra de produtos relacionados

  #### Recomendação

  - Sistemas de recomendação são usados para prever ou sugerir itens de interesse para os usuários com base em seus históricos ou preferências
  - Abordagens de filtragem:
    - Colaborativa: baseia-se no comportamento de usuários semelhantes
    - Baseada em conteúdo: leva em consideração as características dos itens e as preferências do usuário
  - Casos de uso: Comércio eletrônico, serviços de streaming e redes sociais

### Métodos

#### Indutiva

- Inferir regras e teorias
- Criar hipóteses baseadas em uma amostra
- Aprendizagem por descoberta

#### Dedutiva

- De uma regra geral para uma nova regra específica/derivada

#### Por resposta/feedback

- Subtipos:
  - Supervisionado
    - Conceito:
      - Conjunto de entradas incertas (atributos previsores) gera uma saída desejada (atributos alvo ou meta)
      - Técnicas de agrupamento:
        - Agrupar dados que sejam semelhantes entre si
        - Não necessariamente fazem a previsão de um atributo alvo
  - Não supervisionado
    - Conceito:
      - Entradas dos dados não são plenamente conhecidas
      - Sem rótulos ou categorias predefinidas
      - Exploração de padrões intrínsecos
      - Uso de algoritmos de agrupamento
    - Algoritmos:
      - Expectation-Maximization (EM)
        - Conceito:
          - Cria deduções esporádicas com base nos dados
        - Etapas:
          1. Expectativa:
             - Gera hipótese/probabilidade/peso dos valores esperados
          2. Maximização (média das hipóteses):
             - Encontrar valores para os dados que maximizem sua probabilidade
             - Covariância entre os dados
      - K-means
        - Conceito:
          - Realiza um processo de aproximação entre os diferentes clusters
          - Aproximação euclidiana dos atributos de cada elemento
          - Distância euclidiana:
            - Uma dimensão = $\sqrt{(a - b)^2}$
            - Bidimensional = $\sqrt{(ax - bx)^2 + (ay - by)^2}$
      - Hierárquico

#### Por reforço

- Conceito:
  - O agente não conhece as entradas possíveis para se construir as hipóteses
  - Pesos (Weights): define o reforço
- Tipos:
  - Passivo
    - O agente possui conhecimento sobre como agir
  - Ativo
    - O agente aprende durante a execução da aplicação

## Aprendizado por Transferência (Transfer Learning)

### Conceito

- Treinamento de um modelo em uma tarefa e, em seguida, a reutilização desse modelo treinado como ponto de partida (ou ponto de partida pré-treinado) para resolver outra tarefa relacionada
- Conhecimento adquirido em uma tarefa pode ser transferido ou compartilhado com outras tarefas
- Acelera o processo de treinamento e melhora o desempenho em novas tarefas
- Útil em situações quando se tem um conjunto de dados limitado para a tarefa de interesse, mas há abundância de dados disponíveis para tarefas relacionadas
- Modelo pré-treinado, que já aprendeu representações úteis dos dados em uma tarefa anterior, pode ser ajustado (fine-tuning) para a nova tarefa com um conjunto de dados menor
- Economiza tempo e recursos de treinamento

### Técnicas

#### Fine-tuning

- Envolve ajustar os pesos e parâmetros de um modelo pré-treinado para a nova tarefa
- Usa um conjunto de dados menor e específico para a nova tarefa
- Pesos iniciais são inicializados com os valores aprendidos na tarefa anterior

#### Feature Extraction

- Modelo pré-treinado é usado apenas para extrair recursos (representações de dados) da camada intermediária
- São então alimentados em um novo modelo construído especificamente para a nova tarefa
- Esses recursos podem ser vetores de características úteis aprendidos pelo modelo pré-treinado

#### Modelo Híbrido

- Às vezes, as camadas intermediárias de um modelo pré-treinado são usadas como parte de um novo modelo, que é treinado em conjunto com camadas adicionais específicas da nova tarefa

### Etapas

1. Pré-processamento

- Aquisição dos dados
- Tratamento de dados

2. Treinamento e testes
3. Processamento

- Algoritmos:
  - K-nearest neighbors (k-nn)
    - Definição:
      - Verifica a similaridade entre vizinhos
      - Significado de K: quantidade de vizinhos a ser comparados
    - Aplicações:
      - Coloração de mapas
      - Identificar padrões em imagens
  - Árvore de decisão
    - Objetiva prever o valor de uma variável
    - Usa um conjunto de regras simples aprendidas
    - Estrutura hierárquica (relação pai/filho)
    - Constituída de elementos em camadas
  - Redes neurais
  - Naive Bayes (descrito em Incerteza)

4. Pós-processamento

- Validação dos resultados (qualidade)
  - Para algoritmos não supervisionados:
    - Índice Davies-Bouldin (DB):
      - Procura estimar a dispersão entre os dados
      - Calcular a diferença entre os clusters
    - Índice silhouette:
      - Média total da aproximação de todos os pontos em relação a todos os demais pontos de seus clusters
  - Matriz de confusão:
    - Avaliar o desempenho de um modelo de classificação a partir da frequência de erros e acertos
  - Medida de confiança de uma regra de associação:
    - Calculada pela porcentagem de transações que contêm o antecedente e o consequente da regra
    - Exemplo:
      - Se um cliente compra leite, então ele também compra pão" tem uma confiança de 0,66
      - Isso significa que 66% das transações que contêm leite também contêm pão
- Ajuste dos dados

## Processamento de Linguagem Natural (Natural Language Processing, NLP ou PLN)

### Definição

- Comunicação verbal e textual
- Fundamentada em regras gramaticais e dialetos

### Modelos

- N-grama
  - Definição:
    - Identificar a linguagem utilizada no input
    - Cadeia de Markov de ordem 1-N (N como o número de caracteres)
      - Não depende de estado anterior
      - Assume a forma de grafos
    - Gera uma árvore de dependência
  - Tipos: 1, 2 ou 3-grama (entradas com um, dois ou três caracteres)
- Redes Neurais Artificiais
  - Conceito:
    - Algoritmos de classificação supervisionadas para gerar respostas e realizar tarefas
  - Características:
    - Possuem camadas de tratamento para classificação dos objetos
    - Cada nodo possui um peso e desvio associados (weights and biases)
    - Não têm um modelo do mundo explícito
    - Usam seu conhecimento implícito dos padrões de linguagem e do mundo real

### Processo

- Classificação ou categorização dos dados (entradas ou inputs)

## Percepção

### Sensores

#### Funcionalidades

- Filtragem
  - Cálculos probabilísticos usados para representar conjuntos de hipóteses
- Previsão
  - Percepção de ocorrência de estados futuros
- Suavização
  - Realizar previsões com base em dados passados
- Explicação mais provável
  - Identificar padrões e gerar conclusões
- Aprendizagem
  - Aprender com eventos passados
