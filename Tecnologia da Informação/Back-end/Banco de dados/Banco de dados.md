# Banco de Dados

## Modelos

### Relacional

- **Características**

  - Utiliza uma estrutura tabular.
  - Os dados são organizados em tabelas compostas por linhas e colunas.
  - Tornou-se o padrão de fato para bancos de dados.
  - Oferece uma estrutura mais simples e intuitiva para organizar os dados.
  - Alterações na estrutura podem ser realizadas com menos impacto nos dados existentes.
  - É mais fácil de ser mantido e modificado.
  - Com suporte e implementação ampla em sistemas de gerenciamento de banco de dados (SGBDs).

- **Relacionamentos**

  - Relacionamentos são geralmente unidirecionais.
  - Tabelas têm chaves primárias e chaves estrangeiras para estabelecer relacionamentos entre elas.
  - Utiliza relacionamentos unidirecionais simples entre tabelas.
  - Segue o princípio da chave primária e chave estrangeira.
  - Associações muitos-para-muitos são tratadas por meio de tabelas de junção.

- **Acesso aos dados**

  - O acesso aos dados é realizado por meio de consultas SQL (Structured Query Language).
  - Consultas são expressas em uma linguagem declarativa.
  - Sistema de gerenciamento de banco de dados é responsável por otimizar a execução das consultas.
  - SQL é uma linguagem padronizada e adotada para consultas e manipulação de dados em sistemas relacionais.

#### Modelagem

Utiliza o DER (Diagrama de Entidade e Relacionamento).

1. Conceitual

O modelo de dados é criado a partir da visão geral do negócio. Define os objetos de dados e suas relações.

- **Cardinalidade**
  - **1 para 1 (um para um):**
    - Um único registro em uma entidade está associado a no máximo um registro em outra entidade, e vice-versa.
    - Exemplo:
      - Relação entre um estudante e seu número de identificação único.
      - Cada estudante tem apenas um número de identificação, e cada número de identificação está associado a apenas um estudante.
  - **1 para N (um para muitos):**
    - Um único registro em uma entidade pode estar associado a vários registros em outra entidade, mas cada registro nesta segunda entidade está associado a no máximo um registro na primeira entidade.
    - Exemplo:
      - Relação entre um departamento e funcionários.
      - Um departamento pode ter vários funcionários, mas cada funcionário pertence a apenas um departamento.
  - **N para M (muitos para muitos):**
    - Vários registros em uma entidade podem estar associados a vários registros em outra entidade.
    - É necessário introduzir uma tabela de associação (ou tabela de junção) que conecta as duas entidades.
    - Exemplo:
      - Relação entre estudantes e cursos.
      - Um estudante pode se inscrever em vários cursos, e um curso pode ter vários estudantes matriculados.

2. Lógica

- Tipos de dados, restrições e índices.
- Não considera os detalhes de implementação nos Sistemas de Bancos de Dados.

3. Física

- Qual gerenciador de Banco de Dados será utilizado.
- Parâmetros de configuração.
- Layout de armazenamento e o algoritmo de indexação.
- Leva em consideração os detalhes de implementação, como desempenho e integridade dos dados.

#### Modelos Entidade Relacionamento

1. UML (Unified Modeling Language)

- Notação gráfica utilizada para modelagem de sistemas de software.

- **Características**

  - Notação visual que usa símbolos gráficos para representar elementos.
    - Classes, objetos, relacionamentos, comportamentos, entre outros.
  - Orientada a objetos e utilizada no desenvolvimento de software.
    - Desde a análise, projeto até a documentação e comunicação entre as equipes.
  - Linguagem padronizada.
  - Possui uma ampla variedade de diagramas.
    - Diagramas de classes, sequência, atividades, entre outros.
  - Flexível e extensível.
    - Permite que os desenvolvedores criem diagramas específicos para diferentes domínios e necessidades.
  - Propriedades.
    - **Dependência:** mudanças na definição de um elemento (o fornecedor) podem causar mudanças ao outro (o cliente).

- **Diagramas Estruturais:**

  1. **Diagrama de Classes:**

  - Representa a estrutura estática do sistema, mostrando as classes, seus atributos, métodos e os relacionamentos entre elas.

  - **Elementos**

    - **Níveis de acesso**

      - '#' = protected / protegido.
      - <u>Sublinhado</u> = estático.
      - _Itálico_ = abstrato.

    - **Relacionamentos**

      - Subclasse (generalização): linha continua com a Ponta de flecha vazada (não preenchida).
      - Implementa Interface (realização): linha tracejada com a Ponta de flecha vazada.

  2. **Diagrama de Objetos:**

     - Detalha instâncias de classes e seus relacionamentos em um determinado momento durante a execução do sistema.

  3. **Diagrama de Componentes:**

     - Ilustra a estrutura física dos componentes de software e suas interações.

  4. **Diagrama de Implantação:**

     - Mostra a disposição física dos artefatos de software em nós (hardware) e suas interações.

