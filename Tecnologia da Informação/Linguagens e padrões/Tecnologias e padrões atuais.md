# Tecnologias e Padrões Atuais

## Web Services/APIs e Padrões de Interoperabilidade de Objetos Distribuídos

### CORBA (Common Object Request Broker Architecture)

- Padrão mais antigo, completo e complexo.
- Usado em sistemas distribuídos, de negócios e jogos.
- Conceito de objetos remotos.
  - Existem em uma máquina diferente da que o código está sendo executado.

### DCOM (Distributed Component Object Model)

- Semelhante ao CORBA, mas adequado para aplicações Microsoft Windows.

### RMI (Remote Method Invocation)

- Padrão utilizado em programação distribuída em Java
- Permite que objetos em máquinas virtuais Java diferentes possam invocar métodos uns nos outros de forma transparente.
  - Baseado em objetos remotos.
  - Utiliza a serialização de objetos para passar dados e argumentos de método entre as máquinas.
  - Usado em sistemas distribuídos Java, como servidores de aplicativos, serviços web, entre outros.

### REST (Representational State Transfer)

#### Características

- Estilo arquitetural utilizado na construção de APIs web.
- Adequado para aplicações compatíveis com navegadores web.
- Criação de interfaces que permitem que os clientes acessem e manipulem recursos em um sistema.
  - Baseado em HTTP.
  - Recursos identificados por URLs e podem ser representados em diferentes formatos (JSON, XML, HTML, CSS, RSS (Really Simple Syndication)).
  - Idempotente ou Idempotência: quando se chama a mesma funcionalidade com o mesmo valor o resultado deve ser sempre o mesmo.
- É recomendado usar Rate Limiter para evitar ataques a API e Negação de Serviço (DoS).

#### Princípios

- Uso de métodos HTTP (GET, POST, PUT, DELETE) para indicar a operação a ser realizada no recurso.
   - O método GET nunca pode mutar (mutate) ou mudar dados.
- Utilização de códigos de status HTTP para representar o resultado da operação.
- Separação clara entre o cliente e o servidor.
- O servidor não mantém estado sobre as solicitações do cliente.

#### Restrições/Constraints

- Uniform interface/interface uniforme.
  - Desacopla a arquitetura (independência entre cliente e servidor).
- Pode levar a casos de Over-fetching ou Under-fetching.

#### API RESTful

- Swagger (documentation tool).

### SOAP (Simple Object Access Protocol)

