# Gestão de Configuração e Integração e entrega contínua (CI/CD)

## Características

- Automatizar e agilizar o processo de construção, teste e entrega de software
- Integração frequente do código em um repositório
- Configuração de infraestrutura como código (IaC)
- Pipelines de implantação
  - Compilação, testes, empacotamento e implantação no ambiente de produção

## Controle de versão

### Git

- Sistema de controle de versão distribuído. Diferente do Subversion (SVN), que é um sistema de controle de versão centralizado.
- o Git é o sistema de controle de versão mais flexível, escalável e amplamente adotado.

### CVS (Concurrent Versions System)

- Código Aberto

#### Criar um repositório

```bash
cvs -d <caminho do diretório> init
```

- **Onde:**  
   -d: diretório  
   init: inicializar o repositório

## Ferramentas de orquestração

### Gitlab (similar ao GitHub)

- Gestão de pipelines no Gitlab CI
  - Configuração com o arquivo: gitlab-ci.yml
    - Funcionalidades
      - Scripts to run automatically or manually
      - Include other configuration files and templates
      - Dependencies and caches
      - Sequence and parallel commands
      - Deploy location
    - Seções
      - Variáveis
      - Cache
      - Testes
      - Workflow (run scripts)

### Jenkins (servidor de integração contínua, CI/CD)

- É uma plataforma de automação de código aberto
- Processo automatizado de compilação, teste e implantação
- Utilizada para a construção, teste e implantação contínuos de software
- Permite a criação de pipelines de CI/CD
  - Monitora o repositório de código-fonte
  - Automatizam a compilação de código, execução de testes, empacotamento e implantação em diferentes ambientes
- É extensível e escalável, suporta uma variedade de plugins que facilitam a integração com várias ferramentas e serviços
- Pode ser integrado com outras ferramentas de gerenciamento de configuração, como Puppet e Ansible
- Possui recursos de notificação e geração de relatórios
- É linguagem-agnóstico
- Interface de usuário baseada na web

### AWS CodePipeline

## Ferramentas de gerenciamento de configuração

### Puppet

- Ferramenta de automação de código aberto
- Permite a automação e o gerenciamento de configurações de sistemas e servidores
- Utiliza uma linguagem declarativa para descrever como um sistema deve ser configurado
- Garante que os estados dos sistemas correspondam à definição declarada
- Usado para automatizar tarefas de configuração
- Garante a consistência e facilita a administração de sistemas em larga escala

### Ansible

- Ferramenta de automação de código aberto
- Permite a automação de tarefas de configuração e gerenciamento de servidores
  - Via playbooks
    - composto por plays
      - sequências de tasks que, por sua vez, chamam modules.
- Utiliza uma abordagem baseada em YAML e SSH para descrever as tarefas que devem ser executadas em servidores remotos
- Conhecido por sua simplicidade e facilidade de uso
- Não requer agentes em máquinas remotas
- Suporta a automação de tarefas em sistemas Windows e Unix
- Também pode ser usado para orquestração de aplicativos e provisionamento de infraestrutura

### ShellScript

- É uma linguagem de script que é executada no ambiente de linha de comando de um sistema operacional Unix-like, como Linux ou macOS
- Usado para automatizar tarefas e interagir com o sistema operacional
  - Automatizar backup de arquivos, limpeza de logs ou geração de relatórios
  - Criar scripts de instalação e configuração de aplicativos
  - Monitorar e relatar métricas de sistema
  - Realizar operações de gerenciamento de arquivos e diretórios
  - Administração do sistema, como adicionar/remover usuários ou atualizar permissões
- Permite que você crie scripts para executar uma variedade de ações, desde tarefas simples até complexas
- Ferramenta para administradores de sistemas e desenvolvedores que desejam automatizar tarefas repetitivas

## Jira (gestão de projetos)

- Desenvolvido pela Atlassian
- Objetivos: planejar, rastrear e gerenciar projetos
- Funcionalidades
  - Acompanhamento de tarefas e problemas
    - Criar tarefas, problemas ou histórias de usuário
      - Cada item pode ser atribuído a um membro da equipe
      - Com uma prioridade e um prazo
  - Fluxos de trabalho personalizáveis
    - Definir os estados de um problema ou tarefa
      - Para Fazer
      - Em Progresso
      - Concluído
  - Gerenciamento de backlog
  - Quadros de tarefas
    - [Kanban](</Tecnologia da Informação/Gestão e legislação/Metodologias/Agile Frameworks/Kanban.md>)
      - Visões de cartões
      - Mover as tarefas entre as colunas para indicar o progresso
    - [Scrum](</Tecnologia da Informação/Gestão e legislação/Metodologias/Agile Frameworks/Scrum.md>)
      - Planejar sprints, definir histórias e controlar o progresso do sprint
  - Atribuição de recursos
    - Atribuir membros da equipe a tarefas específicas
  - Relatórios e métricas
    - Acompanhar o progresso
    - Identificar problemas recorrentes
    - Analisar o tempo gasto em diferentes tarefas
  - Integrações e extensões
    - Confluence (para documentação colaborativa)
    - Bitbucket (para controle de versão)
    - Gliffy, Desk.com, Team Calendars, entre outros
    - Ampla gama de extensões e plugins

## Análise estática de código fonte

### Ferramenta SonarQube

- Características
  - Código aberto
  - Desenvolvida pela SonarSource
  - Análise estática de código
    - Analisar o código-fonte de um projeto
    - Fornecer métricas e insights sobre a qualidade do código
    - Monitoramento e melhoria contínua da qualidade do código
    - Identificar problemas
      - De qualidade
      - Vulnerabilidades de segurança
      - Violações de melhores práticas de programação
    - Verificações automáticas que detectam problemas comuns
      - Bugs, vulnerabilidades, duplicações de código
      - Complexidade excessiva, falta de cobertura de testes
      - Violações de convenções de codificação
- Funcionalidades
  - Detecção de problemas de qualidade
    - Informações específicas sobre cada problema
      - Gravidade, localização no código e sugestões de correção
  - Métricas e estatísticas
    - Cobertura de código, complexidade, acoplamento entre componentes
    - Conformidade com padrões de codificação
    - Histórico de qualidade
  - Integração contínua
    - Integrado em pipelines de integração contínua, como o Jenkins
    - A análise de código seja executada automaticamente após cada alteração
  - Suporte as principais linguagens de programação
    - Java, C/C++, C#, Python, JavaScript, TypeScript, PHP e outras
  - Customização e extensibilidade
    - Personalizar as regras de análise de código
    - Plugins e integrações com outras ferramentas de desenvolvimento
  - Interface de usuário intuitiva
