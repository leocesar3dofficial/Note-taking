**Plataformas de Desenvolvimento**

- **Servidores Web (HTTP Server)**

  - Nginx
    - Liberar portas se usar o Uncomplicated Firewall (UFW) com os perfis
      - Nginx Full: Abre as portas 80 e 443 (para criptografia SSL/TLS)
      - Nginx HTTP: Abre apenas a porta 80 (para tráfego da Web não criptografado)
      - Nginx HTTPS: Abre apenas a porta 443 (para criptografia SSL/TLS)
  - Apache
  - IIS (Microsoft Internet Information Services)

- **Servidores de Aplicação**

  - Java Platform, Enterprise Edition (JEE)
  - Wildfly
    - Usa JBoss Modules para fornecer isolamento de aplicação
    - Console de Administração (Recursos)
      - Criar a conta de administrador (somente no primeiro acesso)
      - Interface baseada na web (acesso via navegador/browser)
      - Iniciar e parar o servidor
      - Implantar e desimplantar aplicativos
      - Configurar o servidor
      - Monitorar o desempenho do servidor
  - Tomcat
  - Node.js
    - Express
    - Next.js

- **Conceito de Servidores de Armazenamento de Objetos**

  - **Plataformas**
    - Jackrabbit (JCR)
      - Plataforma de gerenciamento de conteúdo baseada na tecnologia Java Content Repository (JCR)
      - Fornece um ambiente de armazenamento hierárquico para conteúdo estruturado e não estruturado
      - Permite o gerenciamento eficiente de informações em um formato flexível
      - Oferece recursos avançados de pesquisa, versionamento, controle de acesso e suporte a transações
      - Adequado para aplicativos que exigem um sistema robusto de gerenciamento de conteúdo
    - H2 DB
      - Sistema de gerenciamento de banco de dados relacional (RDBMS) escrito em Java
      - Conhecido por sua leveza, desempenho rápido e facilidade de uso
      - Pode ser usado como um banco de dados incorporado em aplicativos Java ou como um servidor de banco de dados autônomo
      - Suporta recursos avançados, como consultas SQL, transações ACID, índices, replicação e suporte a vários modos de acesso
      - Uma escolha popular para aplicativos que exigem uma solução de banco de dados eficiente
    - MinIO
      - Sistema de armazenamento de objetos de código aberto
      - Compatível com o protocolo S3 da Amazon
      - Projetado para ser escalável, altamente disponível e fácil de usar
      - Permite armazenar e recuperar grandes volumes de dados não estruturados
      - Interface simples baseada em RESTful APIs
      - Recursos como criptografia, replicação, balanceamento de carga e suporte a várias regiões
      - Opção popular para aplicativos que precisam de armazenamento distribuído de objetos
    - Apache Kafka
      - Plataforma de streaming distribuída
      - Usada para construir sistemas de mensagens em tempo real e processamento de fluxo de dados
      - Projetado para lidar com grandes volumes de dados em tempo real
      - Fornece uma arquitetura escalável e tolerante a falhas
      - Permite a captura, armazenamento e processamento de streams de eventos em tempo real
      - Fornece recursos como particionamento, replicação, persistência e garantias de entrega
      - Amplamente utilizado em aplicativos de streaming, processamento de eventos, ingestão de dados em tempo real e pipelines de dados
    - RabbitMQ
      - Sistema de mensagens de código aberto
      - Implementa o protocolo Advanced Message Queuing Protocol (AMQP)
      - Fornece uma plataforma robusta para troca de mensagens entre aplicativos distribuídos
      - Permite o envio e a recepção de mensagens assíncronas entre diferentes componentes de um sistema
      - Garante a entrega confiável e ordenada das mensagens
      - Suporta recursos avançados, como filas, trocas, roteamento flexível e filas de mensagens persistentes
      - Amplamente utilizado em aplicativos de integração, microservices, sistemas distribuídos e arquiteturas orientadas a eventos
    - ActiveMQ
      - **Fornecedor**
        - Solução de mensageria de código aberto mantida pela Apache Software Foundation
        - Adotado pela comunidade de código aberto e é conhecido por ser de fácil uso e configuração
      - **Protocolos Suportados**
        - Protocolo OpenWire, MQTT, AMQP, STOMP e WebSocket
        - Isso o torna versátil e adequado para uma variedade de casos de uso
      - **Modelo de Mensagens**
        - Segue o modelo de publish-subscribe e o modelo de fila de mensagens
        - Permite a comunicação assíncrona entre diferentes aplicativos e componentes
      - **Escalabilidade**
        - Pode ser configurado para atender às necessidades de escalabilidade horizontal e vertical
      - **Integração com o Ecossistema Apache**
        - Como parte do ecossistema Apache, pode ser facilmente integrado com outras ferramentas e tecnologias Apache
          - como o Apache Camel, para criar soluções de integração mais abrangentes
    - WebSphereMQ (IBM MQ)
      - **Fornecedor**
        - Desenvolvido pela IBM
        - Solução de mensageria comercial de alto desempenho usada em ambientes empresariais
      - **Protocolos Suportados**
        - TCP/IP, HTTP, WebSphere MQ JMS, entre outros
        - Compatível com outros produtos da IBM
      - **Modelo de Mensagens**
        - Segue o modelo de fila de mensagens e é conhecido por sua confiabilidade
        - Garante que as mensagens sejam entregues uma única vez e na ordem correta
      - **Recursos Avançados**
        - Clustering para alta disponibilidade
        - Criptografia de mensagens, suporte a transações distribuídas
        - Integração com outros produtos da IBM, como o WebSphere Application Server
      - **Licenciamento**
        - É uma solução comercial e requer licenciamento

