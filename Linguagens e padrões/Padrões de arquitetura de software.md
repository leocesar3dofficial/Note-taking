# Padrões de Arquitetura de Software

## MVC (Model-View-Controller)

- **Separação de Responsabilidades:**

  - O modelo (model) representa os dados e a lógica de negócios.
  - A visão (view) é responsável pela apresentação dos dados ao usuário.
  - O controlador (controller) manipula as interações do usuário e coordena o modelo e a visão.

- **Modularidade:**

  - Permite que diferentes componentes possam ser desenvolvidos, testados e mantidos independentemente.

  - **Reutilização de Código:**
    - Os componentes podem ser reutilizados em diferentes partes da aplicação.

## Orientado a Eventos

- Baseado em um modelo de programação reativa.
- Os componentes reagem a eventos gerados por outros componentes ou pelo sistema.

- **Comunicação Assíncrona:**

  - Os componentes podem enviar e receber eventos sem bloquear a execução.

- **Desacoplamento:**
  - Os componentes não precisam ter conhecimento direto uns dos outros.
  - Facilita a manutenção e a evolução do sistema.

## Microsserviços

- **Arquitetura Distribuída:**

  - O sistema é dividido em serviços independentes que se comunicam por meio de APIs.

- **Escalabilidade e Flexibilidade:**

  - Cada serviço pode ser dimensionado e atualizado individualmente.
  - Permite que partes específicas do sistema sejam otimizadas.

- **Desacoplamento:**
  - Cada serviço é responsável por uma funcionalidade específica.
  - Pode ser desenvolvido, implantado e mantido independentemente.

## SOA (Service Oriented Architecture)

- **Estrutura Baseada em Serviços:**

  - As funcionalidades do sistema são oferecidas como serviços.
  - Podem ser acessados por meio de interfaces padrão.

- **Reutilização de Serviços:**

  - Os serviços podem ser compartilhados e reutilizados em diferentes aplicações ou processos de negócio.

- **Interoperabilidade:**
  - Os serviços podem ser implementados em diferentes tecnologias e plataformas.
  - Permite a integração de sistemas heterogêneos.

## Web Services

- Padrão de comunicação baseado em protocolos web como HTTP, XML e JSON

### Interoperabilidade

- Os serviços podem ser consumidos por diferentes tecnologias e plataformas
- Descoberta e registro de serviços
  - Os serviços podem ser descobertos e registrados em um diretório para facilitar a sua utilização

### Controles e testes de segurança

#### Autenticação

- Garante que apenas usuários autorizados possam acessar e consumir os Web Services

##### Métodos comuns

- Tokens de acesso
- Autenticação baseada em certificados digitais
- Autenticação de usuário e senha

#### Autorização

- Uma vez autenticado, é necessário controlar quais operações e recursos um usuário pode acessar
- Define permissões e restrições de acesso aos Web Services com base em papéis ou grupos de usuários

#### Criptografia

- Garantir a confidencialidade dos dados
- Uso de protocolos como HTTPS (HTTP seguro)
- Utilizar criptografia de ponta a ponta com chaves assimétricas

#### Validação e sanitização de entrada

- Evita ataques de injeção, como SQL Injection ou Cross-Site Scripting (XSS)
- Técnicas como validação de formato, restrição de caracteres especiais e escape de caracteres perigosos

#### Controle de sessão

- Se os Web Services possuem estado, é necessário implementar um controle de sessão adequado
- Protege contra ataques de falsificação de solicitação entre sites (CSRF)

#### Auditoria, monitoração e logs

- Registrar informações detalhadas sobre as transações e atividades dos Web Services
- Detecção e investigação de possíveis incidentes de segurança
- Os logs devem incluir informações como origem das solicitações, horários, ações realizadas e resultados obtidos

##### Simple Network Management Protocol (SNMP)

- É um protocolo utilizado para o gerenciamento e monitoramento de dispositivos de rede e sistemas de TI
- Coleta informações sobre o status e o desempenho de dispositivos de rede
  - Como roteadores, switches, servidores, impressoras, entre outros
- Opera em um modelo cliente-servidor
  - Os dispositivos gerenciados (agentes) relatam informações para um sistema de gerenciamento de rede (gerente)
- As informações são organizadas em uma estrutura de dados hierárquica chamada de MIB (Management Information Base)

### Ferramentas

#### Zabbix