- **Diagramas Comportamentais:**

  1. **Diagrama de Casos de Uso:**

     - Descreve as interações / associações / contexto entre atores (usuários externos) e o sistema, destacando os cenários de uso.

  2. **Diagrama de Sequência:**

     - Representa a ordem temporal das mensagens entre objetos durante uma interação.

  3. **Diagrama de Comunicação:**

     - Similar ao diagrama de sequência, mostra as interações entre objetos, mas enfatiza as associações entre eles.

  4. **Diagrama de Máquina de Estados:**

     - Modela o comportamento de um objeto em termos de estados que ele pode assumir e transições entre esses estados.

  5. **Diagrama de Atividades:**

     - Descreve o fluxo de atividades, incluindo a sequência de ações e decisões.

     - **Elementos**

       - Início: bola cheia.
       - Fim: bola no interior de um círculo.
       - Condição de guarda:
         - Precisa ser satisfeita para permitir que uma transição associada seja ativada.
         - Expressão booleana entre colchetes. Ex. [sim], [não].

2. IDEF (Integrated Definition Language)

- Família de linguagens de modelagem utilizadas para representar sistemas complexos.
- Abrange tanto aspectos técnicos quanto gerenciais.
- Usado principalmente para modelar sistemas físicos, industriais e de negócios.
- Possui várias versões, como IDEF0, IDEF1X, IDEF3, IDEF4, entre outros, cada um com um propósito específico de modelagem.
- Enfatiza a representação detalhada de processos, fluxos de trabalho, informações, dados e recursos em um sistema.
- Mais textual, baseada em notações gráficas, como fluxogramas e diagramas de contexto.

- **UML vs IDEF**

  - São duas abordagens diferentes para modelagem e representação de sistemas.
  - Possuem propósitos semelhantes.

  - **Diferenças**

    - UML: ênfase na orientação a objetos, IDEF: ênfase em processos, fluxos de trabalho e informações.
    - Ambas as notações têm suas próprias vantagens e são aplicáveis em diferentes contextos de modelagem de sistemas.
    - A escolha entre UML e IDEF dependerá das necessidades específicas do sistema e do domínio em questão.

3. Notação IDEF1X

- É uma das variantes da família de linguagens IDEF.
- Usada para modelar esquemas conceituais de banco de dados.
  - **Modelagem Conceitual**
    - Modelar a estrutura conceitual de um banco de dados.
    - Capturando as entidades, atributos e relacionamentos.
    - É independente do Sistema de Gerenciamento de Banco de Dados (SGBD).
  - **Ênfase nos Relacionamentos**
    - Suporta relacionamentos binários (1:1, 1:N, N:M).
    - Permite a definição de restrições e cardinalidades específicas.
  - **Diagramas de Entidade-Relacionamento (DER)**
    - Visualizar as estruturas de dados.
      - Caixas retangulares para representar as entidades.
      - Linhas para denotar os relacionamentos.
      - Símbolos para indicar a cardinalidade e a participação dos elementos.
    - **Elementos básicos:** Entidades, Atributos e Relacionamentos.
  - **Atributos Multivalorados e Compostos**
    - Permite a modelagem de estruturas de dados mais complexas.
  - **Herança e Generalização/Especialização**
    - Permite a modelagem de herança e a criação de hierarquias de entidades.
    - Representar estruturas de dados onde as entidades compartilham características comuns.
  - **Legibilidade e Clareza**
    - Projetada para ser legível e de fácil compreensão.
    - Os diagramas são organizados de forma lógica.
      - Utilizam símbolos e convenções claras para facilitar a interpretação.
  - **Suporte à Documentação**
    - Usado para documentar os requisitos de um sistema de banco de dados.
    - Fornece uma visão estruturada das entidades e seus relacionamentos.
  - **Independência de Plataforma**
    - É independente de plataforma.
    - Pode ser implementada usando várias ferramentas disponíveis.

#### Álgebra Relacional

- **Características**

  - Proporciona uma abordagem matemática precisa para a manipulação de dados.
  - Permite a expressão de consultas de forma concisa e eficiente.
  - Essencial para a compreensão dos fundamentos dos bancos de dados relacionais.
  - Utilizada na concepção, implementação e otimização de consultas.
  - É uma linguagem formal utilizada para descrever operações e consultas em bancos de dados relacionais.
  - É uma linguagem teórica e serve de base para a linguagem SQL.
  - Fornece um conjunto de operadores para manipulação e combinação de relações.
    - São estruturas de dados tabulares.
    - Permite a combinação e aplicação sequencial de operadores para realizar consultas complexas.

- **Operadores**

  - **Básicos**
    - **Seleção (σ):** Seleciona as tuplas que atendem a uma determinada condição.
    - **Projeção (π):** Seleciona colunas específicas de uma relação, descartando as demais colunas.
    - **União (∪):** Combina duas relações compatíveis verticalmente, excluindo duplicatas.
    - **Interseção (∩):** Retorna as tuplas comuns entre duas relações.
    - **Diferença (-):** Retorna as tuplas presentes em uma relação, mas ausentes em outra.
  - **De Junção**
    - **Junção Natural (⨝):** Combina duas relações com base em atributos comuns.
    - **Junção Theta (⨝θ):** Combina duas relações com base em uma condição específica.
    - **Junção Externa (⨝⨃):** Combina duas relações, incluindo as tuplas não correspondentes.
  - **De Agregação**
    - **Agregação (γ):** Realiza operações de agregação, como soma, média, contagem, mínimo e máximo, em um grupo de tuplas.
  - **De Renomeação**
    - **Renomeação (ρ):** Renomeia atributos ou relações para facilitar a clareza e evitar conflitos de nome.

#### Normalização

