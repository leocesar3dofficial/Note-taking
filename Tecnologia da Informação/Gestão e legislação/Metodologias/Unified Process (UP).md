# Unified Process ou Processo Unificado (UP)

- Modelo de processo de software baseado no modelo incremental.
- Visa a construção de software orientado a objetos.
- Usa a UML como notação.
- Framework personalizável. Ex: RUP.

- **Princípios**
  - Desenvolvimento iterativo.
  - Baseado em casos de uso.
  - Centrado na arquitetura.

## Processo de planejamento

- **Quem** está fazendo (papel)
  - Desenvolvedor.
- **O quê** (artefato)
  - Documentos produzidos durante o desenvolvimento.
  - Alguns são opcionais.
- **Como** (atividades)
  - Tarefa executada pelo desenvolvedor.
- **Quando** (disciplina)
  - Modelagem de Negócio.
  - Requisitos.
  - Projeto.
  - Implementação.

## Artefatos por disciplina

- **Modelagem de Negócio**
  - Modelo Conceitual.
- **Requisitos**
  - Diagrama de Casos de Uso:
    - Relacionamentos (similaridades entre os casos de uso).
      - **Associação**
        - É um relacionamento entre dois classificadores, como classes ou casos de uso.
        - Descreve as razões para o relacionamento e as regras que o regem.
      - **Generalização ou herança**
        - Indicar que o filho recebe todos os atributos, operações e relacionamentos definidos no pai.
        - Um elemento de modelo (o filho) tem como base outro elemento de modelo (o pai).
        - Utilizados em diagramas de classe, componente, implementação e caso de uso.
      - **Inclusão**
        - Um caso de uso base inclui a funcionalidade de outro caso de uso de inclusão.
        - Reutilização da funcionalidade em um modelo de caso de uso.
      - **Extensão**
        - Especificar que um caso de uso (extensão) estende o comportamento de outro caso de uso (base).
        - Revela detalhes sobre um sistema ou aplicativo que normalmente estão ocultos em um caso de uso.
  - Casos de Uso Textuais.
  - Diagrama de Seqüência.
  - Contratos para operações.
  - Glossário.
- **Projeto**
  - Diagrama de Classes.
  - Diagrama de Colaboração.
  - Diagrama de Pacotes.
  - Documento de Arquitetura.
- **Implementação**
  - Código fonte.

## Fases

- **Concepção**
  - Viabilidade.
  - Escopo.
  - Custos e cronograma (orçamento).
  - Riscos.
  - Arquitetura.
- **Elaboração**
  - Requisitos funcionais (o que o software / sistema deve fazer).
  - Detalhamento da arquitetura.
  - Gerenciamento dos riscos.
- **Construção**
  - O sistema é efetivamente desenvolvido.
  - Deve ser executável.
- **Transição**
  - Entrega ao cliente (produção).
  - Testes e correção de defeitos.

## Fluxos de Trabalho (Workflow)

- **Disciplinas** (realizados a qualquer momento durante o ciclo de desenvolvimento)
  - Requisitos.
  - Análise.
  - Projeto.
  - Implementação.
  - Testes.

## Arquitetura Visão-Modelo 4+1

- Descreve o funcionamento de sistemas de software.

### Visões

1. **Lógica**

   - Se concentra na funcionalidade que o sistema disponibiliza para o usuároi final.
   - Diagramas UML: de classes, de comunicação e de sequencia.

2. **De desenvolvimento ou implementação**

   - O sistema do ponto de vista do programador.
   - Se preocupa com o gerenciamento de projeto.
   - Diagramas UML: de componentes ou pacotes.

3. **De processo**

   - Visualizar as partes dinâmicas do sistema.
   - Explicar os processos e como eles se comunicam.
   - Comportamento do sistema em tempo de execução.
   - Concorrência, paralelismo, distribuição, integração, performance e escalabilidade.
   - Diagramas UML: de atividades.

4. **Física ou de implantação**

   - O sistema do ponto de vista do egenheiro.
   - Topologia dos componentes de software (no contexto físico).
   - Comunicação entre esses componentes.
   - Diagramas UML: de implantação.

5. **De caso de uso (+1)**

   - Descrever a arquitetura através do uso de Diagramas de casos de uso.
   - Cada diagrama descreve sequências de interações entre os objetos e processos.
   - Identificar elementos, ilustrar e validar o design de arquitetura.
