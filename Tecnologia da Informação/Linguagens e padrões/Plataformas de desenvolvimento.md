# Plataformas de Desenvolvimento

## Servidores Web (HTTP Server)

- **Nginx**

  - Utilizado como um servidor proxy reverso e também como um servidor web HTTP.
    - Liberar portas se usar o Uncomplicated Firewall (UFW) com os perfis.
      - Full: Abre as portas 80 (HTTP) e 443 (HTTPS) para criptografia SSL/TLS.
      - HTTP: Abre apenas a porta 80 (para tráfego da Web não criptografado).
      - HTTPS: Abre apenas a porta 443 (para criptografia SSL/TLS).
  - Opera com grandes volumes de tráfego, devido ao gerenciamento de conexões simultâneas.
    - Armazena em cache todas as respostas às solicitações feitas com os métodos HTTP (GET e HEAD) na primeira vez que essas respostas são recebidas de um servidor proxy.
  - Código aberto, alta performance, escalabilidade e baixo consumo de recursos.

- **Apache**

  - Código aberto mantido pela Apache Software Foundation.
  - Um dos servidores web mais antigos e populares.
  - Módulos estendem suas funcionalidades.

- **IIS (Microsoft Internet Information Services)**

  - Desenvolvido pela Microsoft para plataformas Windows.
  - Integrado ao sistema operacional Windows Server.
  - Suporte nativo para tecnologias da Microsoft, como ASP.NET e .NET Core.

## Servidores de Aplicação

- **Java Platform, Enterprise Edition (JEE)**

  - Criar e implantar aplicativos corporativos Java.
  - Conjunto de APIs e serviços para desenvolver aplicativos empresariais.
    - Acesso a banco de dados, serviços web, segurança, transações distribuídas, etc.
  - Utilizado em grandes organizações para desenvolver aplicativos corporativos de missão crítica.

- **Wildfly**

  - Anteriormente conhecido como JBoss Application Server.
  - Servidor de aplicativos Java de código aberto desenvolvido pela Red Hat.
  - Implementa as especificações do JEE
  - Recursos:
    - Clustering, balanceamento de carga, escalabilidade horizontal e suporte a microservices.
    - Usa JBoss Modules para fornecer isolamento de aplicação.
    - Console de Administração (Recursos).
      - Criar a conta de administrador (somente no primeiro acesso).
      - Interface baseada na web (acesso via navegador/browser).
      - Iniciar e parar o servidor.
      - Implantar e desimplantar aplicativos.
      - Configurar o servidor.
      - Monitorar o desempenho do servidor.

- **Apache Tomcat**

  - Código aberto mantido pela Apache Software Foundation.
  - Implementa as especificações do Java Servlet e JavaServer Pages (JSP)
  - Utilizado para hospedar aplicativos web em pequena e média escala.

    - Exemplo de código servlet:

      ```java
      protected void doGet(HttpServletRequest request,
      HttpServletResponse response)
      throws ServletException, IOException {
        // Lógica de tratamento da requisição
        int idade = Integer.parseInt(request.getParameter("idade"));
      }
      ```

- **Node.js**

  - Desenvolvimento de aplicativos de código aberto baseado em JavaScript.
  - Modelo de E/S não bloqueante e orientado a eventos.
  - Aplicativos em tempo real, APIs web, aplicativos de streaming, etc.
  - Famoso no desenvolvimento de aplicativos web.
  - Frameworks:
    - Express
      - Framework web minimalista. Simplifica o processo de criação de aplicativos web e APIs.
      - Recursos: rotas, solicitações HTTP, middleware, etc.
      - Escolha de componentes e bibliotecas que melhor se adequem ao projeto.
    - Next.js
      - Framework React de renderização do lado do servidor (SSR) e Static Site Generator (SSG).
      - Simplifica a construção de aplicativos web React.
      - Recursos: roteamento, pré-renderização, geração estática, CSS-in-JS, etc.
      - Escolhido para projetos que exigem SEO aprimorado, carregamento rápido de página.

## Conceito de Servidores de Armazenamento de Objetos

### Plataformas

- **Jackrabbit (JCR)**

  - Plataforma de gerenciamento de conteúdo baseada na tecnologia Java Content Repository (JCR).
  - Fornece um ambiente de armazenamento hierárquico para conteúdo estruturado e não estruturado.
  - Permite o gerenciamento eficiente de informações em um formato flexível.
  - Oferece recursos avançados de pesquisa, versionamento, controle de acesso e suporte a transações.
  - Adequado para aplicativos que exigem um sistema robusto de gerenciamento de conteúdo.