- **Gerenciamento de Contêineres**
  - Docker
    - Plataforma de código aberto para empacotar, distribuir e executar aplicativos em contêineres
    - Contêineres são ambientes isolados que contêm todas as dependências e bibliotecas necessárias para executar um aplicativo
    -

Garante que ele seja executado consistentemente em diferentes ambientes - Fornece uma maneira fácil e eficiente de criar, implantar e gerenciar contêineres - Permitindo a escalabilidade e a portabilidade de aplicativos - Facilita a implantação de aplicativos e a construção de ambientes de desenvolvimento consistentes

- Kubernetes
  - Plataforma de orquestração de contêineres de código aberto
  - Automatiza o gerenciamento, a escalabilidade e a implantação de aplicativos em contêineres
  - Usado para implantar e gerenciar aplicativos em ambientes de produção escaláveis e altamente disponíveis
  - Fornece um ambiente para implantar e executar aplicativos em vários nós de um cluster
    - **Cluster:** é um grupo de nós
    - **Nó:** é uma máquina que executa o kubelet
    - **Kubelet:** é um processo que gerencia os contêineres em um nó
  - Gerencia automaticamente a distribuição de carga, o balanceamento de recursos e a resiliência dos aplicativos
  - **Recursos Avançados**
    - Dimensionamento automático
    - Monitoramento
    - Recuperação automática de falhas
    - Gerenciamento de segredos
  - **Ferramentas**
    - Argo CD
      - **Características**
        - Ferramenta de entrega contínua declarativa e GitOps para Kubernetes
        - Usado para gerenciar o ciclo de vida de aplicativos em um cluster Kubernetes
        - Permite que você defina, implante e monitore aplicativos em um cluster Kubernetes
        - Usa arquivos YAML e Git
      - **Recursos**
        - Automatizar a implantação de aplicativos
        - Auditar as alterações de configuração
        - Garantir que os ambientes de implantação sejam consistentes e confiáveis
    - OpenShift (Red Hat)
      - Construída em cima do Kubernetes
        - Install, update, and manage the lifecycle of Kubernetes native applications (Operators)
        - Cluster service version (definir metadados)
      - Usado por empresas para criar, implantar e gerenciar aplicativos em contêineres de maneira eficiente e produtiva
      - É uma plataforma de desenvolvimento e implantação de aplicativos baseada em contêineres
      - Fornece recursos adicionais de gerenciamento e automação
      - Facilita a implantação e o gerenciamento de aplicativos em contêineres
      - Recursos de desenvolvimento, integração contínua, implantação contínua e escalabilidade automática
      - Fornece um catálogo de serviços prontos para uso
      - Suporta o desenvolvimento de aplicativos em várias linguagens de programação
      - Permite a integração com ferramentas populares de desenvolvimento e DevOps

## Arquiteturas de infraestrutura em nuvem (cloud computing)

### Características

- Modelo de fornecimento de serviços de computação
- Oferece recursos compartilhados e escaláveis
- Podem ser acessados de qualquer lugar e a qualquer momento

### Escalabilidade

