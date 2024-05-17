# Programação Orientada a Objetos (POO)

## Definição

- Paradigma que organiza o código em objetos que interagem entre si.
- Ajuda a estruturar e projetar sistemas baseados em entidades.
- As entidades possuem propriedades e comportamentos específicos.
- Estrutura para projetar sistemas complexos.
- Promove reutilização de código, modularidade, legibilidade e manutenibilidade.
- Implementada em diversas linguagens de programação, como Java, C++, Python e C#.

## Conceitos

### Classe

- É um modelo ou estrutura que define o comportamento e as propriedades de um objeto.
- Uma classe serve como um plano ou template para criar objetos.
- Ela encapsula os dados (propriedades) e comportamentos (métodos).

- **Tipos de classe**

  1. **Base ou Superclasse**
  
    - Classe da qual outras classes derivam.
    - Fornece um conjunto de funcionalidades comuns que são herdadas por suas subclasses.
    - Por exemplo, uma classe "Animal" pode ser uma superclasse para classes como "Cachorro", "Gato", etc.

  2. **Classe Derivada ou Subclasse**
  
    - Classe que herda atributos e métodos de uma classe base.
    - Pode adicionar novos comportamentos ou modificar os existentes.
    - Por exemplo, a classe "Cachorro" pode ser uma subclasse da classe "Animal".

  3. **Classe Abstrata**
    
    - Classe que não pode ser instanciada por si só.
    - É projetada para ser herdada por outras classes.
    - Pode conter métodos abstratos, ou seja, métodos que devem ser implementados pelas subclasses.
    - Por exemplo, uma classe "Veículo" pode ser abstrata, com métodos como "acelerar" e "frear" que devem ser implementados por suas subclasses concretas.

  4. **Classe Concreta**
  
    - Classe que pode ser instanciada diretamente.
    - Fornece implementações para todos os métodos abstratos herdados de suas superclasses.
    - Por exemplo, uma classe "Carro" pode ser uma classe concreta derivada da classe abstrata "Veículo".

  5. **Classe Final**
  
    - Classe que não pode ser estendida, ou seja, não pode ter subclasses.
    - Garantir que uma classe não seja alterada ou estendida em futuras implementações.
    - Por exemplo, em Java, você pode declarar uma classe como final.

  6. **Classe Estática**
  
    - Classes que não podem ser instanciadas e contêm apenas membros estáticos, como métodos e variáveis estáticas.
    - Usadas para agrupar funcionalidades relacionadas que não precisam ser instanciadas.

### Objeto

- É uma instância de uma classe.
- Representa uma entidade do mundo real com características específicas.
- Possui estado (valores das propriedades) e comportamento (ações que ele pode realizar).

### Relacionamento

- Refere-se à interação entre objetos.
- Permitem que os objetos cooperem e troquem informações para realizar tarefas complexas.

#### Tipos

- **Associação**
  - Um objeto está relacionado ao outro de alguma forma.
  - Essa relação pode ser de qualquer tipo e pode ser unidirecional ou bidirecional.
  - Os objetos associados podem existir independentemente um do outro.
  - Não implica em uma dependência forte entre eles.
  - Exemplo: uma classe de "Professor" pode estar associada a uma classe de "Aluno".
- **Agregação**
  - Descreve uma relação de "tem um" entre dois objetos.
  - Um objeto é o dono e o outro é uma parte ou componente desse objeto.
  - A parte ou componente pode existir independentemente do objeto proprietário.
  - Exemplo: uma classe de "Casa" pode ter uma agregação com uma classe de "Cômodo" (a casa possui cômodos, mas os cômodos podem existir separadamente).
- **Composição**
  - Os objetos estão intimamente ligados.
  - Têm uma relação de "todo-parte".
  - O objeto parte só pode existir como parte do objeto todo e não pode existir independentemente dele.
  - Quando o objeto todo é destruído, as partes também são destruídas.
  - Exemplo: uma classe de "Carro" pode ter uma composição com uma classe de "Motor" (o motor só pode existir dentro do contexto do carro).
- **Herança**

### Herança

- Permite que uma classe herde características de outra classe.
- Permite a reutilização de código, estabelece a hierarquia entre as classes e facilita a extensibilidade.
- **Subclasse ou classe derivada:** a classe que herda.
- **Superclasse ou classe base:** a classe da qual ela herda.

### Polimorfismo

- Capacidade de um objeto se comportar de várias formas.
- Permite que um objeto de uma classe base possa ser substituído por um objeto de uma classe derivada.
- O polimorfismo permite que diferentes objetos respondam de maneira específica a uma mesma mensagem ou chamada de método.

### Encapsulamento

#### Características

- É o conceito de agrupar dados e os métodos que operam nesses dados em uma única unidade ou classe.
  - Controla o acesso aos dados e comportamentos de uma classe.
  - Permite um melhor controle sobre o acesso e modificação dos dados.
  - Limita o impacto de mudanças internas na classe em outras partes do código.
  - Restringe o acesso externo.
  - Protege sua integridade.
- Oculta os detalhes internos de implementação de um objeto.
- Expõe apenas as interfaces necessárias para interagir com ele.
  - Garante que a interação com a classe ocorra por meio de uma interface bem definida.
    - Interface é um contrato que define um conjunto de métodos que uma classe deve
      implementar
      - Descreve o comportamento que uma classe deve ter, mas não fornece a implementação
      - As classes que implementam uma interface devem fornecer suas próprias implementações
      - Maneira de alcançar a abstração, modularidade, flexibilidade e a reutilização de código, independentemente de suas heranças
      - Usadas para atingir o conceito de polimorfismo
  - Getters e setters dão acesso aos atributos protegidos de forma segura.
- Promove a segurança e a manutenção do código.
  - Promove a modularidade, reutilização de código e facilita a manutenção do programa.

#### Níveis de acesso

- **Private/Privado (acesso apenas para a classe)**
  - É o mais restrito e impõe restrições ao acesso aos membros da classe.
  - São acessíveis apenas dentro da própria classe.
  - Eles não podem ser acessados por outras classes, objetos ou subclasses.
  - É usado para ocultar os detalhes de implementação.
  - Fornece segurança e integridade aos dados da classe.
  - **Métodos privados**
    - Usados para implementar a lógica interna da classe.
    - Não devem ser acessados diretamente por outros objetos.
- **Protected/Package-Private/Protegido (padrão)**
  - Restringe o acesso aos membros da classe para a própria classe e suas subclasses (classes derivadas).
    - Acesso pelas sub-classes e pacote.
  - Não são acessíveis fora da hierarquia de herança da classe.
  - Podem ser acessados pelos próprios métodos da classe e pelas subclasses.
  - Permite que os membros protegidos sejam usados internamente pela classe.
  - As subclasses herdam e modificam seu comportamento.
- **Public/Público (todos têm acesso)**
  - É o mais acessível.
  - Não impõe restrições ao acesso aos membros da classe.
  - Os membros declarados como públicos são acessíveis por qualquer código.
  - Os métodos públicos geralmente são usados para expor a interface pública da classe.
  - Permite que outros objetos interajam com ela.