- Monitora a infraestrutura de TI, como redes, servidores, máquinas virtuais e serviços em nuvem
- Coleta e exibe métricas básicas
- Ferramenta de software de código aberto

#### Nagios

- É uma ferramenta de código aberto utilizada para monitorar a infraestrutura de TI
- Permite monitorar servidores, serviços, hosts e dispositivos de rede
- Pode alertar os administradores quando ocorrem problemas
  - Notificações por e-mail, SMS ou outros meios
- Oferece recursos de geração de relatórios e históricos de desempenho

#### Prometheus

- É uma plataforma de monitoramento de código aberto
- Coleta e armazena métricas de sistemas e serviços em tempo real
- É escalável e oferece recursos de consultas flexíveis, alertas configuráveis
- Integrações com outras ferramentas, como Grafana

#### Grafana

- É uma plataforma de visualização de métricas de código aberto
- Funciona em conjunto com outras ferramentas de monitoramento, como Prometheus e InfluxDB
- Permite criar painéis interativos e gráficos para visualizar dados de desempenho em tempo real
- Utilizado para criar painéis de monitoramento personalizados e relatórios

#### Application Performance Monitoring (APM)

- É uma categoria de ferramentas que se concentra na monitorização do desempenho de aplicativos
- Usadas para rastrear e analisar o comportamento de aplicativos em tempo real
- Identifica gargalos de desempenho, erros e áreas de melhoria
- Exemplos de ferramentas de APM incluem New Relic, AppDynamics e Dynatrace

#### Stack ELK (código aberto)

##### Elasticsearch

##### Características

- É uma plataforma de busca e análise de dados distribuída em tempo real
- Construído em cima do Apache Lucene
- Usado para indexar, pesquisar e analisar grandes volumes de dados de forma eficiente
- Suporta várias fontes de dados
- Permite a execução de consultas complexas em tempo real
- Recursos avançados, como agregação, filtragem, pesquisa de texto completo
- Suporte a várias linguagens de consulta
- Amplamente utilizado em aplicativos de busca, análise de logs, monitoramento e análise de dados em tempo real

##### Index Lifecycle Management (ILM)/Ciclo de Vida de Índices

##### Estágios

1. Hot

- Ingestão de dados
- Rollover de um índice baseado no nível de espaço em disco

2. Warm

- Índices consultados, mas com menor frequência

3. Cold

- Não são utilizados para consultas
- Mantidos por diversos motivos como: normas regulamentares, histórico, etc.

4. Delete

- Índices prontos para serem excluídos

##### Logstash

##### Ingestão de dados de log e na preparação de dados para consulta e análise em tempo real

##### Recursos

##### Ingestão de Dados

- Coleta dados de uma ampla variedade de fontes
  - logs de aplicativos, logs de sistemas, feeds de sensores, eventos de rede, entre outros
- Suporta inúmeras entradas, como arquivos de log, syslog, Beats, JDBC, HTTP, e muitos outros

##### Processamento de Dados

- Transforma e enriquece os dados de log durante o processo de ingestão
- Usa filtros que podem realizar tarefas como
  - análise de padrões, remoção ou anonimização de informações confidenciais,
  - conversão de formatos de data/hora e enriquecimento de dados com informações adicionais

##### Saída de Dados

- Após o processamento, envia os dados preparados para vários destinos,
- O Elasticsearch para armazenamento e o Kibana para visualização e análise
- É possível configurar saídas para outros sistemas
  - como bancos de dados, sistemas de mensagens, arquivos e muito mais

##### Plugins

- Extensível por meio de plugins
- Possui uma grande biblioteca de plugins de entrada, filtro e saída
- Podem ser usados para adaptar a ferramenta às necessidades específicas do seu ambiente

##### Configuração Flexível

- Feita por meio de arquivos de configuração simples e flexíveis
- Nos formatos JSON ou YAML
- Permite que você defina como os dados devem ser coletados, processados e para onde devem ser enviados

##### Escalabilidade

- Pode ser dimensionado horizontalmente para lidar com grandes volumes de dados
- Pode configurar várias instâncias do Logstash para trabalhar em paralelo e balancear a carga

##### Monitoramento e Gerenciamento

- A Elastic fornece ferramentas de monitoramento e gerenciamento, como o Elasticsearch e o Kibana
- Podem ser usadas em conjunto com o Logstash para acompanhar o desempenho e a saúde
- do sistema de ingestão de logs

##### Kibana

##### Características