- Capacidade de um sistema crescer para atender a uma demanda crescente,
  mantendo ou melhorando o desempenho
- Tipos
  - Horizontal: adição de mais instâncias ou servidores
  - Vertical: aumento da capacidade de um único recurso, como adicionar mais CPU, RAM, etc.

### Elasticidade

- Capacidade de um sistema de se adaptar dinamicamente às mudanças na carga de trabalho,
  aumentando ou reduzindo os recursos automaticamente conforme necessário

### Flexibilidade

- Capacidade de um sistema de ser adaptado ou modificado para atender a
  diferentes requisitos ou cenários sem grande esforço

### Recursos e serviços oferecidos

- Servidores para processamento
- Armazenamento de dados
- Plataformas de desenvolvimento
- Software e outros serviços relacionados

### Factories (Fábricas)

- Modelo de provisionamento automatizado de recursos de computação
- Permite que os usuários solicitem e configurem recursos de computação conforme suas necessidades
  - Uma fábrica de máquinas virtuais em nuvem
    - Permite que os usuários solicitem e provisionem instâncias virtuais de servidores de forma automatizada
    - Sem a necessidade de configurar fisicamente o hardware subjacente
- Simplificam o processo de criação e gerenciamento de recursos computacionais em nuvem
- Aumenta a escalabilidade e a flexibilidade

### Orientação a serviço

#### Características

- Conceito central na computação em nuvem
- Disponibilização de serviços independentes, escaláveis e reutilizáveis
- Permite que os aplicativos sejam construídos como um conjunto de serviços interconectados e independentes
- Cada serviço realiza uma função específica
- Acessados por outros serviços ou aplicativos por meio de interfaces bem definidas
- Promove a modularidade, o reuso e a flexibilidade na construção de aplicativos em nuvem
- Permite a escalabilidade horizontal e a manutenção simplificada

#### Modelo de serviço em nuvem

##### IaaS (Infraestrutura como Serviço)

- Fornece recursos de infraestrutura computacional virtualizada aos usuários
- Inclui servidores virtuais, redes, armazenamento e outros recursos relacionados
- Os usuários têm controle total sobre o ambiente de computação
- Os usuários são responsáveis pela configuração e gerenciamento dos sistemas operacionais,
  aplicativos e dados
- O provedor de nuvem é responsável por fornecer a infraestrutura subjacente
  - Garante a disponibilidade e escalabilidade dos recursos
- É adequado para organizações que desejam ter controle granular sobre a infraestrutura de computação
- Permite maior flexibilidade e personalização
- Pagamento por demanda/uso

##### SaaS (Software como Serviço)

- Um aplicativo é disponibilizado aos usuários por meio da Internet
- Em vez de adquirir e instalar o software localmente, os usuários acessam o aplicativo remotamente
  - Geralmente por meio de um navegador da web
- O provedor de nuvem é responsável pela manutenção, atualização e operação do software
- Os usuários se concentram em usar o aplicativo sem se preocupar com a infraestrutura subjacente
- Utilizado em diversas áreas
  - Gerenciamento de relacionamento com o cliente (CRM)
  - Colaboração
  - Gerenciamento de projetos
  - Recursos Humanos

##### PaaS (Plataforma como Serviço)

- Fornece uma plataforma de desenvolvimento e implantação de aplicativos aos usuários
- Oferece uma infraestrutura de execução e um conjunto de serviços e ferramentas
- Facilita o desenvolvimento, teste, implantação e gerenciamento de aplicativos
- Os desenvolvedores podem se concentrar na codificação do aplicativo
- O provedor de nuvem se encarrega da infraestrutura, escalabilidade e manutenção do ambiente de execução
- Adequado para equipes de desenvolvimento que desejam
  - Acelerar o ciclo de vida do aplicativo
  - Reduzir a complexidade operacional
  - Se beneficiar da escalabilidade e flexibilidade da nuvem

### Infraestrutura física

#### Zonas de disponibilidade

- Grupos separados de datacenters dentro de uma região
- São próximas o suficiente para ter conexões de baixa latência
- Suficientemente afastadas para reduzir a probabilidade de que mais de uma seja afetada por
  interrupções locais ou pelo clima
- Datacenters conectados por uma rede de alto desempenho com baixa latência

## Padrões de design de microsserviços na nuvem

### SAGA

#### Características