- **Características**

  - Envolve identificar as dependências funcionais entre os atributos de uma tabela.
  - Divide a tabela em várias tabelas menores, se necessário, para eliminar dependências indesejadas.
  - Facilita a manutenção dos dados.
  - Possibilita um melhor desempenho nas operações de consulta e atualização.
  - Baseada em uma série de regras e formas normais.
    - Ajudam a estruturar as tabelas e seus relacionamentos de forma otimizada.

- **Finalidades**

  - Evitar e reduzir a redundância de dados.
  - Garantir a consistência, integridade e a eficiência dos dados.

- **Formas Normais Comuns**

  - **Primeira Forma Normal (1NF)**
    - Cada atributo de uma tabela deve conter um único valor atômico.
    - Não deve haver repetição de grupos de valores em um mesmo atributo.
    - Não deve possuir valores de atributos que sejam multivalorados ou compostos.
  - **Segunda Forma Normal (2NF)**
    - Uma tabela já deve estar na 1NF.
    - Todos os atributos não chave devem depender totalmente da chave primária.
    - Ausência de dependências parciais, onde um atributo depende apenas de uma parte da chave primária.
  - **Terceira Forma Normal (3NF)**
    - Uma tabela já deve estar na 2NF.
    - Todos os atributos não chave devem ser dependentes apenas da chave primária.
    - Ausência de dependências transitivas, onde um atributo depende de outro atributo não chave.
  - **Boyce-Codd**
    - Uma tabela já deve estar na 3NF.
    - Todo atributo não chave precisa depender funcionalmente diretamente da chave, seja ela primária ou candidata.
    - Ausência de dependências entre os atributos não chave.
    - Elimina toda redundância que pode ser descoberta com base nas dependências funcionais, porém, podendo restar outros tipos de redundância.
  - **Quarta Forma Normal (4NF)**
    - Ausência de dependências multivaloradas.
  - **Quinta Forma Normal (5NF)**
    - Ausência de dependências de junção.

### Em Rede

- **História**

  - Desenvolvido na década de 1960.
  - Foi utilizado nas décadas de 1960 e 1970.
  - Com o surgimento do modelo relacional e a padronização do SQL, sua popularidade diminuiu significativamente.

- **Características**

  - Utiliza uma estrutura hierárquica.
  - Os dados são organizados em uma coleção chamada conjuntos de registros.

- **Flexibilidade**

  - Permite a representação de estruturas de dados mais flexíveis.
  - Oferece flexibilidade ao permitir a criação de relacionamentos complexos entre os dados.
  - Essa flexibilidade pode tornar a manutenção e a modificação da estrutura de dados mais complexas.

- **Acesso aos dados**

  - O acesso aos dados é feito por meio de um sistema de ponteiros.
  - Um registro pode ser acessado diretamente por meio de seu ponteiro.
  - Isso permite um acesso rápido aos dados, mas pode ser mais complexo de ser implementado e gerenciado.

- **Relacionamentos**

  - Os conjuntos de registros são conectados por meio de relacionamentos chamados conjuntos de pais/filhos.
  - Permite a criação de relacionamentos complexos entre os conjuntos de registros.
  - Inclui relacionamentos muitos-para-muitos e hierarquias complexas.
  - Registros podem ter múltiplos pais e filhos.

### Hierárquico

- **História**

  - Um dos primeiros modelos de banco de dados a ser desenvolvido.
  - Utilizado nas décadas de 1960 e 1970.
  - Embora tenha sido substituído pelo modelo relacional e outros modelos mais modernos.
  - Ainda existem sistemas legados que utilizam essa abordagem.

- **Características**

  - Dados são organizados em uma estrutura de árvore.
  - Cada registro é conectado a um registro pai e pode ter um ou mais registros filhos.
  - Estrutura semelhante a uma hierarquia.
  - Registros são organizados em níveis, começando por um registro raiz e avançando para os registros filhos.

- **Pontos fracos**

  - Possui limitações em relação aos modelos em rede e relacional.
  - Dificuldade de lidar com relacionamentos muitos-para-muitos.
  - Rigidez da estrutura hierárquica.
  - Modificação e manutenção dos dados são mais complexas.

### Distribuído

- **Características**

  - Sistema de banco de dados.
  - Dados são armazenados e gerenciados em múltiplos nós ou servidores interconectados.
  - Cada nó contém uma parte dos dados.
  - Nós são capazes de processar consultas e realizar transações de forma independente.
  - Pode ser implementado em diferentes arquiteturas e infraestruturas de rede, como redes locais ou redes de longa distância.
  - Não é equivalente à computação em nuvem.
  - Não está restrito à computação em nuvem.
  - Pode ser implementado em uma infraestrutura local, rede privada ou em uma combinação de recursos locais e em nuvem.

- **Objetivos**

  - Melhorar o desempenho.
  - Aumentar a disponibilidade.
  - Permitir a escalabilidade.
  - Fornecer tolerância a falhas.

### Orientado a Objetos (NoSQL)

- **Características**

  - Abordagem alternativa ao modelo relacional.
  - Projetada para lidar com requisitos específicos de aplicativos modernos, como escalabilidade, flexibilidade e armazenamento eficiente de dados não estruturados.

#### Estruturas e Abordagens

