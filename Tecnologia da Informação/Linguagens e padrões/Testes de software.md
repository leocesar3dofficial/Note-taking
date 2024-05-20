# Testes de software

## Tipos

### Automatizados

#### Ponta a ponta

- Executar o fluxo de execução principal de forma completa.
- Ambiente semelhante ao do usuário final.

#### Unitários (Unit Testing)

- Verifica se as partes do software funcionam de maneira isolada das demais partes do sistema.
- Teste realizado pelo próprio desenvolvedor.

- **Princípios FIRST**

  - **Fast (Rápidos):** realizar testes unitários frequentemente.

    - A execução precisa ser rápida, em milissegundos.
    - Se necessário deve-se dividir uma suíte de testes em chunks (pedaços) menores.

  - **Independent (Independentes):** Em nenhum momento crie dependência entre os testes unitários.

    - A ordem de execução dos testes de unidade é irrelevante. O que possibilita, inclusive, execuções paralelas.
    - Use o DRY (Don’t Repeat Yourself) para eliminar dependência entre testes.

  - **Repeatable (Determinísticos):** os testes unitários devem sempre ter o mesmo resultado.

    - Uma vez que os testes ora passam e ora falham, estes são chamados de Flaky (alarme falso).
    - Segundo um estudo do Google (Flaky Tests at Google and How We Mitigate Them) [2016], aproximadamente 16% dos testes são passíveis de Flaky Tests.

  - **Self-Validating (Auto-verificáveis/explicativos):** o resultado deve binário, ou melhor, auto-explicativo (passou/falhou). Desta forma, o resultado pode ser verificado e interpretado.

    - Um relatório contendo evidências (screenshots, se possível) é uma ferramenta que agiliza a verificação de possíveis falhas nos testes executados.

  - **Timely (Previamente escritos):** escrever os testes antes deles serem executados no código.

    - No início eles irão e devem falhar. No entanto, ao decorrer da implementação do código de produção, os testes começão a passar (caso realmente esteja de acordo com o esperado).

- **SUT (System Under Test)**

  - Parte do sistema que queremos testar.

- **Dublês de teste (Test Doubles)**

  - Dummy

    - Objetos que são passados, mas não utilizados.
    - Apenas usados para preencher lista de parâmetros.

  - Fake

    - Tem implementação, mas usa algum atalho que os torna inadequados para produção.
    - Ex. banco de dados na memória.

  - Stubs

    - Retorna respostas prontas para chamadas.
    - Não responde nada fora do que está programado.

  - Spies

    - São como stubs mas registram algumas informações em como foram chamados.
    - Ex. serviço de e-mail que registra quantas mensagens foram enviadas.

  - Mocks

    - Objetos pré-programados formam uma especificação das chamadas que se espera que recebam.

    - **Benefícios**

      - Verificar o comportamento de objetos que dependem de outros objetos.
      - Verificar o comportamento de objetos que são lentos para executar.
      - Tornar os testes unitários mais rápidos e eficientes.
      - Melhorar a qualidade do código.

### Funcionais

- Verificar se um sistema ou aplicativo cumpre as especificações de seus requisitos funcionais.
- Se concentram em testar se o software realiza as ações e funções conforme o esperado.
- Realizados do ponto de vista do usuário.
- Se concentram em validar se a funcionalidade do software atende às necessidades do usuário.
- Incluem a entrada de dados, a execução de ações e o exame dos resultados para garantir que eles estejam em conformidade com o que foi definido nos requisitos.
- Realizados após os testes de unidade e de integração e podem ser automatizados para facilitar a execução repetida.

### Aceitação

- Determinar se o software está pronto para ser entregue ao cliente ou usuário final.
- Validar se o software atende aos critérios de aceitação acordados com o cliente ou partes interessadas.
- Realizado pelo usuário final.

#### Tipos

1. Do Cliente

   - Os clientes ou usuários finais estão envolvidos para verificar se o software atende às suas expectativas e necessidades.
   - Podem incluir testes de funcionalidade, usabilidade, desempenho e conformidade com os requisitos acordados.

