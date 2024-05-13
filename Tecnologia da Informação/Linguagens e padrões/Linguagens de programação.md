# Linguagens de programação

## Implementações

### JavaScript

#### Características

- Alto nível, interpretada e orientada a objetos.
- Usada para desenvolvimento web e criação de aplicações front-end interativas.
- Suporta programação assíncrona e manipulação do DOM (Document Object Model).
- Possui uma vasta quantidade de bibliotecas e frameworks disponíveis.

- Declarations
  - Hoisting (elevar):
    - Variable can be declared after it has been used.
    - Only var can be used before declared, but may return undefined.
    - let variables will return ReferenceError.
    - const variables will show as a syntax error.

#### Pontos fortes

- Fácil integração com HTML e CSS.
- É uma linguagem onipresente no desenvolvimento web.
- Pode ser executada em qualquer navegador.
- Suporte à programação assíncrona com Promises e async/await.

#### Pontos fracos

- Pode ser inconsistente em diferentes navegadores.
- A tipagem dinâmica pode levar a erros difíceis de serem detectados.
- É necessário ter cuidado para evitar problemas de segurança, como injeção de código.

### TypeScript

#### Características

- É um superset do JavaScript que adiciona tipagem estática opcional.
- Compila para JavaScript, permitindo executar em qualquer ambiente onde o JavaScript seja suportado.
- Oferece recursos avançados de orientação a objetos e programação funcional.
- Melhora a experiência de desenvolvimento ao fornecer recursos de autocompletar, validação de tipos e refatoração.

#### Pontos fortes

- Ajuda a identificar erros de código em tempo de desenvolvimento.
- Aumenta a escalabilidade de projetos grandes.
- Compatível com as bibliotecas e frameworks existentes em JavaScript.

#### Pontos fracos

- A curva de aprendizado pode ser um pouco mais íngreme para desenvolvedores acostumados apenas com JavaScript.
- Requer um passo extra de compilação antes de executar o código.

### Java

#### Características

- Orientada a objetos, robusta, coleta de lixo automática e altamente portável.
- Possui uma vasta biblioteca padrão e uma grande comunidade de desenvolvedores.
- É amplamente usada no desenvolvimento de aplicativos empresariais e em sistemas embarcados.
- Suporta programação concorrente e é conhecida por sua segurança.

#### Pontos fortes

- Portabilidade, pode ser executada em diferentes sistemas operacionais e arquiteturas.
- Forte suporte para programação em rede e desenvolvimento de servidores.
- Excelente desempenho e escalabilidade.

#### Pontos fracos

- Requer uma quantidade significativa de código para realizar tarefas simples (boilerplate).
- Pode ser mais verbosa em comparação com outras linguagens.

#### Conversão de valores (Casting)

- Para String:
  `String y = String.valueOf(x)`

### PHP

#### Características

- Linguagem de script do lado do servidor voltada para o desenvolvimento web.
- Fácil integração com HTML e bancos de dados.
- Adoção em sistemas de gerenciamento de conteúdo, como WordPress e Drupal.
- Suporte para diferentes protocolos de rede e manipulação de arquivos.

#### Pontos fortes

- Rápida prototipação e desenvolvimento ágil.
- Documentação e comunidade ativas.
- Suporte nativo para interação com bancos de dados.

#### Pontos fracos

- Pode ser propensa a vulnerabilidades de segurança se não for usada corretamente.
- A falta de coerção de tipos pode levar a erros difíceis de serem detectados.

### Python

#### Características

- Alto nível, interpretada e multiparadigma.
- Sintaxe clara e legível, facilitando a leitura e o aprendizado.
- Vasta biblioteca padrão e uma ampla gama de bibliotecas de terceiros disponíveis.
- Usada em ciência de dados, aprendizado de máquina, automação, desenvolvimento web e mais.

#### Pontos fortes

- Ênfase na legibilidade e produtividade do desenvolvedor.
- Grande comunidade e documentação abrangentes.
- Forte suporte para ciência de dados e aprendizado de máquina.
- Multiplataforma, sendo executada em diversos sistemas operacionais.

#### Pontos fracos

- Pode ter desempenho relativamente mais lento em comparação com linguagens compiladas.
- Escalabilidade limitada para projetos muito grandes.

#### Funções comuns

- Listas
  - range(start, stop, step)

### C#

#### Características