- **Orientado a Documento (MongoDB)**

  - Dados são armazenados em documentos no formato JSON ou BSON (Binary JSON).
  - Análogo a uma linha em uma tabela de banco de dados relacional.
  - Cada documento pode ter uma estrutura flexível.
  - Documentos podem ser agrupados em coleções, permitindo consultas rápidas e eficientes.

- **Chave-Valor (Redis)**

  - Dados são armazenados em pares de chave-valor simples.
  - Cada valor é associado a uma chave única.
  - Permite a recuperação rápida dos dados.
  - Extremamente eficiente em termos de desempenho e escalabilidade.
  - Oferece pouca ou nenhuma estruturação ou consulta avançada dos dados.

- **Grafo (Neo4j)**

  - Dados são representados como nós e arestas.
  - Nós representam entidades e as arestas representam relacionamentos entre essas entidades.
  - Especialmente adequado para representar e consultar relacionamentos complexos.
  - Permite consultas eficientes e expressivas em estruturas de dados altamente conectadas.

- **Colunar (Cassandra)**

  - Dados são armazenados em colunas, em vez de linhas como no modelo relacional.
  - Permite uma compressão eficiente dos dados e consultas mais rápidas em conjuntos específicos de colunas.
  - Especialmente adequado para análises de alto desempenho.

- **Time Series**

  - Projetado especificamente para armazenar e consultar dados associados a carimbos de data e hora (timestamp).
  - Fornece recursos avançados para trabalhar com dados temporais, como agregação, interpolação, filtragem e análise de tendências.

  - **Implementações**

    - **InfluxDB:**

      - Código aberto e escalável.
      - Projetado para alta ingestão e consultas rápidas em dados de séries temporais.

    - **TimescaleDB:**

      - Extensão do PostgreSQL.
      - Adiciona recursos otimizados para armazenamento e consulta de dados de séries temporais.

    - **OpenTSDB:**

      - Banco de dados distribuído e escalável para dados de séries temporais.
      - Projetado para integração com o Hadoop.
      - Usado em grande escala para monitoramento e análise de dados.

    - **Prometheus:**

      - Coleta e armazenamento de métricas de monitoramento.
      - Utilizado para monitorar sistemas e serviços.

    - **Graphite:**

      - Plataforma de armazenamento e visualização de dados de séries temporais.
      - Permite a coleta de métricas de séries temporais.
      - Fornece uma interface para consulta e visualização desses dados.

## Conhecimento de SGBD (Sistema de Gerenciamento de Banco de Dados)

### Características

#### Controle de acesso

- Conjunto de mecanismos e políticas utilizados para controlar o acesso aos dados.
- Permite definir permissões e restrições para diferentes usuários ou grupos de usuários.
- Determina quais operações eles podem realizar (por exemplo, leitura, gravação, exclusão).

#### Usuário

- Representa uma entidade ou identidade associada ao banco de dados.
- Os usuários podem ser autenticados e autorizados com base em suas credenciais.
- Os privilégios e permissões de um usuário determinam quais ações ele pode executar no banco de dados.

#### Cálculo volumétrico

- Refere-se à capacidade do SGBD de gerenciar e calcular o tamanho ocupado pelos dados armazenados no banco de dados.
- Útil para monitorar o uso do espaço em disco, planejar a capacidade e otimizar o desempenho do banco de dados.

#### Replicação

- Processo de criar e manter cópias idênticas dos dados em diferentes locais ou servidores.
- Usada para melhorar a disponibilidade, escalabilidade e desempenho do banco de dados.
- Permite que os dados sejam acessados localmente em diferentes partes de um sistema distribuído.

#### Cluster

- Grupo de servidores ou nós interconectados que trabalham juntos como um único sistema.
  - Possui alta disponibilidade, escalabilidade e tolerância a falhas.
- Garante a continuidade dos serviços e a distribuição de cargas de trabalho entre os nós.

#### Particionamento

- Técnica de dividir uma tabela grande em partes menores chamadas partições.
- Com base em determinados critérios (por exemplo, intervalo de valores, chave de particionamento).
- Melhora o desempenho.
- Permite que as consultas acessem apenas as partições relevantes.
- Distribui os dados em diferentes unidades de armazenamento.
  - Não garante a disponibilidade do banco de dados.

#### Esquemas

- Estrutura lógica e organização dos objetos de banco de dados, como tabelas, índices e visões.
- Define a forma como os objetos são agrupados e relacionados entre si.
- Fornece uma visão organizada e coerente dos dados.
- Fornecem controle de acesso e segurança granular.
- Determina quem pode visualizar e modificar os objetos de banco de dados.

#### Controle de Concorrência

- Garante que múltiplas transações possam ser executadas simultaneamente sem causar inconsistências nos dados.
  - Isolamento de Transações.
    - Define o nível de isolamento entre transações concorrentes para evitar problemas como leituras sujas e inconsistências.
  - Bloqueio.
    - Utiliza bloqueios para evitar conflitos entre transações concorrentes ao acessar os mesmos dados
  - Controle de Conflitos.
    - Gerencia e resolve conflitos quando duas ou mais transações tentam modificar os mesmos dados simultaneamente.

#### Otimização de Consultas