2. Aceitação do Sistema

   - Conduzidos pela equipe de desenvolvimento ou de testes.
   - Verificar se o sistema atende aos critérios de aceitação definidos.
   - Podem incluir testes de integração, desempenho, segurança e conformidade com os padrões de qualidade.

## Técnicas para Aplicação de Testes de Software

### Caixa-Branca (White-Box Testing)

- Os testadores têm conhecimento detalhado do código-fonte do software.
- Projetam casos de teste com base na estrutura interna do código, incluindo caminhos de execução, condições de decisão e lógica interna.
- Objetivo: Identificar falhas lógicas, erros de programação e verificar a cobertura de código.

#### Exemplos de técnicas

- Teste de Caminho de Controle.
- Teste de Caminho de Dados.
- Teste de Cobertura de Código.

### Caixa-Preta (Black-Box Testing)

- Os testadores não têm conhecimento do código-fonte subjacente.
- Concentram-se em testar o software com base nas entradas e saídas esperadas, sem considerar a implementação interna.
- Objetivo: Validar a funcionalidade de acordo com os requisitos e identificar defeitos de usabilidade.

#### Exemplos de técnicas

- Teste de Requisitos.
- Teste de Equivalência.
- Teste de Caixa de Erro.

### Testes de Integração

- Verificar se os diferentes componentes de um sistema funcionam bem juntos quando são integrados.
- **Objetivo:** Identificar problemas que possam surgir quando os componentes individuais do software são combinados e interagem entre si.
- Concentram-se na **comunicação entre partes** do sistema.
- Incluem testes de regressão para garantir que as alterações nos componentes integrados não tenham introduzido defeitos ou problemas inesperados.
- **Tipos**
  - Interfaces com o usuário
  - Cenários de uso

#### Integração Contínua

- Os desenvolvedores integram constantemente seus códigos no repositório principal, acionando automaticamente testes de integração.
- Ajuda a identificar problemas de integração logo após a adição de novos códigos.

#### Ferramentas de Teste

- Existem ferramentas de automação de testes de integração que facilitam a execução e a análise dos resultados dos testes de integração.

#### Tipos

- Big Bang Integration

  - Todos os componentes são integrados simultaneamente, e o sistema é testado como um todo.
  - É menos incremental e pode ser mais desafiador para identificar problemas específicos.

- Top-Down Integration

  - Os módulos principais são integrados primeiro, e os módulos mais detalhados são adicionados progressivamente.
  - Permite uma abordagem mais gradual.

- Bottom-Up Integration

  - Os módulos mais detalhados são integrados primeiro, e os módulos principais são adicionados posteriormente.

### Testes de Regressão

- Garantir que as alterações / mudanças recentes no software não tenham introduzido novos defeitos ou afetado negativamente as funcionalidades existentes.
- É útil em cenários de desenvolvimento ágil, onde as alterações frequentes são feitas.
- Pode ser automatizado para economizar tempo e recursos.

## Padrões de Qualidade

**Atributos de qualidade:** segurança, compreensibilidade e portabilidade.

### TDD (Test Driven Development)

- Desenvolvimento Orientado a Testes.
- É uma prática de desenvolvimento de software.
- Enfatiza a criação de testes automatizados antes de escrever o código de produção para cada funcionalidade.

#### Etapas

1. Escrever um teste automatizado que falhe.
2. Implementar o código necessário para fazer o teste passar.
3. Refatorar o código para melhorar sua qualidade.

- Garante que o código seja testado de forma abrangente e contínua durante o processo de desenvolvimento.
- Gera um código confiável, modular e de fácil manutenção.
- O desenvolvedor se concentra nos requisitos e comportamentos esperados do sistema.

### DDD (Domain Driven Design)

- Design Orientado a Domínio.
- É uma metodologia de design de software.
- Cria sistemas complexos baseados no entendimento do domínio do problema.
- Foco principal no domínio do negócio, em vez de se concentrar apenas nos aspectos técnicos.

#### O domínio é modelado em uma linguagem ubíqua