- **H2 DB**

  - Sistema de gerenciamento de banco de dados relacional (RDBMS) escrito em Java.
  - Conhecido por sua leveza, desempenho rápido e facilidade de uso.
  - Pode ser usado como um banco de dados incorporado em aplicativos Java ou como um servidor de banco de dados autônomo.
  - Suporta recursos avançados, como consultas SQL, transações ACID, índices, replicação e suporte a vários modos de acesso.
  - Uma escolha popular para aplicativos que exigem uma solução de banco de dados eficiente.

- **MinIO**

  - Sistema de armazenamento de objetos de código aberto.
  - Compatível com o protocolo S3 da Amazon.
  - Projetado para ser escalável, altamente disponível e fácil de usar.
  - Permite armazenar e recuperar grandes volumes de dados não estruturados.
  - Interface simples baseada em RESTful APIs.
  - Recursos como criptografia, replicação, balanceamento de carga e suporte a várias regiões.
  - Opção popular para aplicativos que precisam de armazenamento distribuído de objetos.

- **Apache Kafka**

  - Plataforma de streaming distribuída.
  - Usada para construir sistemas de mensagens em tempo real e processamento de fluxo de dados.
  - Projetado para lidar com grandes volumes de dados em tempo real.
  - Fornece uma arquitetura escalável e tolerante a falhas.
  - Permite a captura, armazenamento e processamento de streams de eventos em tempo real.
  - Fornece recursos como particionamento, replicação, persistência e garantias de entrega.
  - Utilizado em aplicativos de streaming, processamento de eventos, ingestão de dados em tempo real e pipelines de dados.

- **RabbitMQ**

  - Sistema de mensagens de código aberto.
  - Implementa o protocolo Advanced Message Queuing Protocol (AMQP).
  - Fornece uma plataforma robusta para troca de mensagens entre aplicativos distribuídos.
  - Permite o envio e a recepção de mensagens assíncronas entre diferentes componentes de um sistema.
  - Garante a entrega confiável e ordenada das mensagens.
  - Suporta recursos avançados, como filas, trocas, roteamento flexível e filas de mensagens persistentes.
  - Utilizado em aplicativos de integração, microservices, sistemas distribuídos e arquiteturas orientadas a eventos.

- **ActiveMQ**

  - **Fornecedor**
    - Solução de mensageria de código aberto mantida pela Apache Software Foundation.
    - Adotado pela comunidade de código aberto e é conhecido por ser de fácil uso e configuração.
  - **Protocolos Suportados**
    - Protocolo OpenWire, MQTT, AMQP, STOMP e WebSocket.
    - Isso o torna versátil e adequado para uma variedade de casos de uso.
    - Integração com o Ecossistema Apache. Como o Apache Camel.
  - **Modelo de Mensagens**
    - Segue o modelo de publish-subscribe e o modelo de fila de mensagens.
    - Permite a comunicação assíncrona entre diferentes aplicativos e componentes.
  - **Escalabilidade**
    - Pode ser configurado para atender às necessidades de escalabilidade horizontal e vertical.

- **WebSphereMQ (IBM MQ)**

  - **Fornecedor**
    - Desenvolvido pela IBM.
    - Solução de mensageria comercial de alto desempenho usada em ambientes empresariais.
  - **Protocolos Suportados**
    - TCP/IP, HTTP, WebSphere MQ JMS, entre outros.
    - Compatível com outros produtos da IBM.
  - **Modelo de Mensagens**
    - Segue o modelo de fila de mensagens e é conhecido por sua confiabilidade.
    - Garante que as mensagens sejam entregues uma única vez e na ordem correta.
  - **Recursos Avançados**
    - Clustering para alta disponibilidade.
      - Alternativa paralela à estrutura funcional de redes de dados, elétrica e computacional.
    - Criptografia de mensagens, suporte a transações distribuídas.
    - Integração com outros produtos da IBM, como o WebSphere Application Server.

## Gerenciamento de Contêineres

### Docker

#### Características

- Plataforma de código aberto para empacotar, distribuir e executar aplicativos em contêineres.
- Contêineres são ambientes isolados que contêm todas as dependências e bibliotecas necessárias para executar um aplicativo.
  - Segregação de processos no mesmo kernel.
  - O processo é isolado o máximo possível de todo o resto do ambiente.