- É uma plataforma de visualização e exploração de dados de código aberto desenvolvida pela Elastic
- Projetado para trabalhar em conjunto com o Elasticsearch
- Atua como uma interface de usuário amigável para análise e visualização de dados
  - armazenados no Elasticsearch e outros sistemas de armazenamento de dados

##### Recursos

##### Visualização de Dados

- Permite criar painéis interativos e gráficos a partir dos dados armazenados no Elasticsearch
- Gráficos de barras, gráficos de pizza, tabelas, mapas geográficos e muito mais
- para explorar e analisar informações

##### Painéis Personalizados

- Agregam várias visualizações em uma única página
- Monitorar métricas e estatísticas específicas

##### Busca e Filtragem Avançada

- Fornece uma poderosa linguagem de consulta
- que permite buscar, filtrar e analisar dados de maneira flexível
- Realiza consultas em tempo real para encontrar informações específicas nos dados

##### Exploração de Logs e Métricas

- Usado para análise de logs e métricas
- Identifica problemas em sistemas, aplicativos e infraestrutura
- Fornece insights sobre eventos, erros e tendências

##### Suporte a Dados Geoespaciais

- Recursos avançados de visualização geoespacial
- Permite a criação de mapas interativos com base em dados geográficos

##### Integração com Elasticsearch

- Usado para explorar e visualizar dados indexados no Elasticsearch
- O Elasticsearch é um mecanismo de pesquisa e análise de dados distribuído
  - Usado para armazenar e consultar grandes volumes de dados

##### Segurança e Autenticação

- Autenticação de usuário e controle de acesso
- Permite que limite o acesso às visualizações e painéis com base em funções e permissões

##### Extensibilidade via plugins

### Testes de segurança

- Testes de penetração (penetration testing)
- Análise de vulnerabilidades
- Testes de segurança automatizados
- Revisões de código para identificar possíveis brechas ou falhas de segurança

## Cliente-servidor

- Divisão de responsabilidades entre o cliente (interface de usuário) e o servidor (processamento e armazenamento)
- Comunicação em duas direções
  - O cliente solicita informações ou serviços ao servidor
  - O servidor responde com os dados necessários
- Escalabilidade
  - O servidor pode ser dimensionado para atender a um grande número de clientes simultaneamente

## Pipes-and-filters

- Transformação de dados em etapas sequenciais
- Fluxo de dados através de uma série de componentes de processamento
  - Filtros conectados por meio de canais (pipes)
- Processamento modular
  - Cada filtro realiza uma tarefa específica e os dados fluem sequencialmente pelos filtros
- Flexibilidade
  - É possível combinar e reorganizar os filtros para atender a diferentes requisitos de processamento

## P2P (Peer-to-Peer)

- Arquitetura descentralizada
  - Todos os nós da rede têm capacidade de serem tanto clientes quanto servidores
  - Compartilhamento de recursos
    - Os nós podem compartilhar recursos
    - Dados e poder de processamento de forma direta
- Escalabilidade
  - O sistema pode ser escalado adicionando-se novos nós à rede
  - Não há necessidade de uma infraestrutura centralizada

## Serverless

- Conceito
  - Modelo de computação em nuvem
  - Permite aos desenvolvedores executar código sem se preocupar com a infraestrutura subjacente
  - Funções ou pequenas unidades de código que são executadas em resposta a eventos
    - Solicitações HTTP, uploads de arquivos ou alterações em bancos de dados
- Características
  - Escalabilidade automática
    - Provedores de serviços em nuvem, como AWS Lambda, Azure Functions e Google Cloud Functions
    - Gerenciam automaticamente o dimensionamento das funções conforme a demanda
    - Permite que os aplicativos sejam altamente escaláveis
  - Pagamento por uso
    - Você paga apenas pelo tempo de execução real das funções
    - Econômica para cargas de trabalho intermitentes ou de baixo tráfego
  - Ausência de gerenciamento de infraestrutura
    - Não há necessidade de configuração ou manutenção
      - De servidores, bancos de dados ou outros recursos de infraestrutura
    - Simplifica o desenvolvimento e a implantação de aplicativos
  - Event-driven
    - As funções são acionadas por eventos
    - Promove a criação de aplicativos reativos e orientados a eventos

## Hexagonal ou Ports and Adapters (Arquitetura de Portas e Adaptadores)