- Compartilhada entre os especialistas do domínio e os desenvolvedores.
- O design do software é orientado pela estrutura do domínio.
- Usa conceitos como entidades, agregados, serviços de domínio e objetos de valor.
- O objetivo é alinhar o código com a realidade do domínio, tornando-o expressivo, compreensível e fácil de manter.
- Promove a separação em camadas.
  - Camada de domínio: contém a lógica central do negócio.
  - Camadas de aplicação e infraestrutura: tratam dos aspectos técnicos.
- Utilizado em conjunto com outras práticas ágeis, como o TDD.

### BDD (Behavior Driven Development)

- Desenvolvimento Orientado a Comportamento.
- É uma metodologia de desenvolvimento de software.
- Melhora a comunicação e colaboração entre os membros da equipe.
  - Desenvolvedores, especialistas do domínio e gerentes de produto.
- Garante que o software desenvolvido atenda aos requisitos do negócio e forneça valor aos usuários finais.

#### Cenários de uso

- Requisitos e comportamentos expressos em linguagem natural.
- Escritos em formato de histórias ou especificações executáveis.
- Compreendidos por todas as partes interessadas do projeto.
- São automatizados usando ferramentas de teste.
  - Permite que sejam executados como testes automatizados.
  - Garante que o software seja desenvolvido de acordo com o comportamento esperado.
  - Os testes servem como documentação viva do sistema.
- Promove a colaboração contínua entre as partes interessadas.
- Definição conjunta de cenários de uso.
- Implementação e execução dos testes automatizados.

## Métricas e estimativas de software

### 1. Linhas de Código (LOC, Lines Of Code)

- Conta o número de linhas de código-fonte em um programa.
- Métrica limitada, pois não reflete a complexidade ou qualidade do código.

### 2. Pontos de Função (Function Points)

#### Características

- Funcionalidades implementadas, sob o ponto de vista do usuário.
- Orientada para a análise do impacto das funcionalidades do software.
- Utiliza-se de estimativas.
- Independe da tecnologia utilizada.
- Baseia-se na visão do usuário.
- Existem ferramentas automatizadas e métodos que podem auxiliar no cálculo.

#### Fórmula

$$ \text{Pontos de Função (PF)} = \sum_{i=1}^{n} \text{Complexidade}\_i \times \text{Peso}\_i $$

**Onde:**

- $ n $ é o número de componentes.
- $ \text{Complexidade}\_i $ é a complexidade de cada componente.
- $ \text{Peso}\_i $ é o peso atribuído a cada nível de complexidade (baixa, média, alta).

#### Tabela de pesos

| Componente                   | Baixa | Média | Alta |
| ---------------------------- | ----- | ----- | ---- |
| EE (Entrada Externa)         | 3     | 4     | 6    |
| CE (Consulta Externa)        | 3     | 4     | 6    |
| SE (Saída Externa)           | 4     | 5     | 7    |
| ALE (Arquivo Lógico Externo) | 5     | 7     | 10   |
| ALI (Arquivo Lógico Interno) | 7     | 10    | 15   |

#### O que é quantificado

- Interações entre o usuário e o sistema (externa) e sua complexidade (baixa à altamente complexa):
  - **Entradas**
    - Os dados vão do ambiente externo para o sistema.
    - Exemplo: Um formulário preenchido pelo usuário.
  - **Saídas**
    - Os dados vão do sistema para o ambiente externo.
    - Exemplo: Um relatório gerado pelo sistema e enviado ao usuário.
  - **Consultas**
    - O sistema responde a uma pergunta ou consulta do usuário sem alterar dados.
    - Exemplo: Uma pesquisa ao sistema para obter informações. Gera uma saída.
- Arquivos lógicos (não contêm dados).
  - Representação ou visualização de um ou mais arquivos físicos (multiformatos).
- Interfaces do usuário de um sistema.

### 3. Velocidade (Velocity)

- Utilizada em metodologias ágeis, como o Scrum.
- Estima a quantidade de trabalho que uma equipe realiza em um determinado tempo.
- Calculada com base na quantidade de histórias de usuário concluídas em iterações anteriores.

### 4. Estimativas baseadas em tempo

