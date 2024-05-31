# Frameworks e Toolkits

## Front-end

- Angular (Javascript)
- React (Javascript)
- Vue (Javascript)
- jQuery (Javascript)
- Laravel (PHP)

## Back-end

### Spring (ecossistema Java)

#### Spring Boot (bootstrap ou inicialização de aplicativos)

- Conceito
  - Fornece um conjunto de ferramentas e convenções para criar aplicativos autônomos e prontos para produção.
  - Construído sobre o framework Spring (Java).
  - Torna o desenvolvimento mais rápido e simplificado.
- Recursos
  - **Configuração Conveniente**
    - Oferece configuração automática com base nas dependências adicionadas ao projeto.
    - Reduz a necessidade de configuração manual.
  - **Embedded Web Servers**
    - Inclui servidores web incorporados (como o Tomcat, Jetty ou Undertow).
    - Executa aplicativos sem a necessidade de configurações externas.
  - **Gerenciamento de Dependências**
    - Gerencia automaticamente as versões das dependências.
    - Facilita a resolução de conflitos e a manutenção de bibliotecas.
  - **Monitoramento e Métricas**
    - Oferece suporte a monitoramento e métricas integrados.
    - Torna mais fácil a implantação e o gerenciamento de aplicativos em produção.
- Casos de Uso
  - Desenvolvimento rápido de aplicativos, microsserviços, APIs RESTful e aplicativos da web.
  - Simplifica a configuração, aumentando a produtividade dos desenvolvedores.

#### Spring MVC (Model-View-Controller)

- Recursos
  - **DispatcherServlet**
    - Componente central do Spring MVC que recebe todas as solicitações HTTP.
    - Encaminha para os Controladores apropriados com base em mapeamentos definidos.
  - **Anotações**
    - Utiliza anotações Java, como @Controller, @RequestMapping, @ModelAttribute e @ResponseBody.
    - Define Controladores, mapeamentos de URL e outras configurações.
  - **Resolutores de Visualização**
    - Oferece resolutores de visualização para escolher a View apropriada.
  - **Validação de Dados**
    - Validação de dados usando anotações como @Valid e @ModelAttribute.
    - Garante que os dados de entrada do usuário sejam válidos.
  - **Integração com Spring**
    - Pode ser integrado com outros módulos do Spring (como Spring Security e Spring Boot).

#### Spring Cloud (ferramentas para sistemas distribuídos)

- Conceito
  - Conjunto de ferramentas e bibliotecas no ecossistema Spring.
  - Facilita a construção de sistemas distribuídos e aplicativos em nuvem.
    - Promove a independência de estado de serviço.
      - Capacidade de um serviço funcionar de forma autônoma e sem depender do estado de outros serviços para realizar suas operações.
  - Fornece abstrações e soluções para problemas comuns de desenvolvimento de microsserviços.
- Recursos
  - **Descoberta de Serviços**
    - Inclui componentes como Eureka e Consul para descobrir e registrar serviços em ambientes distribuídos.
  - **Balanceamento de Carga**
    - Oferece soluções para balanceamento de carga, como Ribbon.
    - Distribui o tráfego eficientemente entre instâncias de serviços.
  - **Configuração Centralizada**
    - O Config permite a gestão centralizada de configurações em ambientes distribuídos.
  - **Resiliência**
    - Bibliotecas como Hystrix para lidar com resiliência em sistemas distribuídos (circuit breakers e fallbacks).
  - **Gateway API**
    - Fornece um gateway API para encaminhar solicitações para os serviços apropriados.
- Casos de Uso
  - Desenvolvimento de sistemas baseados em microsserviços.

### JBoss Seam (Java, servidor de aplicações)

- Simplifica o desenvolvimento de aplicações web enterprise.
- Integração de tecnologias como JSF, JPA, EJB e BPM.
- Gerenciamento de estado declarativo para simplificar o gerenciamento de estado de aplicação.
- Menos popular do que frameworks mais recentes.

### Quarkus (Java)

- Plataforma stackless para a construção de aplicações web e microservices.
- Suporte nativo para Kubernetes e containers.
- Início rápido e baixo consumo de memória.
- Integração com tecnologias populares como JAX-RS, Hibernate e Spring.
- Menos maduro do que JBoss Seam.

### Django (Python)

- Framework Python de alto nível para desenvolvimento web.
- Sistema de templates.
- Gerenciamento de objetos relacionais integrado.
- Ampla biblioteca de componentes reutilizáveis.

### Flask (Python)

- Microframework Python para desenvolvimento web.
- Baixa dependência de bibliotecas externas.
- Ideal para aplicações web simples e APIs.
- Menos recursos integrados do que frameworks completos.
- Requer mais código para implementar recursos comuns.
- Comunidade menor do que Django.

### JPA (Java, interface comum para frameworks ORM)

- Based on Hibernate on its inception.
- Jakarta Persistence API (formerly Java Persistence API).

### Hibernate (Java, Mapeamento Objeto-Relacional ou Object-Relational Mapping (ORM))

- Hibernate 6.2 usa a estratégia otimista de bloqueio por padrão
  - Assume que várias transações podem ser concluídas sem afetar outras.
  - Mais eficiente, mas propenso a falhas.
- Pode usar a estratégia pessimista de bloqueio
  - Garante que as linhas de dados não sejam alteradas por outras transações.