- Sequência de transações que atualiza cada serviço
  e publica uma mensagem ou evento para disparar a próxima etapa de transação
- Transações
  - Uma transação pode ser composta por várias operações
- Ações compensatórias: para contornar falhas

#### Estratégias

- Coreografia
  - Message Broker (mecanismo de mensageria)
- Orquestração
  - Orchestrator
  - Componente: Saga Execution Coordinator (SEC)

### CQRS (Command Query Responsibility Segregation)

#### Características

- Padrão que separa as operações de leitura e atualização de um armazenamento de dados
- Segregação de Responsabilidade de Comando e Consulta

#### Benefícios

- Maximizar o desempenho, a escalabilidade e a segurança
- Permite ao sistema evoluir melhor ao longo do tempo
- Impede que os comandos de atualização causem conflitos

## Automação (Infrastructure as Code)

### Ferramenta Terraform

- Usada para criar, alterar e destruir infraestrutura de nuvem de forma automatizada
- Utiliza a HashiCorp Configuration Language (HCL)
  - Descreve a configuração de sistemas
  - É uma linguagem de configuração declarativa que é fácil de ler e de escrever
  - Permite que você especifique a infraestrutura que deseja criar
  - O Terraform usa essa especificação para criar a infraestrutura em vários provedores
    - Como o AWS, Azure, Google Cloud e VMware vCenter

### Administração e gerenciamento de ambientes de virtualização

#### Características

- Planejamento
  - Recursos necessários
  - Capacidade de armazenamento, a rede e a segurança
- Segurança
  - Implementação de políticas de segurança, patches regulares e medidas de isolamento
- Monitoramento
  - Acompanhar o desempenho das VMs
  - Identificar problemas de recursos
  - Planejar upgrades ou otimizações
- Backup e recuperação
  - Estratégias de backup e recuperação
  - Os dados e as VMs podem ser restaurados em caso de falhas
- Dimensionamento e otimização
  - Acompanhe o uso de recursos
  - Ajuste a alocação de recursos conforme necessário para evitar subutilização ou superutilização
- Treinamento
  - Certifique-se de que os administradores de sistemas estejam treinados e atualizados nas tecnologias de virtualização utilizadas
- Testes e validação
  - Antes de implementar mudanças significativas, realize testes em um ambiente de laboratório para evitar problemas em produção

#### Ferramentas

##### VMWare

- Empresa líder em virtualização e oferece uma variedade de produtos, incluindo o vSphere e o ESXi
- A administração do VMWare envolve
  - Configuração de hosts ESXi
  - Criação e a gestão de VMs
  - Alocação de recursos
  - Monitorização de desempenho
  - Aplicação de políticas de segurança
- Soluções
  - vSphere
    - Suíte de produtos que permite criar e gerenciar máquinas virtuais (VMs) em servidores físicos
    - Possui recursos avançados de gerenciamento
      - Migração ao vivo (vMotion)
      - Balanceamento de carga
      - Recuperação de desastres
  - O ESXi
    - É um hypervisor de tipo 1 (bare-metal)
    - Executa diretamente no hardware do servidor
    - Fornece um ambiente de virtualização de alto desempenho e segurança

##### KVM/Proxmox (Kernel-based Virtual Machine)

- KVM: Tecnologia de virtualização de código aberto incorporada ao kernel do Linux
- A administração do KVM/Proxmox envolve
  - Instalação e configuração do Proxmox VE
  - Criação de VMs e contêineres
  - Gestão de redes virtuais
  - Monitoramento de recursos
- Com KVM e Proxmox, os administradores podem criar VMs e contêineres em servidores Linux
- Aproveita as funcionalidades de virtualização do KVM e as ferramentas de gerenciamento do Proxmox
- Proxmox
  - Plataforma de gerenciamento de virtualização que utiliza KVM e contêineres Linux (LXC)
  - Oferece uma interface web fácil de usar para criar, implantar e gerenciar VMs e contêineres
  - Suporta recursos avançados, como migração em tempo real e backups

## Low-code e no-code

### Utilizam plataformas visuais e intuitivas para facilitar o desenvolvimento de aplicativos

### Benefícios

- Podem ser usadas por usuários que não são desenvolvedores
- Facilitam o desenvolvimento de aplicativos
- Oferecem uma variedade de recursos de segurança, mas não são isentos de falhas
- São geralmente mais rápidas e eficientes do que o desenvolvimento manual
