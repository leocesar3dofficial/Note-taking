# Design de Software

## Princípios para o Desenvolvimento de Software

### 12 Fatores (12 Factories)

1. Código-base e infraestrutura separados
2. Configuração externa
3. Processos isolados
4. Dados armazenados de forma durável
5. Recursos compartilhados
6. Processos de implantação automatizados
7. Processos de monitoramento automatizados
8. Processos de diagnóstico automatizados
9. Processos de recuperação automatizados
10. Processos de testes automatizados
11. Processos de documentação automatizados
12. Processos de atualização automatizados

### SOLID

#### Características

- Design orientado a objetos
- Aplicáveis a outros paradigmas de programação, como a programação imperativa e funcional
- Independem de linguagem de programação

#### Princípios

- **Single Responsibility Principle (SRP):**

  - A class should have only one reason to change, be responsible for one thing

- **Open/Closed Principle (OCP):**

  - Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification
  - It must be easily extended with new features without having to modify the existing code

- **Liskov Substitution Principle (LSP):**

  - A subtype must be substitutable for its supertype
  - If a class A is a subtype of class B, then any code that uses class B should be able to use class A without any problems

- **Interface Segregation Principle (ISP):**

  - Segregação de Interface
  - Uma interface não deve exigir que seus clientes implementem métodos que eles não usam
  - Aplicado criando interfaces menores e mais especializadas
  - Torna o código mais modular, flexível, reusável, fácil de entender e manter

- **Dependency Inversion Principle (DIP):**
  - High-level modules should not depend on low-level modules
  - High-level and low-level modules should depend on abstractions
  - The high-level modules do not depend on the low-level modules directly
  - They should depend on abstractions that represent the functionality of the low-level modules

### GRASP (General Responsibility Assignment Software Patterns)

#### Características

- Conjunto de princípios de design de software
- Ajudam a determinar a atribuição de responsabilidades em um sistema orientado a objetos

#### Padrões

- **Controller (Controlador):**

  - Uma classe, geralmente chamada de "Controller",
  - Deve ser responsável por receber e encaminhar as solicitações do sistema para outras classes
  - Comumente usado em padrões arquiteturais como o MVC (Model-View-Controller), atuando como intermediário entre as interfaces de usuário e o modelo

- **Expert (Especialista):**

  - Uma responsabilidade deve ser atribuída à classe que possui as informações necessárias para cumpri-la de maneira eficiente
  - A classe que possui o conhecimento e os dados necessários para realizar uma tarefa deve ser responsável por ela
  - Ajuda a manter o baixo acoplamento entre classes e promove um design mais coeso e modular

- **Creator:**

  - Responsável por atribuir a responsabilidade de criar uma instância de uma classe a outra classe

- **High Cohesion:**

  - Responsável por manter as responsabilidades de uma classe altamente relacionadas e coesas
  - Evita que ela faça muitas coisas diferentes

- **Low Coupling:**

  - Responsável por manter as classes independentes umas das outras
  - Reduzir as dependências entre elas

- **Polymorphism:**

  - Atribuir a responsabilidade de executar um comportamento específico a uma classe que pode ser substituída por outras

- **Pure Fabrication:**

  - Cria uma classe fictícia para delegar responsabilidades e evitar que uma classe acumule muitas responsabilidades

- **Indirection:**
  - Atribui a responsabilidade de mediar entre outros componentes ou serviços
