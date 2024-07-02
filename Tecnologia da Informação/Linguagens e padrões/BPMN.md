# BPMN (Business Process Model and Notation)

## Características

- Representação gráfica dos processos de um sistema.

## Boas práticas

- Definir inícios e fins claros.
- Manter claro os cenários primários e alternativos.
- Definir marcos (milestones).
- Usar os padrões BPMN (standards).
- Simplificar diagramas.

## Elementos do Business Process Diagram (BPD)

![Símbolos do BPMN](/Imagens/BPMN-Symbols.png)

_**Imagem:** Símbolos mais comuns do BPMN._

![Diagrama de exemplo](/Imagens/BPMN-Example.png)

_**Imagem:** Exemplo de diagrama BPMN._

### Objetos de fluxo

#### Eventos

- Representados por círculos.
- Início (Start).
- Intermediário (Intermediate).
- Fim (End).

#### Atividades

![Atividades](/Imagens/BPMN-Activity.png)

_**Imagem:** Atividades._

![Marcadores de Atividades](/Imagens/BPMN-Activity-Types.png)

_**Imagem:** Marcadores de Atividades._

![Marcadores de Tarefas](/Imagens/BPMN-Tasks.png)

_**Imagem:** Tipos de Tarefas._

- Representados por retângulos com cantos arredondados.
- Tarefa.
- Sub processo (Quadrado simples com +).
- Transação.
- Chamar atividade.

#### Gateways

![Gateways](/Imagens/BPMN-Gateways.png)

_**Imagem:** Tipos de Gateways._

- Representados por diamantes.
- Exclusive (Exclusivo, X)
  - Representa uma decisão onde apenas uma das saídas é escolhida, com base em uma condição.
  - Apenas uma das sequências de saída será seguida, dependendo da avaliação da condição associada.
- Inclusive (Inclusivo, O)
  - Permite que múltiplas sequências de saída sejam seguidas, com base em condições avaliadas.
  - Mais de uma sequência pode ser escolhida, dependendo das condições definidas.
- Parallel (Paralelo, +)
  - Divide o fluxo de execução em múltiplos caminhos paralelos.
  - Todas as sequências de saída são seguidas simultaneamente, sem depender de condições.
- Complex (Complexo, \*)
  - É um gateway mais flexível que permite modelar condições complexas para a decisão do fluxo.
  - Ele pode ter várias entradas e saídas, permitindo lógicas mais elaboradas.
- Event-Based (Baseado em Evento, Pentágono)
  - É usado para modelar fluxos condicionais com base em eventos.
  - As sequências de saída são ativadas por eventos específicos que ocorrem durante a execução do processo.
  - Círculo duplo com pentágono: apenas Event-Based.
  - Círculo simples com pentágono: Event-Based exclusivo.
  - Círculo simples com +: Event-Based paralelo.

### Objetos de Conexão

- Fluxo de sequência (\_\_\_➤).
- Fluxo de mensagem (◇.....➢).
- Associação (.....➢).

### Swimlanes

- Pools: Represent different organizations or business entities involved in a process.
- Lanes: Subdivide pools to show different roles or departments within an organization.

### Artifacts

![Diagrama de exemplo](/Imagens/BPMN-Data.png)

_**Imagem:** Artefatos de Dados._

- Data Objects: Represent information required or produced by activities.
- Groups: Visually group related activities without affecting the flow.
- Annotations: Provide additional textual explanations.

## ARIS-EPC (Event-driven Process Chain)

- Notação de modelagem de processos de negócios.
- Ênfase em eventos e em transições de estados.
