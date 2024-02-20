# Padrão de Projeto de Software (Design Patterns)

## Padrões da GoF (Gang of Four, autores do livro sobre Design Patterns)

### Classificações/Famílias de Padrões

#### De Criação

##### Características

- Abstraem e/ou adiam o processo de criação dos objetos
- Usados em sistemas que dependem mais da composição de objetos do que herança

##### Tipos

- **Factory Method (criar)**

  - Permite que uma classe delegue a responsabilidade de criar objetos para outra classe

- **Abstract Factory**

  - Agrupa fábricas de objetos que têm um tema comum

- **Builder (construir)**

  - Permite que um objeto seja construído em etapas

- **Prototype (copiar)**

  - Permite que um objeto seja copiado para criar um novo objeto

- **Singleton**
  - Restringe a criação de objetos para uma única instância

#### Estruturais

##### Características

- Definem a forma como classes e objetos são compostos para formar estruturas maiores

##### Tipos

- **Class Adapter**

  - Permite que classes com interfaces incompatíveis trabalhem juntas, envolvendo sua própria interface em torno de uma classe já existente

- **Bridge**

  - Desacopla uma abstração de sua implementação para que ambas possam variar independentemente

- **Composite (compor)**

  - Permite que objetos sejam compostos em uma hierarquia de objetos

- **Decorator**

  - Adiciona/sobrescreve dinamicamente o comportamento em um método existente de um objeto

- **Facade**

  - Fornece uma interface simplificada para um grande conjunto de código

- **Flyweight**

  - Reduz o custo de criar e manipular um grande número de objetos semelhantes

- **Proxy**

  - Fornece um espaço reservado para outro objeto controlar o acesso, reduzir custos e simplificar a complexidade

#### Comportamentais

##### Características

- Definem os algoritmos e atribuições de responsabilidades entre os objetos

##### Tipos

- **Chain of Responsibility**

  - Delega comandos para uma cadeia de objetos de processamento

- **Command**

  - Cria objetos que encapsulam ações e parâmetros

- **Interpreter**

  - Implementa uma linguagem especializada

- **Iterator (iterar)**

  - Permite que os objetos de uma coleção sejam iterados

- **Mediator**

  - Permite um acoplamento flexível entre classes, sendo a única classe que tem conhecimento detalhado de seus métodos

- **Memento**

  - Fornece a capacidade de restaurar um objeto para seu estado anterior (desfazer)

- **Observer**

  - É um padrão de publicação/assinatura, permitindo que vários objetos observadores vejam um evento

- **State**

  - Permite que um objeto altere seu comportamento quando seu estado interno muda

- **Strategy**

  - Permite a seleção dinâmica de um algoritmo de uma família de algoritmos em tempo de execução

- **Template Method**

  - Define o esqueleto de um algoritmo como uma classe abstrata, permitindo que suas subclasses forneçam um comportamento concreto

- **Visitor**
  - Separa um algoritmo de uma estrutura de objetos, movendo a hierarquia de métodos para um objeto

## Anti-Padrões (Anti-Patterns)

### Características

- São soluções comuns para problemas recorrentes que geralmente são ineficazes
- Podem ser altamente contraproducentes
- São o oposto dos padrões de design, que são soluções comprovadamente eficazes para problemas de design de software
- O termo "anti-padrão" foi cunhado em 1995 pelo programador de computador Andrew Koenig
- É um processo, estrutura ou padrão de ação comumente usado que, apesar de inicialmente parecer uma resposta apropriada e eficaz a um problema, tem mais consequências ruins do que boas
- Outra solução existe para o problema que o anti-padrão está tentando resolver
- Essa solução é documentada, repetível e comprovadamente eficaz, enquanto o anti-padrão não é
- Documentar anti-padrões pode ser uma maneira eficaz de analisar um espaço de problemas e capturar conhecimento especializado

### Code Smell

#### Características

- É qualquer característica no código-fonte de um programa que possivelmente indica um problema mais profundo
- Determinar o que é e o que não é um Code Smell é subjetivo e varia de acordo com a linguagem, desenvolvedor e metodologia de desenvolvimento
- O termo foi popularizado por Kent Beck em WardsWiki no final dos anos 1990
- Apresentado no livro "Refactoring: Improving the Design of Existing Code" de Martin Fowler em 1999
- É também um termo usado por programadores ágeis
- Uma violação de princípios fundamentais de design e qualidade de código
- Geralmente não são bugs
- Não são tecnicamente incorretos e não impedem o programa de funcionar
- Indicam fraquezas no design que podem retardar o desenvolvimento ou aumentar o risco de bugs ou falhas no futuro

#### Tipos

- **Big Ball of Mud**

  - Falta de design ou arquitetura em um sistema de software, resultando em um código confuso e difícil de manter

- **God Class**

  - Uma única classe lida com todo o controle em um programa em vez de o controle ser distribuído por várias classes

- **Magic Numbers**

  - Um valor único com um significado inexplicável ou várias ocorrências que poderiam ser substituídas por uma constante nomeada

- **Poltergeists**
  - Classes controladoras efêmeras que só existem para invocar outros métodos em classes
