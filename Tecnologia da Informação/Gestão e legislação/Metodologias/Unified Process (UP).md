# Unified Process ou Processo Unificado (UP)

- Modelo de processo de software baseado no modelo incremental
- Visa a construção de software orientado a objetos
- Usa a UML como notação
- Framework personalizável. Ex: RUP
- **Princípios**
  - Desenvolvimento iterativo
  - Baseado em casos de uso
  - Centrado na arquitetura

## Processo de planejamento

- **Quem** está fazendo (papel)
  - Desenvolvedor
- **O quê** (artefato)
  - Documentos produzidos durante o desenvolvimento
  - Alguns são opcionais
- **Como** (atividade)
  - Tarefa executada pelo desenvolvedor
- **Quando** (disciplina) atividades
  - Modelagem de Negócio
  - Requisitos
  - Projeto
  - Implementação

### Artefatos por disciplina

- **Modelagem de Negócio**
  - Modelo Conceitual
- **Requisitos**
  - Diagrama de Casos de Uso
  - Casos de Uso Textuais
  - Diagrama de Seqüência
  - Contratos para operações
  - Glossário
- **Projeto**
  - Diagrama de Classes
  - Diagrama de Colaboração
  - Diagrama de Pacotes
  - Documento de Arquitetura
- **Implementação**
  - Código fonte

## Fases

- **Concepção**
  - Viabilidade
  - Escopo
  - Custos e cronograma (orçamento)
  - Riscos
  - Arquitetura
- **Elaboração**
  - Requisitos funcionais (o que o software / sistema deve fazer) 
  - Detalhamento da arquitetura
  - Gerenciamento dos riscos
- **Construção**
  - O sistema é efetivamente desenvolvido
  - Deve ser executável
- **Transição**
  - Entrega ao cliente (produção)
  - Testes e correção de defeitos

## Arquitetura Visão-Modelo 4+1

- Descrever o funcionamento de sistemas de software

### Visões

1. **Lógica**
    - Se concentra na funcionalidade que o sistema disponibiliza para o usuároi final
    - Diagramas UML: de classes, de comunicação e de sequencia
2. **De desenvolvimento ou implementação**
    - O sistema do ponto de vista do programador
    - Se preocupa com o gerenciamento de projeto
    - Diagramas UML: de componentes ou pacotes
3. **De processo**
    - Permite visualizar as partes dinâmicas do sistema 
    - Explicar os processos e como eles se comunicam
    - Foco no comportamento do sistema em tempo de execução
    - Concorrência, paralelismo, distribuição, integração, performance e escalabilidade
    - Diagramas UML: de atividades
4. **Física ou de implantação**
    - O sistema do ponto de vista do egenheiro
    - Topologia dos componentes de software (no contexto físico)
    - Comunicação entre esses componentes
    - Diagramas UML: de implantação
5. **De caso de uso (+1)**
    - Descreve a arquitetura através do uso de Diagramas de casos de uso
    - Cada diagrama descreve sequências de interações entre os objetos e processos
    - Identificar elementos, ilustrar e validar o design de arquitetura