- Aprimora o desempenho das consultas executadas em um banco de dados.
  - **Plano de Execução**
    - Determina a melhor estratégia para executar uma consulta, otimizando o tempo de resposta e utilização dos recursos.
  - **Índices**
    - Cria e gerencia índices para acelerar a busca e recuperação de dados, reduzindo o tempo de execução das consultas.
  - **Estatísticas e Análise**
    - Coleta informações sobre os dados e o uso das consultas para realizar ajustes e otimizações adicionais.
  - **Cache**
    - Armazena em cache os resultados de consultas frequentes para evitar a necessidade de executá-las repetidamente.
  - **Refatoração de Consultas**
    - Reescreve consultas para melhorar a eficiência, eliminando operações desnecessárias e simplificando a lógica.
  - **Buffer**
    - Busca dados do armazenamento de disco para a memória principal.

### Características de banco de dados massivos (Big Data)

- Projetado para lidar com grandes volumes de dados, variedade de tipos de dados e velocidade de processamento.
- Escalabilidade horizontal.
  - Capacidade de dimensionar horizontalmente.
  - Distribui os dados e a carga de trabalho em vários servidores ou nós.
  - Lida com grandes volumes de dados.
  - Suporte a cargas de trabalho intensivas.
- Processamento distribuído.
  - Projetado para executar operações em paralelo.
  - Distribui o processamento entre vários nós.
  - Isso permite um processamento mais rápido e eficiente de consultas e análises de dados.
- Armazenamento distribuído.
  - Os dados são armazenados em clusters distribuídos.
  - Cada nó contém parte dos dados.
  - Permite uma distribuição eficiente de dados em grande escala.
  - Capacidade de expansão conforme necessário.
- Processamento de dados em tempo real.
  - Ingestão e processamento de dados em tempo real.
  - Permite a análise de dados em tempo real e a tomada de decisões em tempo hábil.
- Suporte a dados não estruturados.
  - Além de dados estruturados, como tabelas e colunas.
  - É capaz de lidar com dados semiestruturados e não estruturados.
    - Como texto, imagens, áudio e vídeo.
- Tolerância a falhas.
  - Permite a recuperação rápida e eficiente de falhas em nós individuais ou em todo o sistema.
- Integração com ferramentas de Big Data.
  - Permitindo a integração e o processamento de dados em diferentes plataformas e tecnologias.
  - Compatível com ecossistemas de Big Data.
    - Como Hadoop, Spark e sistemas de armazenamento em nuvem.
- Análise avançada de dados.
  - Mineração de dados, aprendizado de máquina e análise preditiva.
  - Permite a descoberta de insights valiosos e a tomada de decisões baseadas em dados.
- Integração de dados heterogêneos.
  - Integra dados provenientes de várias fontes e formatos diferentes.
  - Permite a criação de uma visão unificada dos dados em uma organização.
- Privacidade e segurança.
  - Projetado para garantir a privacidade e a segurança dos dados sensíveis.
  - Implementa recursos de autenticação, autorização e criptografia.

## Produtos

### Oracle

#### Características

- Comercial de alto desempenho.
- Utilizado em grandes empresas e aplicações críticas.
- Recursos avançados.
  - Suporte a clustering.
  - Particionamento.
  - Recuperação de desastres.
- Suporte a várias plataformas, incluindo Linux, Windows e Unix.

#### Vantagens

- Escalabilidade.
- Desempenho excepcional para grandes volumes de dados e cargas de trabalho complexas.
- Recursos avançados de segurança, como criptografia, auditoria e controle de acesso granular.
- Ferramentas e ecossistema robusto, com suporte técnico amplo e documentação abrangente.

#### Desvantagens

- Licenciamento e custo associados podem ser mais altos em comparação com outras opções de código aberto.
- Requer habilidades especializadas para administração e otimização de desempenho.
- Pode ser considerado excessivo para pequenas e médias empresas com necessidades mais simples.

#### Tabela temporária

- **Características**

  - Criada, em tempo de execução, para armazenar dados temporários específicos de uma sessão.
  - Existe apenas durante a duração de uma sessão específica.
    - Permite operações independentes em cada sessão sem afetar outras sessões.
    - Cada sessão tem sua própria instância isolada da tabela temporária.
  - Útil para armazenar dados temporários ou intermediários que são usados em consultas complexas ou processos de negócios.
  - Ao criar uma tabela temporária.
    - É possível definir índices em tabelas temporárias para otimizar o desempenho de consultas.
    - Alocação de espaço em disco temporário para armazenar os dados da tabela.
    - Podem haver operações de E/S adicionais em comparação com tabelas permanentes.
    - Cada sessão que usa a tabela temporária tem sua própria instância isolada dessa tabela.
    - Cada sessão pode inserir, atualizar ou excluir dados na tabela temporária sem afetar as outras sessões.
  - É necessário cuidado ao usar tabelas temporárias em operações distribuídas.
    - Cada nó de processamento terá sua própria instância da tabela temporária.
  - Existem opções para controlar a visibilidade e o escopo dos dados em tabelas temporárias.

    - Opção "ON COMMIT DELETE ROWS" para tabelas globais temporárias, que remove os dados da tabela após cada transação.

  - **Tipos**

  - Tabelas globais temporárias.
    - São criadas uma vez e podem ser usadas por várias sessões simultaneamente.
    - Cada sessão tem acesso aos seus próprios dados específicos na tabela global temporária.
    - Os dados são visíveis somente para a sessão que os insere, atualiza ou exclui.
  - Tabelas locais temporárias.
    - São criadas para uma sessão específica e são destruídas automaticamente quando a sessão é encerrada.
    - Cada sessão tem acesso exclusivo aos seus próprios dados na tabela local temporária.
    - São úteis para armazenar dados temporários específicos de uma sessão sem interferir em outras sessões.