- Estima o tempo necessário para concluir uma tarefa ou projeto.
- Técnicas de estimativa.
  - Análoga: compara com projetos anteriores.
  - Paramétrica: usa modelos matemáticos.
  - De Três Pontos: considera estimativas otimistas, pessimistas e prováveis / realistas.

### 5. Análise de Story points

- Compara a complexidade e o esforço de uma tarefa com outras já realizadas.
- Estimativa relativa.

### 6. Análise de Pontos de Função

- Funcionalidades que um sistema deve realizar.
- Análise dinâmica.
  - É possível identificar exceções que não foram tratadas.

### 7. Análise de Ponto de Função Ajustada (APFA)

- Combina os pontos de função com fatores de ajuste.
- Leva em consideração aspectos como complexidade técnica, desempenho, reutilização de componentes, entre outros.
- Oferece uma estimativa mais refinada e precisa.

### 8. Análise de Custo-Benefício ou Retorno Sobre Investimento (ROI, Return On Investment)

- Envolve a análise dos custos envolvidos no desenvolvimento em relação aos benefícios, receita esperados.
- Determina se o projeto é viável e a tomar decisões informadas sobre investimentos.

### 9. Análise estática de código

#### Características

- Revisão e a avaliação do código-fonte de um programa de software sem a necessidade de executá-lo.
- Identificar problemas, erros, vulnerabilidades de segurança, violações de padrões de codificação e más práticas.
- **Walk-through**
  - Revisão manual do código-fonte, documentação e de outros artefatos por membros da equipe.

#### Detecção de Erros

- Identificar erros no código, como variáveis não inicializadas, uso incorreto de operadores, loops infinitos e outros problemas de lógica.

#### Melhoria da Qualidade

- Garantir que o código siga padrões de codificação, seja coeso e fácil de entender, e siga as melhores práticas.

#### Segurança

- Identificar vulnerabilidades de segurança no código, como potenciais pontos de injeção de SQL, vulnerabilidades de Cross-Site Scripting (XSS) e muito mais.

#### Automatização / Automação

- Linters e analisadores de código, são frequentemente usadas para automatizar o processo de revisão do código.
- Ferramentas:
  - ESLint.
  - Prettier.

### 10. Teste de Requisitos Não Funcionais (RNFs)

#### Características

- Requisitos que não estão diretamente relacionados às funcionalidades do software, mas sim a características que afetam o:
  - Desempenho / Eficiência.
  - Escalabilidade.
  - Segurança.
  - Usabilidade.
  - Portabilidade.
    - Afeta negativamente a eficiência.
  - Outros aspectos que não envolvem a lógica do sistema.
- Envolve a validação e a verificação desses requisitos.

#### Classificação dos Requisitos Não Funcionais

- **Requisitos de produtos:** Requisitos que especificam o comportamento do produto.
  - Requisitos de usabilidade (facilidade de uso).
  - Requisitos de eficiência. Ex.: o sistema deverá processar n requisições por um determinado tempo.
  - Requisitos de confiabilidade. Ex.: o sistema deverá ter alta disponibilidade, p.exemplo, 99% do tempo.
  - Requisitos de portabilidade. Ex.: o sistema deverá executar em qualquer plataforma.
- **Requisitos organizacionais:** Requisitos decorrentes de políticas e procedimentos corporativos.
  - Ex. padrões, infraestrutura,etc.
  - Requisitos de entrega. Ex.: um relatório de acompanhamento deverá ser fornecido toda segunda-feira.
  - Requisitos de implementação. Ex.: o sistema deverá ser desenvolvido na linguagem Java.
  - Requisitos de padrões. Ex.: uso de programação orientada a objeto sob a plataforma A.
- **Requisitos externos:** Requisitos decorrentes de fatores externos ao sistema e ao processo de desenvolvimento.
  - Ex. requisitos de interoperabilidade, legislação,localização geográfica, etc.
  - Requisitos de interoperabilidade. Ex.: o sistema deverá se comunicar com o banco SQL Server.
  - Requisitos éticos. Ex.: o sistema não apresentará aos usuários quaisquer dados de cunho privativo.
  - Requisitos legais. Ex.: o sistema deverá atender às normas legais, tais como padrões, leis, etc.