- Hibernate Envers
  - Módulo do Hibernate ORM para auditoria e versionamento para entidades JPA.
  - Permite manter um histórico de alterações em entidades.
  - Funciona com o Hibernate e JPA, podendo ser usado onde o Hibernate é usado.
  - **Como usar**
    1. Adicionar a dependência do hibernate-envers ao seu projeto.
    2. Anotar suas entidades com @Audited.
    3. O Envers criará automaticamente tabelas de auditoria e manterá um registro de alterações.
  - Fornece uma API poderosa para recuperar informações de auditoria de suas entidades.
  - Casos de uso incluem rastreamento de alterações em entidades de usuário, configuração e histórico de pedidos.

### JUnit (Java, teste unitário)

### .NET Core

### [Node.js (Javascript)](/Tecnologia%20da%20Informação/Back-end/Tools/Node.js.md)

### gRPC (Google Remote Procedure Call)

- Conceito:
  - Framework de código aberto desenvolvido pelo Google.
  - Facilita a comunicação entre sistemas distribuídos.
  - Usado em cenários de microsserviços.
  - Baseado no protocolo HTTP/2.
  - Utiliza o protocolo de serialização de dados protobuf (Protocol Buffers).
    - Define interfaces de serviço e mensagens.
- Características:
  - **RPC (Remote Procedure Call)**
    - Permite que os aplicativos chamem funções em servidores remotos de maneira semelhante a uma chamada local.
  - **Suporte a várias linguagens de programação**
    - Facilita a comunicação entre componentes escritos em linguagens diferentes.
  - **Streaming bidirecional**
    - Permite a criação de fluxos de dados bidirecionais entre clientes e servidores.
    - Adequado para cenários como chat em tempo real e transmissão de eventos.
  - **Segurança integrada**
    - Possui suporte para autenticação e criptografia.

### Flutter

- Kit de desenvolvimento de software (SDK) open-source criado pelo Google.
- Construir aplicações nativas compiladas para mobile, web e desktop a partir de uma única base de código.
- Permite criar interfaces de usuário bonitas e responsivas.
- Utiliza a linguagem de programação Dart.

### R

- Linguagem e ambiente de software livre para computação estatística e gráficos.
- Usada em estatística, bioinformática, e ciência de dados para análise de dados e visualização.
- Características:
  - Multiparadigma: orientada a objetos e programação funcional.
  - Fracamente tipada.
- Possui uma vasta gama de pacotes para:
  - Análises estatísticas básicas.
  - Modelos complexos de aprendizado de máquina.

### Scala

- Combina características de programação funcional e orientada a objetos.
- Roda na Java Virtual Machine (JVM).
- Conhecida por sua concisão e expressividade.
- Usada em desenvolvimento de sistemas de alto desempenho e big data.
  - Frameworks como Apache Spark.

### COBOL (Common Business-Oriented Language)

- Robustez e capacidade de lidar com grandes volumes de transações.
- Usada em sistemas legados de bancos, governos e grandes empresas.
- Embora antiga, continua a ser crucial em muitos sistemas críticos pelo mundo.

#### Divisões (DIVISION)

1. DATA DIVISION
  - PICTURE (ou PIC)

## Desenvolvimento Móvel (Mobile)

### Android (Kotlin)

- Características
  - Linguagem preferencial para o desenvolvimento de aplicativos Android.
  - **Interface de Usuário Rica**
    - Oferece uma variedade de componentes de interface de usuário.
  - **Acesso a Recursos do Dispositivo**
    - Câmera, GPS, sensores e armazenamento.
  - **Integração com Serviços do Google**
    - Google Maps, autenticação e notificações na plataforma Android.
  - **Ferramentas de Desenvolvimento**
    - Android Studio é a principal IDE.
      - Oferece recursos de depuração, emuladores e uma variedade de ferramentas para simplificar o desenvolvimento.
      - Permite construir apps com código parcialmente em Java e parcialmente em Kotlin, sem restrições.

### Swift (iOS)

- Características
  - Linguagem oficial da Apple para o desenvolvimento de aplicativos iOS.
  - Combina elementos de C e Objective-C.
  - **Ecossistema Fechado**
    - Proporciona maior controle de hardware e segurança.
  - **Interface de Usuário Polida**
    - Desenvolvedores podem criar aplicativos que se integram perfeitamente à estética.
  - **Desenvolvimento Nativo**
    - Usa ferramentas e APIs nativas da Apple, resultando em aplicativos de alto desempenho.
  - **Ferramentas de Desenvolvimento**
    - Xcode é a IDE padrão para desenvolvimento iOS.
      - Oferece um ambiente de desenvolvimento completo com emuladores, depuração e uma interface de construção de interfaces gráficas.

### Objective-C (iOS e macOS)

- Orientada a objetos que adiciona capacidades de Smalltalk à linguagem C.
- Foi a principal linguagem usada pela Apple para desenvolvimento de software para iOS e macOS antes do Swift.
- Ainda é relevante para a manutenção de código legado e integração com bibliotecas antigas.

### Ionic

- Características
  - Framework de código aberto.
  - Permite o desenvolvimento de aplicativos móveis multiplataforma usando tecnologias web, como HTML, CSS e JavaScript.
  - **Desenvolvimento Multiplataforma**
    - Baseado em Angular.
  - **Interface de Usuário Personalizável**
    - Flexibilidade para personalizar a aparência e o comportamento por meio de CSS e componentes reutilizáveis.
  - **Ferramentas de Desenvolvimento**
    - Ionic CLI e bibliotecas como Capacitor ou Cordova para acessar recursos nativos do dispositivo.