- Conceito
  - Visa separar as preocupações de negócios da infraestrutura e das tecnologias externas
  - Separação entre a lógica de negócios e a interação com o mundo externo
  - Chamada de "hexagonal" devido à sua representação gráfica que se assemelha a um hexágono
- Características
  - Separação de camadas
    - Aplicação, Negócios, Adaptadores e Portas
  - Portas e adaptadores
    - As portas são interfaces onde a lógica de negócios se comunica com o mundo externo
    - Os adaptadores são responsáveis por implementar as portas e lidar com detalhes de implementação
      - Acesso a banco de dados, chamadas de API, etc.
  - Testabilidade
    - Facilita a testabilidade
    - Pode substituir os adaptadores por simuladores ou mocks durante os testes
    - Mantém a lógica de negócios inalterada
  - Flexibilidade
    - A separação de camadas e a modularização tornam a arquitetura flexível
    - e facilmente adaptável a mudanças nos requisitos ou na tecnologia
  - Manutenção e evolução
    - As mudanças na infraestrutura externa têm impacto mínimo na lógica de negócios

## Anti-padrões arquiteturais

- Monolito Gigante (Big Ball of Mud)
  - Todo o código do sistema é colocado em um único monólito, tornando-o grande e difícil de gerenciar
  - Não há separação adequada de preocupações
  - A complexidade aumenta à medida que o sistema cresce, tornando a manutenção e a escalabilidade problemáticas
- Mágica de Alto Acoplamento (Spaghetti Code)
  - O código é altamente acoplado, com muitas dependências entre diferentes partes do sistema
  - Torna o código difícil de entender e de testar
  - Qualquer alteração em uma parte do código pode ter efeitos colaterais imprevisíveis em outras partes
- Interface Monolítica (Monolithic Interface)
  - Uma única interface é projetada para várias funcionalidades ou casos de uso diferentes
  - Resulta em uma interface grande e confusa
  - Torna a interface difícil de usar, entender e manter
- Dependência Circular (Circular Dependency)
  - Ocorre quando dois ou mais módulos ou componentes dependem uns dos outros, criando um loop de dependência
  - Dificulta a compreensão do fluxo de controle e tornam as mudanças no sistema arriscadas
- Procrastinação (Architectural Drift)
  - Decisões arquiteturais importantes são adiadas indefinidamente
  - Resulta em um sistema que cresce organicamente, sem um plano ou estrutura clara
  - Leva a sistemas desorganizados e difíceis de manter e expandir
- Erros de Sincronização (Race Conditions)
  - Ocorrem quando múltiplos threads ou processos competem por recursos compartilhados
  - Leva a resultados imprevisíveis ou inesperados
  - Resulta em problemas de segurança e desempenho
- Projeto por Exceção (Design by Exception)
  - O código é projetado principalmente para tratar exceções ou casos de erro
  - Em vez de se concentrar no fluxo principal da lógica de negócios
  - Leva a um código inchado, difícil de ler e manter
- Código Copiado e Colado (Copy-Paste Programming)
  - Envolvem a prática de copiar e colar código em vez de reutilizá-lo de maneira adequada
  - Resulta em duplicação de código
  - Tornam as atualizações e correções difíceis de manter em sincronia

## Programação Assíncrona

- É uma técnica que permite que um programa execute tarefas em segundo plano
- Sem bloquear a execução principal do programa
- Em vez de esperar que uma tarefa seja concluída antes de continuar
- ela permite que o programa continue executando outras tarefas enquanto aguarda a conclusão de operações demoradas
- Usada para melhorar a responsividade e o desempenho de sistemas que precisam lidar com E/S intensiva
  - Aplicativos web que precisam processar várias solicitações simultaneamente

## Ferramentas de Integração Assíncrona

- Tecnologias e bibliotecas que permitem a comunicação entre componentes ou sistemas de forma assíncrona
- Sistemas de mensageria, como RabbitMQ ou Apache Kafka
- Permitem a troca de mensagens entre sistemas de forma assíncrona, facilitando a comunicação entre componentes distribuídos

## Programação Multithread

- Criação e gerenciamento de várias threads de execução em um programa
- Threads são unidades de processamento leves que podem ser usadas para executar tarefas simultaneamente
- Usada para melhorar o desempenho e a capacidade de resposta de sistemas
- Permite que tarefas concorrentes sejam executadas em paralelo
- Importante em sistemas multiusuários e que precisam lidar com carga de trabalho intensiva

## Sub-rotinas (ou funções)