#### Tipos de testes para Requisitos Não Funcionais

- **Teste de Carga**

  - Avaliar o desempenho do sistema sob carga máxima ou condições de pico.
  - Garantir que ele possa lidar com um grande número de usuários ou transações sem falhas ou degradação significativa do desempenho.

- **Teste de Estresse**

  - Leva o sistema além dos limites normais para avaliar seu comportamento em condições extremas.
  - Isso pode incluir estressar a capacidade de processamento, memória ou rede para entender como o sistema se comporta sob pressão.

- **Teste de Segurança**

  - Envolve verificar se os requisitos de segurança do sistema estão sendo atendidos.
  - Identificar e corrigir vulnerabilidades e garantir a integridade e a confidencialidade dos dados.
  - Dynamic Application Security Testing (DAST).
    - Detect vulnerabilities by actually performing attacks.
    - Covers security weaknesses and vulnerabilities present in an application.
    - It is a black-box test.
    - Análise em tempo de execução.

- **Teste de Usabilidade**

  - Avalia a facilidade de uso do sistema, incluindo a interface do usuário, a acessibilidade e a experiência do usuário para garantir que atenda aos requisitos de usabilidade.

- **Teste de Desempenho**

  - Avalia o desempenho do sistema em termos de tempo de resposta, tempo de carregamento e outros aspectos para garantir que ele atenda aos requisitos de desempenho especificados.

### 11. Revisão e programação por pares

## Frameworks para testes automatizados

### JUnit (Java)

- **Descrição**
  - É um dos frameworks de teste mais conhecido e usado.
- **Características**
  - Suporta anotações para definir testes e configurações.
  - Oferece assertivas para verificar resultados esperados.
  - Integração com IDEs populares, como Eclipse e IntelliJ IDEA.
  - Suporte para testes parametrizados e suítes de testes.
- **Módulos**
  - Plataforma JUnit, JUnit Jupiter e JUnit Vintage.
- **Anotações e recursos**
  - @Test: é possível especificar um método de teste.
  - assertEquals: um método de asserção localizado normalmente no interior dos métodos de testes.
    - Faz o método de teste falhar ou ter sucesso.

### Mockito (Java)

- **Descrição**

  - É uma biblioteca usada para criar e configurar objetos simulados (mocks) em testes unitários.

- **Características**

  - Permite criar mocks de objetos e definir seus comportamentos.
  - Facilita a verificação de interações entre objetos em testes.
  - Usado para testes de isolamento e para simular dependências externas.

### Selenium

- **Descrição**

  - É uma ferramenta de automação de testes de interface de usuário (UI) de aplicativos web.

- **Características**

  - Suporta várias linguagens de programação, incluindo Java, Python e C#.
  - Permite a automação de ações de navegação em navegadores web.
  - Usado para testar aplicativos web em diferentes navegadores e sistemas operacionais.
  - WebDriver API pode ser utilizada para a automação de aplicações Web com a linguagem Java e com a API de testes JUnit.

### Jest (JavaScript)

- **Descrição**

  - É um framework de teste de JavaScript usado para testes unitários, de integração e de componentes de interface de usuário.

- **Características**

  - Fornecido com ferramentas integradas para testar códigos JavaScript, com suporte a módulos ES6 / ES7.
  - Execução de testes paralelos.
  - Integração com frameworks, como o React.

### Cucumber

- **Descrição**

  - Escrita de testes de aceitação usando linguagem natural (Gherkin).

- **Características**

  - Os cenários de teste são escritos em linguagem natural.
  - Facilita a colaboração entre desenvolvedores e partes interessadas.
  - Compatível com várias linguagens de programação.
  - Automação de testes de aceitação e integração contínua.

### Karate DSL (Domain-Specific Language)

- **Descrição**

  - É uma biblioteca de automação de teste de API.
  - Fornece uma sintaxe simplificada (DSL) e semelhante à linguagem natural.

- **Características**

  - Criação de cenários de teste para APIs REST em uma sintaxe fácil de ler e escrever.
  - Validação, geração de dados e relatórios.
  - Testa APIs independentemente da linguagem de programação.