### PostgreSQL

#### Características

- Código aberto, conhecido por sua confiabilidade, integridade e conformidade com padrões SQL.
- Recursos avançados.
  - Suporte a dados geoespaciais.
  - Indexação avançada.
  - Replicação.
- Comunidade ativa de desenvolvedores.
- Ampla gama de extensões e complementos.

#### Vantagens

- Alta conformidade com padrões SQL, o que facilita a portabilidade de aplicativos entre diferentes bancos de dados.
- Excelente desempenho para consultas complexas e manipulação de grandes volumes de dados.
- Licença de código aberto permite custos mais baixos e flexibilidade na customização.

#### Desvantagens

- Recursos de escalabilidade horizontal (cluster) são menos desenvolvidos em comparação com algumas outras opções.
- O suporte técnico comercial pode ser limitado em comparação com SGBDs comerciais.

#### PostGIS

- Extensão espacial do PostgreSQL.
- Gratuita e de código fonte livre.
- Permite o uso de objetos GIS (Sistemas de Informação Geográfica) ser armazenado em banco de dados.
- Possui suporte para índices espaciais GiST e R-Tree.

### SQL Server

#### Características

- Desenvolvido pela Microsoft, com foco em integração com o ecossistema Microsoft e suporte a recursos empresariais.
- Oferece integração com ferramentas e tecnologias como .NET Framework e Active Directory.
- Recursos avançados.
  - Replicação.
  - Alta disponibilidade.
  - Integração com serviços de análise de dados.

#### Vantagens

- Integração com ferramentas e tecnologias Microsoft, facilitando o desenvolvimento de aplicativos no ecossistema Microsoft.
- Boa usabilidade e interface gráfica amigável para administração e desenvolvimento.
- Suporte técnico robusto e ampla adoção em ambientes empresariais.

#### Desvantagens

- Pode ter um custo inicial mais alto em comparação com SGBDs de código aberto.
- Menor portabilidade devido à ênfase na integração com tecnologias Microsoft.
- Recursos avançados podem exigir versões e licenças mais caras.

#### Foreign key constraints

- Opções para ON DELETE e ON UPDATE.
  - CASCADE, NO ACTION, SET DEFAULT e SET NULL.

### MySQL

#### Características

- Código aberto, utilizado em aplicações web e móveis.
- Possui uma arquitetura leve e de baixo consumo de recursos.
- Suporta a linguagem SQL padrão e oferece.
  - Recursos avançados.
    - Replicação.
    - Clustering.
    - Particionamento.

#### Vantagens

- Código aberto, o que permite maior flexibilidade e custos mais baixos em termos de licenciamento.
- Desempenho rápido e eficiente, especialmente para cargas de trabalho de leitura intensiva.
- Grande comunidade de usuários e desenvolvedores, com abundância de recursos e suporte disponíveis.

#### Desvantagens

- Alguns recursos avançados podem estar ausentes em comparação com SGBDs comerciais.
  - Índices FULLTEXT podem ser aplicados somente para tabelas InnoDB e MyISAM.
- Escalabilidade vertical (acréscimo de recursos em um único servidor) pode ter limitações em comparação com opções escaláveis horizontalmente.
- Suporte técnico comercial pode ser limitado em comparação com SGBDs comerciais.
- Índices FULLTEXT podem ser aplicados somente para tabelas InnoDB e MyISAM.

## Conceitos e Propriedades das Transações (ACID)

### Características

- As transações em bancos de dados seguem o conjunto de propriedades conhecidas como ACID.
- Garantem a confiabilidade, consistência e integridade dos dados.

### Propriedades

#### Atomicidade (Atomicity)

- Uma transação é tratada como uma unidade indivisível de trabalho.
- É executada como uma operação completa.
- Todas as alterações são aplicadas com sucesso ou nenhuma alteração é feita.
- Em caso de falha, todas as alterações até esse ponto são desfeitas (rollback).
- Garante que o banco de dados volte ao estado inicial.

#### Consistência (Consistency)

- Garante que uma transação leve o banco de dados de um estado válido para outro estado válido.
- As regras e restrições do banco de dados devem ser mantidas durante toda a transação.
- Violando a consistência, todas as alterações são desfeitas (rollback), mantendo a integridade dos dados.

#### Isolamento (Isolation)

- Garante que cada transação seja executada de forma isolada.
- Cada transação não é afetada por outras transações concorrentes.
- Cada transação parece estar sendo executada em um ambiente isolado, evitando problemas como leituras sujas, leituras não repetíveis e escritas fantasmas.

#### Durabilidade (Durability)

- Garante que, uma vez confirmada (commit), uma transação tenha alterações permanentes.
- As alterações são armazenadas permanentemente, mesmo em caso de falha do sistema.
- Geralmente alcançado por meio de técnicas como registros de log e confirmação de gravação em disco.

## Linguagem SQL (Padrão ANSI) e PL/SQL

### Consultas

- Comandos para recuperar dados de um banco de dados.
- Realizam operações de leitura, como seleção (SELECT), filtragem, ordenação e agregação de dados.

### Subconsultas

- Consultas aninhadas dentro de outras consultas.
- Fornecem dados de uma consulta interna executada antes da consulta externa.

