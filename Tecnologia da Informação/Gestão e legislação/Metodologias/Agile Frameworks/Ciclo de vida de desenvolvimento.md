# Ciclo de Vida de Desenvolvimento de Software (SDLC)

## Características

- Processo econômico e rápido
- **DevSecOps**
  - Segurança é uma parte integral
  - Integrar testes de segurança em todas as etapas
- **Objetivo**
  - Minimizar os riscos do projeto
- O gerenciamento eficiente do desenvolvimento de software se concentra nos 4 Ps: pessoas; produto; processo; e, projeto.

## Benefícios

- Transparência
- Estimativa, planejamento e programação eficientes
- Melhor gerenciamento de riscos e estimativa de custos
- Entrega sistemática do software e maior satisfação do cliente

## Etapas

1. **Planejamento**
   - Análise do custo-benefício
   - Especificação de requisitos
     - Item de backlog épico
       - É um grande requisito que pode ser dividido em vários requisitos menores (histórias de usuário)
       - Usados para organizar e gerenciar grandes requisitos
       - Facilita a comunicação entre as partes interessadas
   - Programação, estimativa e alocação de recursos
2. **Projeto**
   - Análise dos requisitos para identificar as melhores soluções
3. **Implementação**
4. **Teste**
5. **Implantação**
6. **Manutenção**

## Modelos

- **Cascata ou Waterfall**
  - Características
    - Fases sequenciais, sistemáticas e inflexíveis
    - Recomendado para pequenos projetos
    - Modelo de processo prescritivo e sequencial mais antigo
    - Resultados previsíveis ou preditivo
  - **Fases**
    - Especificação dos requisitos do cliente
    - Planejamento
    - Modelagem
    - Construção
    - Entrega
    - Suporte contínuo
- **Modelo V**
  - Características
    - Melhoria e derivação do modelo em cascata
    - Fases paralelas de desenvolvimento e teste
  - **Fases**
    - Lado esquerdo: Verificação (requisitos sejam atendidos) <-> lado direito: Validação (produto certo)
    - Especificação de requisitos <-> Teste de Aceitação
    - Projeto de alto nível (análise) <-> Teste de Sistema
    - Projeto detalhado (Arquitetura) <-> Teste de Integração
    - Codificação <-> Teste de Unidade
- **Iterativo**
  - Entrega de um subconjunto de requisitos até a conclusão do projeto
  - Os requisitos podem ser alterados entre as iterações
  - Multi-cascata ou Mini-cascatas
    - Combina elementos do modelo cascata, aplicado de maneira iterativa
    - Essa filosofia incremental também é usada em processos ágeis
  - **Desvantagens**
    - Alteração do escopo
    - Subestimação de recursos
- **Espiral**
  - Pequenos ciclos repetidos + fluxo sequencial linear do modelo cascata
  - Orientado por riscos
    - Todos os riscos mitigados -> próxima etapa iniciada
  - Criação de protótipos em cada ciclo
  - Adequado para projetos grandes e complexos
- **Ágil**
  - Ciclos iterativos com menor duração de tempo
  - Avalia continuamente os requisitos, planos e resultados
  - Identifica e soluciona problemas mais rapidamente
  - Envolvimento de todos os interessados
  - **Desvantagens**
    - Alteração excessiva do escopo

## Técnicas/cerimônias para colaboração e integração do time ágil

### SoS (Scrum of Scrums)

- Cerimônia que coordena o trabalho entre múltiplas equipes Scrum que trabalham no mesmo produto ou projeto.

**Como funciona:**
- **Representantes**: Cada equipe Scrum escolhe um representante (geralmente o Scrum Master) para participar da reunião SoS.
- **Frequência**: As reuniões SoS são realizadas regularmente, como diariamente ou algumas vezes por semana.
- **Formato**: Cada representante compartilha:
  - O que sua equipe fez desde a última reunião.
  - O que sua equipe planeja fazer até a próxima reunião.
  - Bloqueadores que precisam ser resolvidos e que podem impactar outras equipes.
- **Objetivo**: Resolver impedimentos que afetam múltiplas equipes e garantir a sincronização e alinhamento entre elas.

### PO Sync (Product Owner (PO) Sync)

- Reunião regular usada em escalas maiores do Agile, como o SAFe (Scaled Agile Framework), para garantir que todos estejam alinhados durante o Program Increment (PI).

**Como funciona:**
- **Participantes**: Inclui Product Managers, Product Owners, Release Train Engineers, e outras partes interessadas.
- **Frequência**: Geralmente, semanal ou bissemanal.
- **Objetivo**: Revisar o progresso do PI, ajustar as prioridades se necessário e resolver qualquer problema que possa impactar o sucesso do PI.

### Planning (Sprint Planning)

- Cerimônia onde a equipe define o trabalho a ser feito durante o próximo sprint.

**Como funciona:**
- **Participantes**: Inclui toda a equipe de desenvolvimento, Product Owner e Scrum Master.
- **Objetivo**: 
  - **Parte 1**: O Product Owner apresenta as prioridades do backlog e explica o que precisa ser feito.
  - **Parte 2**: A equipe discute e define as tarefas que podem ser concluídas durante a sprint, criando o sprint backlog.
- **Resultado**: Um sprint backlog com histórias de usuário e tarefas detalhadas.

### Review (Sprint Review)

- Cerimônia onde a equipe apresenta o trabalho concluído durante o sprint.

**Como funciona:**
- **Participantes**: Inclui a equipe de desenvolvimento, Product Owner, Scrum Master e stakeholders.
- **Objetivo**: 
  - Demonstrar as funcionalidades completadas.
  - Receber feedback dos stakeholders.
  - Ajustar o backlog com base no feedback recebido.
- **Resultado**: Feedback construtivo e ajustamentos no backlog.

### Retrospectiva (Sprint Retrospective)

- Cerimônia onde a equipe reflete sobre o sprint recém-concluído e discute melhorias para os próximos sprints.

**Como funciona:**
- **Participantes**: Toda a equipe de desenvolvimento, Product Owner e Scrum Master.
- **Objetivo**: 
  - Identificar o que funcionou bem.
  - Identificar o que não funcionou.
  - Planejar ações de melhoria.
- **Resultado**: Um plano de ação para melhorar processos e práticas na próxima sprint.

### Daily (Daily Stand-up)

- Reunião curta, realizada diariamente, onde a equipe sincroniza suas atividades.

**Como funciona:**
- **Participantes**: Toda a equipe de desenvolvimento, Product Owner e Scrum Master.
- **Formato**: Cada membro responde a três perguntas:
  - O que fiz ontem?
  - O que farei hoje?
  - Há algum impedimento no meu caminho?
- **Duração**: Normalmente, 15 minutos.

### PI Planning (Program Increment Planning)

- Evento de dois dias que acontece no início de cada Program Increment (PI) no SAFe, envolvendo todos os times do Agile Release Train (ART).

**Como funciona:**
- **Participantes**: Inclui todas as equipes do ART, Product Managers, System Architects, e outras partes interessadas.
- **Objetivo**: 
  - Definir os objetivos do PI.
  - Criar um plano de iteração detalhado.
  - Identificar dependências entre equipes e resolver conflitos.
- **Resultado**: 
  - Objetivos do PI definidos.
  - Backlog de features priorizado.
  - Plano de iteração acordado.