- Orientada a objetos, moderna e desenvolvida pela Microsoft.
- Parte do framework .NET, amplamente usada para desenvolvimento de aplicativos Windows e web.
- Oferece suporte a programação assíncrona, tratamento de exceções e uso de componentes.
- Possui uma sintaxe semelhante ao Java e ao C++.

#### Pontos fortes

- Integração com a plataforma .NET e uma vasta biblioteca padrão.
- Suporte para desenvolvimento de aplicativos Windows.
- Suporte para desenvolvimento web com o framework ASP.NET.

#### Pontos fracos

- Menos popular fora do ecossistema da Microsoft.
- Menor quantidade de bibliotecas e frameworks em comparação com outras linguagens.

### Go (GoLang)

#### Características

- Compilada, concorrente e com coleta de lixo automática.
- Focada em simplicidade, legibilidade e desempenho.
- Projetada para desenvolvimento de software escalável e de alto desempenho.
- Suporta programação concorrente nativamente com goroutines e canais.
- Comumente usada no backend e para a computação em nuvem.
  - Exemplos: Docker, Kubernetes e Istio.

#### Pontos fortes

- Desempenho excepcional e baixo consumo de recursos.
- Concorrência facilitada pela sintaxe e recursos nativos.
- Compila para um único arquivo executável, facilitando a distribuição de aplicativos.

#### Pontos fracos

- Possui uma curva de aprendizado um pouco íngreme para desenvolvedores iniciantes.
- Menos bibliotecas disponíveis em comparação com linguagens mais estabelecidas.

## Elementos estruturais

### Sub-rotinas (ou funções, ou métodos em linguagens orientadas a objetos)

#### Classificação

- **Com base no propósito**
  - De processamento de dados.
    - Funções que lidam com o processamento, transformação e manipulação de dados.
  - De entrada/saída (I/O).
    - Funções que tratam da entrada e saída de dados, como leitura e gravação de arquivos ou interação com dispositivos de entrada/saída.
  - De interface de usuário (UI).
    - Funções responsáveis pela criação e gerenciamento da interface do usuário, como janelas, botões e campos de entrada.
  - De comunicação.
    - Funções que lidam com a comunicação entre sistemas, como conexões de rede ou protocolos de comunicação.

- **Com base no escopo**
  - Locais
    - Funções que são definidas e usadas apenas em um determinado escopo, como em um módulo ou classe.
  - Globais
    - Funções que podem ser acessadas de qualquer lugar no programa.

- **Com base na visibilidade**
  - Sub-rotinas públicas
    - Funções que podem ser chamadas de qualquer lugar no programa.
  - Sub-rotinas privadas
    - Funções que só podem ser chamadas de dentro do escopo onde foram definidas.

- **Com base na recursividade**
  - Sub-rotinas recursivas
    - Funções que podem chamar a si mesmas, geralmente usadas em algoritmos recursivos.
  - Sub-rotinas não recursivas
    - Funções que não chamam a si mesmas.

- **Com base na passagem de parâmetros**
  - Sub-rotinas por valor
    - Parâmetros são passados como cópias dos valores originais.
      - Qualquer modificação feita na cópia dentro da sub-rotina não afetará os dados originais.
      - É uma forma segura, mas pode ser ineficiente para grandes conjuntos de dados.
  - Sub-rotinas por referência
    - Parâmetros são passados como referências aos valores originais.
      - Permite que a sub-rotina acesse e modifique o objeto original.
      - As alterações são refletidas fora da sub-rotina.
      - É uma forma segura de passar dados e é comumente usada em linguagens como C++ com referências
        ou em linguagens orientadas a objetos com passagem de objetos.
  - Sub-rotinas por endereço (ou Ponteiro)
    - Parâmetros são passados como endereços de memória.
      - Permite que a sub-rotina acesse e modifique diretamente os dados na memória principal.
      - É uma forma eficiente de passar dados, mas pode ser perigosa, pois a sub-rotina pode inadvertidamente corromper a memória.

- **Com base na complexidade**
  - Sub-rotinas simples
    - Funções que realizam tarefas simples e diretas.
  - Sub-rotinas complexas
    - Funções que realizam tarefas mais complexas e envolvem várias etapas ou decisões.

- **Com base na reusabilidade**
  - Sub-rotinas genéricas
    - Funções que podem ser reutilizadas em diferentes contextos.
  - Sub-rotinas específicas
    - Projetadas para fins específicos e não facilmente reutilizáveis em outras partes do programa.