### Triggers

- Procedimentos armazenados disparados automaticamente em resposta a eventos específicos no banco de dados.
- Podem executar ações como inserção, atualização ou exclusão de dados em tabelas relacionadas.

### Views

- Consultas armazenadas tratadas como tabelas virtuais.
- Permitem acessar e manipular dados de várias tabelas ou consultas complexas como se fossem tabelas individuais.

### Functions

- Blocos de código reutilizáveis que retornam um valor específico quando chamados.
- Usados em consultas SQL para cálculos, manipulação de strings ou lógica personalizada.

### Stored Procedures

- Conjuntos de comandos SQL armazenados no banco de dados como objetos.
- Chamados e executados posteriormente para realizar tarefas complexas, como manipulação de dados, validações e lógica de negócios.

### Packages

- Objetos de banco de dados que agrupam procedures, functions, tipos de dados e outras construções relacionadas.
- Oferecem uma maneira organizada e modular de gerenciar e encapsular a lógica do programa no banco de dados.
- Recurso disponível em: Oracle, Microsoft SQL Server e PostgreSQL.

### Tratamento de Erros

- Capacidade de lidar com exceções e erros durante a execução de comandos SQL ou PL/SQL.
- Permite capturar e tratar erros de forma controlada, definindo ações específicas em caso de erros.

### Cursores

- Estruturas de controle para manipular conjuntos de resultados retornados por consultas SQL.
- Permitem navegar, recuperar e processar registros um por um em uma consulta.

### Arrays

- Também conhecidos como vetores, são estruturas de dados para armazenar e manipular múltiplos valores em uma única variável.
- Frequentemente usados em PL/SQL para trabalhar com coleções de dados.

## Ferramenta de Migração Flyway

### Características

- **Controle de Versão:** Permite controlar as alterações de esquema do banco de dados através de scripts SQL versionados.
- **Migrações Automáticas:** Executa automaticamente as migrações de banco de dados durante o processo de inicialização do aplicativo.
- **Suporte a Várias Fontes de Scripts:** Suporta arquivos SQL, arquivos de texto puro, scripts Java, Jython e Groovy.
- **Controle de Transações:** Executa cada migração dentro de uma transação, garantindo reversão (rollback) em caso de erro.
- **Integração com Ferramentas de Build:** Pode ser integrado a ferramentas como Maven, Gradle e Ant.
- **Suporte a Vários Bancos de Dados:** Compatível com MySQL, PostgreSQL, Oracle, SQL Server e outros.
- **Extensibilidade:** Permite o uso de plugins e extensões personalizadas.

## Conceitos de Business Intelligence

### Data Warehouse

#### Características

- Repositório centralizado.
- Armazena dados históricos estruturados e integrados de várias fontes.
- Fornece uma base para relatórios, análises e tomada de decisões.

#### Tipos de Modelagem Dimensional

1. **Star Schema**

- Os dados são organizados em torno de uma tabela de fatos central.
- Conectada a várias tabelas de dimensão.
- Estrutura simples e denormalizada.
- Todas as dimensões são conectadas diretamente à tabela de fatos.

2. **Snowflake Schema**

- Estende o conceito do Star Schema.
- Dimensões normalizadas.
- Tabelas de dimensão divididas em várias tabelas relacionadas.
- Estrutura em forma de floco de neve.
- Reduz a redundância de dados, mas pode tornar as consultas mais complexas.

3. **Fact Constellation**

- Várias tabelas de fatos conectadas por tabelas de dimensão compartilhadas.
- Cada tabela de fatos representa um conjunto diferente de medidas e está relacionada a um conjunto específico de dimensões.
- Útil quando há múltiplos processos de negócios ou áreas temáticas distintas a serem analisados.

### Data Mart

- Subconjunto de um data warehouse.
- Focado em uma área ou departamento de negócios específico.
- Contém um subconjunto de dados adaptados às necessidades de um grupo de usuários específico.

### Data Mining

#### Características

- Processo de descoberta de padrões, relacionamentos e insights a partir de grandes conjuntos de dados.
- Envolve o uso de algoritmos e técnicas estatísticas para descobrir padrões ocultos e fazer previsões.

#### Metodologia CRISP-DM (Cross Industry Standard Process for Data Mining)

- **Definição**

  - Modelo de processo de mineração de dados.
  - Descreve abordagens comumente usadas por especialistas em mineração de dados para atacar problemas.

- **Características**

  - Foco no Negócio.
    - Garante que a mineração de dados seja direcionada para entregar valor e insights relevantes.
    - Enfatiza a compreensão dos objetivos e requisitos do negócio.
  - Orientação para Resultados.
    - Objetivo final é fornecer soluções acionáveis que agreguem valor ao negócio.
    - Auxilia na tomada de decisões informadas.
  - Abordagem Iterativa.
    - Divide o projeto em fases revisáveis e refináveis conforme necessário.
  - Flexibilidade.
    - Pode ser adaptada para atender às necessidades específicas de cada projeto.
  - Composta por fases que cobrem todo o ciclo de vida do projeto.
    1. Fase de Entendimento do Negócio.
       - Compreender os objetivos de negócio, requisitos e recursos disponíveis.
    2. Fase de Entendimento dos Dados.
       - Realizar a coleta, exploração e descrição dos dados disponíveis.
    3. Fase de Preparação dos Dados.
       - Realizar atividades de limpeza, transformação e formatação dos dados para prepará-los para a modelagem.
    4. Fase de Modelagem.
       - Desenvolver e avaliar diferentes modelos de mineração de dados.
       - Utiliza técnicas e algoritmos adequados.
    5. Fase de Avaliação.
       - Avaliar e validar os modelos de mineração de dados criados.
       - Garante que eles atendam aos objetivos do projeto.
    6. Fase de Implantação.
       - Implementar os resultados da mineração de dados no ambiente de produção.
       - Criação de relatórios e suporte ao uso prático dos resultados.