[Detalhes aqui](/Tecnologia%20da%20Informação/Linguagens%20e%20padrões/Padrões%20de%20documentos.md#soap-simple-object-access-protocol)

### XMLHttpRequest

- Objeto que permite que um navegador da web faça solicitações HTTP assíncronas a um servidor web.
- Usado em desenvolvimento web para criar aplicativos e páginas da web interativas.
- Busca e atualiza dados sem recarregar a página inteira.
- Parte fundamental da tecnologia AJAX (Asynchronous JavaScript and XML).

### GraphQL (Alternativa para REST)

#### Características

- Linguagem de consulta e especificação para APIs desenvolvida pelo Facebook.
- Permite que clientes solicitem e recebam dados específicos em uma única solicitação.
  - Evita Over-fetching e Under-fetching.
  - Cliente envia uma única consulta especificando campos e informações necessárias.
  - Servidor responde com dados solicitados.

#### Vantagens

- Maior flexibilidade e eficiência na obtenção dos dados.
- Redução de largura de banda necessária para comunicações entre cliente e servidor.
- Capacidade de introspecção, onde clientes podem consultar a própria API.

#### Desvantagens

- As queries podem reduzir a performance do servidor.
- Aceita apenas POST requests.
- Retorna apenas com HTTP 200 e pode levar a confusão, pois as informações de erro são inseridas no corpo da request.

### AMQP (Advanced Message Queuing Protocol)

#### Características

- Protocolo da Internet.
- Padrão aberto e padronizado para troca de mensagens entre sistemas distribuídos.
- Projetado para comunicação confiável e assíncrona entre aplicativos.
  - Utiliza arquitetura de mensagens em fila.
  - Garante entrega confiável e interoperabilidade entre sistemas.

#### Recursos

1. Fila de mensagens.
   - Criação de filas para armazenar mensagens até serem consumidas pelos aplicativos.
   - Permite sistemas distribuídos resilientes e assíncronos.
2. Exchange de mensagens.
   - Roteamento de mensagens para filas corretas com base em critérios definidos.
   - Possibilita implementação de diferentes padrões de roteamento.
3. Modelos de confiabilidade.
   - Oferece opções para garantir confiabilidade na troca de mensagens.
   - Confirmações de entrega e transações.
4. Interoperabilidade.
   - Projetado para ser interoperável, permitindo comunicação entre diferentes sistemas e fornecedores.
   - Define especificação comum.

### WebSockets

#### Características

- Protocolo de comunicação bidirecional.
- Permite comunicação em tempo real entre navegador e servidor.
- Baseado em TCP.
- Multiplexação com HTTP/2.
- Usa CONNECT em vez de GET.

#### Usos

- Bate-papo social ou Live Chat.
- Espaços de trabalho de colaboração online.
- Jogos multijogador.
- Feeds de plataformas de transações financeiras.

## Protocolos de Comunicação

### HTTP/2

#### Conceito

- Segunda versão do protocolo HTTP (Hypertext Transfer Protocol).
- Utilizado para comunicação entre navegadores web e servidores.
- Permite a transferência de dados entre redes de computadores.
- Possibilita que ao inserir a URL do seu site na Web seja possível ver os conteúdos e dados que nele existem.
- É a base da comunicação que existe em toda a Internet em que os sites e conteúdos que tragam hiperlinks possam ser encontrados mais facilmente.
- Projetado para melhorar o desempenho da web, incluindo carregamento de páginas e recursos web.
- Na camada de transporte, o protocolo TCP.

#### Características

- Multiplexação.
  - Permite transmissão simultânea de várias solicitações e respostas em uma única conexão TCP.
  - Reduz a latência e melhora a eficiência.
- Compressão de cabeçalho.
  - Economiza largura de banda e acelera carregamento de páginas.
- Priorização.
  - Indica solicitações mais importantes, garantindo que recursos críticos sejam carregados primeiro.
- Push de servidor.
  - Servidores podem enviar recursos adicionais para o cliente antes de serem solicitados.
  - Melhora velocidade de carregamento de páginas.

## Padrões de Desenvolvimento

### AOP (Aspect-Oriented Programming)

#### Características

- Paradigma de programação para separar preocupações transversais do código principal.
- Aspectos encapsulam comportamentos comuns que cortam várias partes do código.

#### Vantagens

- Permite declaração separada e aplicação de aspectos ao código em tempo de execução.
- Proporciona separação clara de responsabilidades.
- Facilita manutenção e reutilização do código.
- Implementado de várias formas em diferentes linguagens, incluindo uso de proxies, injeção de dependência e manipulação de bytecode.
- Usado em conjunto com paradigmas como programação orientada a objetos (POO).

### Toolkits de Workflow (Business Process Management)

#### jBPM

##### Características

- Java Business Process Management
- Ambiente de desenvolvimento e execução para modelagem, automação e monitoramento de processos de negócios.
- Utiliza notação [BPMN (Business Process Model and Notation)](</Tecnologia da Informação/Linguagens e padrões/BPMN.md>) para representação gráfica dos processos.

##### Recursos e Funcionalidades

1. Modelagem Gráfica
   - Interface gráfica para criação e modelagem de processos de negócios.
   - Utilização da notação BPMN para definir atividades, decisões, fluxos de sequência, eventos, etc.
   - Inclusão de anti-padrões para garantir a qualidade do processo.
2. Execução de Processos.
   - Permite execução de processos de negócios modelados.
   - Suporta interação entre pessoas e sistemas.
   - Automatização de tarefas e coordenação de atividades em fluxos de trabalho.
3. Monitoramento e Controle.
   - Recursos de monitoramento em tempo real para acompanhamento de desempenho dos processos.
   - Visualização de métricas e identificação de gargalos.
4. Gerenciamento de Exceções.
   - Identificação e tratamento de exceções durante execução de processos.
   - Mecanismos para lidar com erros e recuperar execução do processo.
5. Integração e Extensibilidade.
   - Integração com outros sistemas e aplicativos empresariais via APIs e serviços web.
   - Suporte a extensões e personalizações.

#### Bizagi BPM

##### Características

- Automatiza e melhora processos organizacionais.
- Plataforma para modelagem, execução e análise de processos.
- Otimiza operações e melhora eficiência.

##### Recursos e Funcionalidades

1. Modelagem Gráfica
   - Interface intuitiva de arrastar e soltar para modelagem de processos de negócios.
   - Criação de diagramas BPMN para representar etapas, decisões, eventos e fluxos de trabalho.
2. Automatização de Processos.
   - Automatização de processos de negócios, com tarefas atribuídas, executadas e monitoradas automaticamente.
   - Suporte a fluxos de trabalho sequenciais e paralelos, escalonamento de tarefas, aprovações e integração com sistemas externos.
3. Integração de Sistemas.
   - Integração com outros sistemas e aplicativos empresariais (CRM, ERP).
   - Permite que processos de negócios aproveitem dados e funcionalidades de sistemas existentes.
4. Análise e Otimização de Processos.
   - Recursos de análise e relatórios para monitoramento de desempenho dos processos.
   - Identificação de gargalos e oportunidades de melhoria com métricas, gráficos e indicadores de desempenho.
5. Colaboração e Controle de Acesso.
   - Suporte a colaboração entre membros da equipe.
   - Trabalho conjunto na modelagem, execução e melhoria de processos.
   - Recursos de controle de acesso para garantir segurança na modificação dos processos.

## Blockchain

Possibilita o armazenamento e compartilhamento de dados de forma distribuída, criptografada e sem a intermediação de terceiros.

## Modelo Nacional de Interoperabilidade (MNI) (usado somente no Judiciário)

### Objetivo

- Remessa de processos eletrônicos entre tribunais.

### Operações

- Utiliza o protocolo SOAP (Simple Object Access Protocol).
- Exemplo: Consultar Processos.

### Dinâmica das Comunicações

- Fluxos negociais a partir da composição das operações.

### Tipos de Fluxo

1. Principal.
   - Remessa.
   - Baixa definitiva.
2. Alternativo.
   - Envio complementar.
   - Devolução.
   - Reenvio.
   - Declínio de competência.
   - Baixa em diligência.