- Garante que ele seja executado consistentemente em diferentes ambientes.
- Permite a escalabilidade e a portabilidade de aplicativos.
- Facilita a implantação de aplicativos e a construção de ambientes de desenvolvimento consistentes.
- Segue o formato estabelecido pela [OCI](#oci-open-container-initiative).

#### Recursos

- **Imagens Docker:** Pacotes pré-configurados que contêm tudo o que é necessário para executar um aplicativo.
- **Dockerfile:** Arquivo de configuração usado para construir imagens Docker de forma reproduzível.
- **Docker Hub:** Repositório online para compartilhar e distribuir imagens Docker.

### Kubernetes

#### Características

- Também conhecido como K8s e desenvolvido pelo Google, é uma plataforma de orquestração de contêineres declarativa de código aberto.
- Automatiza o gerenciamento, a escalabilidade e a implantação de aplicativos em contêineres.
- Usado para implantar e gerenciar aplicativos em ambientes de produção escaláveis e altamente disponíveis.
- Fornece um ambiente para implantar e executar aplicativos em vários nós de um cluster:
  - **Cluster:** é um grupo de nós.
  - **Nó:** é uma máquina que executa o kubelet.
  - **Kubelet:** é um processo que gerencia os contêineres em um nó.
- Gerencia automaticamente a distribuição de carga, o balanceamento de recursos e a resiliência dos aplicativos.

#### Recursos

- Dimensionamento automático.
- Monitoramento.
- Recuperação automática de falhas.
- Gerenciamento de segredos.
- **Pods:** A menor unidade em Kubernetes, que contém um ou mais contêineres.
- **Service:** Define um conjunto lógico de Pods e uma política de acesso a esses Pods.
- **Deployment:** Permite a definição e atualização de aplicativos.

#### Ferramentas

- **Argo CD**

  - **Características**
    - Ferramenta de entrega contínua declarativa e GitOps para Kubernetes.
    - Usado para gerenciar o ciclo de vida de aplicativos em um cluster Kubernetes.
    - Permite que você defina, implante e monitore aplicativos em um cluster Kubernetes.
    - Usa arquivos YAML e Git.
  - **Recursos**
    - Automatizar a implantação de aplicativos.
    - Auditar as alterações de configuração.
    - Garantir que os ambientes de implantação sejam consistentes e confiáveis.

- **OpenShift (Red Hat)**

  - Construída em cima do Kubernetes.
    - Install, update, and manage the lifecycle of Kubernetes native applications (Operators).
    - Cluster service version (definir metadados).
  - Usado por empresas para criar, implantar e gerenciar aplicativos em contêineres.
  - É uma plataforma de desenvolvimento e implantação de aplicativos baseada em contêineres.
  - Recursos de desenvolvimento, integração contínua, implantação contínua e escalabilidade automática.
  - Suporta o desenvolvimento de aplicativos em várias linguagens de programação.
  - Permite a integração com ferramentas populares de desenvolvimento e DevOps.

### OCI (Open Container Initiative)

#### Características

- A OCI é uma iniciativa de padrões abertos criada para garantir a portabilidade entre diferentes implementações de contêineres.
- Foi lançada para estabelecer padrões comuns para o formato de contêineres e as especificações de execução.

#### Principais componentes

- **Image Specification:** Define o formato e a estrutura de uma imagem de contêiner.
- **Runtime Specification:** Define como um contêiner deve ser executado e interagir com o sistema operacional subjacente.
- **Objetivo:**
  - Fornecer uma base comum para que diferentes implementações de contêineres possam interoperar e oferecer uma experiência consistente para os usuários.

## Arquiteturas de infraestrutura em nuvem (Cloud Computing)

### Características

- Modelo de fornecimento de serviços de computação.
- Oferece recursos compartilhados e escaláveis.
- Podem ser acessados de qualquer lugar e a qualquer momento.
- **Componentes**
  - Front-end (cliente ou dispositivo usado para acessar a nuvem).
  - Back-end (servidores e armazenamento).
  - Modelo de fornecimento com base em nuvem.
  - Rede disponível.

### Recursos e serviços oferecidos

- Servidores para processamento.
- Armazenamento de dados.
- Plataformas de desenvolvimento.
- Software e outros serviços relacionados.

### Benefícios

#### Escalabilidade

- Capacidade de um sistema crescer para atender a uma demanda crescente, mantendo ou melhorando o desempenho.
- Tipos:
  - Horizontal: adição de mais instâncias ou servidores.
  - Vertical: aumento da capacidade de um único servidor, como adicionar mais CPU, RAM, etc.

#### Elasticidade

- Capacidade de um sistema de se adaptar dinamicamente às mudanças na carga de trabalho.
- Aumenta ou reduz os recursos automaticamente conforme necessário.

#### Flexibilidade

- Capacidade de um sistema de ser adaptado ou modificado para atender a diferentes requisitos ou cenários sem grande esforço.

### Serviços comerciais

#### Azure

- **Data Explorer**

  - Análise quase em tempo real para fluxo rápido, dados de streaming de alto volume de dispositivos e sensores de IoT (Internet das Coisas).
  - Permite consultar e visualizar grandes volumes de dados de forma rápida e eficiente, facilitando a descoberta de insights e padrões em tempo real.

- **Virtual Machines (VMs)**

  - Implantação e gerenciamento de máquinas virtuais baseadas em Windows ou Linux.
  - Oferece uma variedade de tamanhos de máquina e sistemas operacionais.

- **App Service**

  - Criar, implantar e dimensionar aplicativos web e móveis.
  - Suporta várias linguagens de programação, como .NET, Java, Node.js e Python.

- **Functions**

  - Computação sem servidor que permite executar código em resposta a eventos sem precisar gerenciar servidores.
  - Os desenvolvedores podem escrever funções simples e focar apenas no código.

- **Storage**

  - Armazenamento de blobs (objetos), arquivos, tabelas e filas.

- **SQL Database**

  - Banco de dados relacional gerenciado.

- **Cosmos DB**

  - Banco de dados multimodelo.
  - Suporta vários modelos de dados: documentos, gráficos, chaves-valores e colunas.

- **Cognitive Services**

  - APIs pré-treinadas para adicionar recursos de inteligência artificial aos aplicativos.
  - Reconhecimento de fala, análise de sentimentos, detecção de rostos e tradução de idiomas.

- **DevOps**

  - Ferramentas para colaboração, desenvolvimento de software e entrega contínua.
  - Gerenciamento de código-fonte, planejamento de projetos, automação de CI/CD e monitoramento de aplicativos.

#### AWS (Amazon Web Service)

- **S3 (Simple Storage Service)**

  - Serviço de armazenamento de objetos que oferece escalabilidade, disponibilidade de dados e segurança.
  - Armazenar e recuperar quantidades massivas de dados de forma econômica.

- **EC2 (Elastic Compute Cloud)**

  - Oferece capacidade de computação redimensionável na nuvem (Load Balancer).
  - Permite lançar e dimensionar servidores virtuais conforme necessário.
  - Flexibilidade para lidar com cargas de trabalho variáveis.

- **RDS (Relational Database Service)**

  - Banco de dados relacional gerenciado que facilita a configuração, operação e escalabilidade.

- **Redshift**

  - Data warehousing totalmente gerenciado.
  - Analisar grandes conjuntos de dados usando SQL padrão.

- **Lambda**

  - Computação sem servidor.
  - Executar código em resposta a eventos sem precisar gerenciar servidores.

#### Google Cloud

- **Apigee**

  - Gerenciamento de API (Interface de Programação de Aplicações), e, geralmente, é considerado como uma solução PaaS (Plataforma como Serviço).

- **Compute Engine**

  - Máquinas virtuais escaláveis.
  - Oferece várias configurações para atender às necessidades de computação.

- **Kubernetes Engine (GKE)**

  - Orquestração de contêiner totalmente gerenciado com Kubernetes.

- **BigQuery**

  - Data warehousing totalmente gerenciado e escalável.
  - Permite analisar grandes conjuntos de dados em tempo real usando SQL.

- **Cloud Storage**

  - Armazenamento de objetos.

### Factories (Fábricas)

- Modelo de provisionamento automatizado de recursos de computação.
  - Uma fábrica de máquinas virtuais em nuvem.
    - Permite que os usuários solicitem e provisionem instâncias virtuais de servidores de forma automatizada.
    - Remove a necessidade de configurar fisicamente o hardware subjacente.
- Simplificam o processo de criação e gerenciamento de recursos computacionais em nuvem.
- Aumenta a escalabilidade e a flexibilidade.

### Orientação a serviço

#### Características

- Conceito central na computação em nuvem.
- Disponibilização de serviços independentes, escaláveis e reutilizáveis.
- Permite que os aplicativos sejam construídos como um conjunto de serviços interconectados e independentes.
- Cada serviço realiza uma função específica.
- Acessados por outros serviços ou aplicativos por meio de interfaces bem definidas.
- Promove a modularidade, o reuso e a flexibilidade na construção de aplicativos em nuvem.
- Permite a escalabilidade horizontal e a manutenção simplificada.

#### Modelos de serviço em nuvem

- **IaaS (Infraestrutura como Serviço)**

  - Fornece recursos de infraestrutura computacional virtualizada aos usuários.
    - Virtual Private Cloud (VPC).
      - Is a virtual network that closely resembles a traditional network that you'd operate in your own data center.
      - After you create a VPC, you can add subnets (range of IP addresses).
  - Inclui servidores virtuais, redes, armazenamento e outros recursos relacionados.
  - Os usuários têm controle total sobre o ambiente de computação.
  - Os usuários são responsáveis pela configuração e gerenciamento dos sistemas operacionais, aplicativos e dados.
  - O provedor de nuvem é responsável por fornecer a infraestrutura subjacente.
    - Garante a disponibilidade e escalabilidade dos recursos.
  - É adequado para organizações que desejam ter controle granular sobre a infraestrutura de computação.
  - Permite maior flexibilidade e personalização.
  - Pagamento por demanda/uso.

- **SaaS (Software como Serviço)**

  - Um aplicativo é disponibilizado aos usuários por meio da Internet.
  - Em vez de adquirir e instalar o software localmente, os usuários acessam o aplicativo remotamente.
    - Geralmente por meio de um navegador web.
  - O provedor de nuvem é responsável pela manutenção, atualização e operação do software.
    - Tópico relacionado: [12 fatores](/Tecnologia%20da%20Informação/Gestão%20e%20legislação/Metodologias/12%20fatores.md).
  - Os usuários se concentram em usar o aplicativo sem se preocupar com a infraestrutura subjacente.
  - Utilizado em diversas áreas:
    - Gerenciamento de relacionamento com o cliente (CRM).
    - Colaboração.
    - Gerenciamento de projetos.
    - Recursos Humanos.
    - Exemplos: Google Docs, Figma, etc.

- **PaaS (Plataforma como Serviço)**

  - Fornece uma plataforma de desenvolvimento e implantação de aplicativos aos usuários.
  - Oferece uma infraestrutura de execução e um conjunto de serviços e ferramentas.
  - Facilita o desenvolvimento, teste, implantação e gerenciamento de aplicativos.
  - Os desenvolvedores podem se concentrar na codificação do aplicativo.
  - O provedor de nuvem se encarrega da infraestrutura, escalabilidade e manutenção do ambiente de execução.
  - Adequado para equipes de desenvolvimento que desejam:
    - Acelerar o ciclo de vida do aplicativo.
    - Reduzir a complexidade operacional.
    - Se beneficiar da escalabilidade e flexibilidade da nuvem.

### Infraestrutura física

#### Zonas de disponibilidade

- Grupos separados de datacenters dentro de uma região.
- São próximas o suficiente para ter conexões de baixa latência.
- Suficientemente afastadas para reduzir a probabilidade de que mais de uma seja afetada por interrupções locais ou pelo clima.
- Datacenters conectados por uma rede de alto desempenho com baixa latência.

### Padrões de design de microsserviços na nuvem

1. SAGA

   - **Características**
     - Sequência de transações que atualiza cada serviço.
       - Publica uma mensagem ou evento para disparar a próxima etapa de transação.
     - Transações.
       - Uma transação pode ser composta por várias operações.
     - Ações compensatórias: para contornar falhas.
   - **Estratégias**
     - Coreografia.
       - Message Broker (mecanismo de mensageria).
     - Orquestração.
       - Orchestrator.
       - Componente: Saga Execution Coordinator (SEC).

2. CQRS (Command Query Responsibility Segregation)

   - **Características**
     - Padrão que separa as operações de leitura e atualização de um armazenamento de dados.
     - Segregação de Responsabilidade de Comando e Consulta.
   - **Benefícios**
     - Maximizar o desempenho, a escalabilidade e a segurança.
     - Permite ao sistema evoluir melhor ao longo do tempo.
     - Impede que os comandos de atualização causem conflitos.

## Automação (Infrastructure as Code)

### Ferramenta Terraform

- Usada para criar, alterar e destruir infraestrutura de nuvem de forma automatizada.
- Utiliza a HashiCorp Configuration Language (HCL).
  - É uma linguagem de configuração declarativa que é fácil de ler e escrever.
  - Permite que o usuário especifique a infraestrutura que deseja criar.
  - Usa essa especificação para criar a infraestrutura em vários provedores.
    - Como o AWS, Azure, Google Cloud e VMware vCenter.
  - Também pode descrever a configuração de sistemas e ser usado em conjunto com o Ansible.

### Administração e gerenciamento de ambientes de virtualização

#### Características

- Planejamento.
  - Recursos necessários.
  - Capacidade de armazenamento, a rede e a segurança.
- Segurança.
  - Implementação de políticas de segurança, patches regulares e medidas de isolamento.
- Monitoramento.
  - Acompanhar o desempenho das VMs.
  - Identificar problemas de recursos.
  - Planejar upgrades ou otimizações.
- Backup e recuperação.
  - Estratégias de backup e recuperação.
  - Os dados e as VMs podem ser restaurados em caso de falhas.
- Dimensionamento e otimização.
  - Acompanhe o uso de recursos.
  - Ajuste a alocação de recursos conforme necessário para evitar subutilização ou superutilização.
- Treinamento.
  - Certifique-se de que os administradores de sistemas estejam treinados e atualizados nas tecnologias de virtualização utilizadas.
- Testes e validação.
  - Antes de implementar mudanças significativas, realize testes em um ambiente de laboratório para evitar problemas em produção.

#### Ferramentas

1. **VMWare**

- Empresa líder em virtualização e oferece uma variedade de produtos, incluindo o vSphere e o ESXi.
- A administração do VMWare envolve.
  - Configuração de hosts ESXi.
  - Criação e a gestão de VMs.
  - Alocação de recursos.
  - Monitorização de desempenho.
  - Aplicação de políticas de segurança.
- Soluções:
  - vSphere.
    - Suíte de produtos que permite criar e gerenciar máquinas virtuais (VMs) em servidores físicos.
    - Possui recursos avançados de gerenciamento.
      - Migração ao vivo (vMotion).
      - Balanceamento de carga.
      - Recuperação de desastres.
  - ESXi.
    - É um [hypervisor](../Back-end/Sistemas%20Operacionais.md#camada-de-virtualização) de tipo 1 (bare-metal).
    - Executa diretamente no hardware do servidor.
    - Fornece um ambiente de virtualização de alto desempenho e segurança.

2. **KVM/Proxmox (Kernel-based Virtual Machine)**

- KVM: Tecnologia de virtualização de código aberto incorporada ao kernel do Linux.
- A administração do KVM/Proxmox envolve:
  - Instalação e configuração do Proxmox VE.
  - Criação de VMs e contêineres.
  - Gestão de redes virtuais.
  - Monitoramento de recursos.
- Com KVM e Proxmox, os administradores podem criar VMs e contêineres em servidores Linux.
- Aproveita as funcionalidades de virtualização do KVM e as ferramentas de gerenciamento do Proxmox.
- Proxmox.
  - Plataforma de gerenciamento de virtualização que utiliza KVM e contêineres Linux (LXC).
  - Oferece uma interface web fácil de usar para criar, implantar e gerenciar VMs e contêineres.
  - Suporta recursos avançados, como migração em tempo real e backups.

## Low-code e no-code

Utilizam plataformas visuais e intuitivas para facilitar o desenvolvimento de aplicativos.

### Vantagens

- Podem ser usadas por usuários que não são desenvolvedores.
- Facilitam o desenvolvimento de aplicativos.
- Oferecem uma variedade de recursos de segurança, mas não são isentos de falhas.
- São geralmente mais rápidas e eficientes do que o desenvolvimento manual.

### Desvantagens

- Podem limitar a personalização.
- Não atendem a complexidade crescente com requisitos avançados.
- Dependência do fornecedor da plataforma.
- Possíveis limitações de desempenho e escalabilidade.
- Falta de controle fino.
- Pode produzir código ineficiente ou não-otimizado.