#### Técnicas Estatísticas e Algoritmos

- **Regressão Linear**
  - Método estatístico que busca estabelecer uma relação linear entre uma variável dependente e uma ou mais variáveis independentes.
- **Regressão Logística**
  - Técnica estatística utilizada para modelar a relação entre uma variável dependente binária e uma ou mais variáveis independentes.
- **Árvores de Decisão**
  - Estrutura de árvore que representa decisões e suas possíveis consequências, usada para classificação ou regressão.
- **Florestas Aleatórias**
  - Conjunto de árvores de decisão independentes combinadas para fornecer uma predição mais robusta e precisa.
- **Naive Bayes**
  - Algoritmo de classificação baseado no Teorema de Bayes, assume a independência entre os atributos para fazer previsões.
- **K-Means**
  - Algoritmo de clusterização que agrupa objetos em k grupos distintos
  - Minimiza a variância intra-grupo e maximiza a separação entre grupos.
- **Análise de Componentes Principais (PCA)**
  - Técnica de redução de dimensionalidade.
  - Transforma um conjunto de variáveis correlacionadas em um novo conjunto de variáveis não correlacionadas chamadas de componentes principais.
- **Análise ou Regra de Associação**
  - Técnica que busca descobrir relações e padrões de associação frequentes entre itens em um conjunto de dados.
  - Utilizado em problemas de recomendação.
  - Um grupo de valores determina outro grupo.
  - Atributos:
    - <u>Suporte:</u> percentual de registros que se encaixam na regra estabelecida.
    - <u>Confiança:</u> percentual de registros que atendem especificamente a regra.
- **Redes Neurais Artificiais**
  - Modelos computacionais inspirados no sistema nervoso humano
  - Utilizados para realizar tarefas complexas de aprendizado e classificação.
- **Support Vector Machines (SVM)**
  - Algoritmo de aprendizado de máquina supervisionado que mapeia os dados em um espaço dimensional superior.
  - Busca encontrar um hiperplano ótimo de separação entre diferentes classes.
- **Análise de Cluster**
  - Técnica que agrupa objetos similares em clusters ou grupos com base em suas características e similaridades.
- **Algoritmos Genéticos**
  - Técnicas baseadas na teoria da evolução para resolver problemas de otimização.
  - Utiliza uma abordagem de populações e operadores genéticos.
- **Redes Bayesianas**
  - Modelos probabilísticos que representam relações causais entre variáveis.
  - Usando um grafo acíclico dirigido que permite inferências e tomadas de decisão.
- **Gradient Boosting**
  - Técnica de aprendizado de máquina
  - Modelos de árvore de decisão fracos são combinados em uma sequência para melhorar o desempenho preditivo.
- **Análise de Séries Temporais**
  - Técnicas utilizadas para analisar e modelar dados que variam ao longo do tempo.
  - Objetivo de encontrar padrões e fazer previsões.
- **Análise Discriminante**
  - Conjunto de técnicas estatísticas utilizadas para classificar objetos.
  - Gera grupos distintos com base em suas características discriminantes.
- **Algoritmos de Mineração de Texto**
  - Algoritmos que extraem informações úteis de grandes volumes de texto não estruturado.
  - Permite a descoberta de padrões e insights.
- **Análise de Sentimentos**
  - Técnica que identifica, classifica e analisa as opiniões, sentimentos e emoções expressas em textos.
  - Como nos comentários das redes sociais e avaliações de produtos em lojas virtuais.
- **Redes Neurais Convolucionais (CNN)**
  - Classe especial de redes neurais profundas.
  - Projetadas para o processamento eficiente de dados estruturados, como imagens e sinais.
- **Deep Learning**
  - Abordagem de aprendizado de máquina baseada em redes neurais profundas.
  - Capaz de aprender representações complexas dos dados.
  - Possui alto desempenho em várias tarefas.
- **Análise de Redes Sociais**
  - Técnica que estuda as relações entre entidades (como pessoas, organizações, etc.) em uma rede social.
  - Analisa padrões de conexões e influências.
- **Aprendizado por Reforço**
  - Método de aprendizado de máquina.
  - O agente interage com um ambiente, aprende a tomar ações que maximizem uma recompensa cumulativa ao longo do tempo.

### Data Lake

- Repositório de armazenamento vasto e escalável.
- Armazena dados estruturados e não estruturados (heterogêneos) em seu formato bruto.
- Dados oriundos de diversas fontes distintas.
- Permite o armazenamento de diferentes tipos de dados.
- Possibilita análises e explorações flexíveis.

### ETL (Extração, Transformação, Carga)

- Processo de extração de dados de várias fontes.
- Transformação em um formato consistente.
- Carregamento em um banco de dados de destino ou data warehouse.
- Garante a qualidade e a integração dos dados.
