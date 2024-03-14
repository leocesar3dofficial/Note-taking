# Tecnologia e Linguagem para Bancos de Dados

## Conceitos

- **Sistema Gerenciador de Banco de Dados (SGBD)**

  - Database Management System (DBMS)
  - Interface entre os programas e os dados armazenados em um servidor

- **Integridade referencial**

  - Controle de alteração de dados de tabelas relacionadas
  - Respeitar às regras de negócio estabelecidas entre as tabelas
  - Segue o modelo de Entidade Relacionamento (ER)

- **Dicionário de dados**
  - Conjunto de arquivos que contém os dados descritivos das estruturas do BD
  - Metadados

## História

- 1960, IBM, primeiro conceito de banco de dados relacionais
- 1980, Oracle, criação do SQL - Structured Query Language, linguagem script
- 1988, Microsoft/Sybase, criou o Microsoft SQL Server
- 1995, MySQL, código aberto
- 1997, PostgreSQL

## Produtos no mercado

- **Proprietários:** Oracle, SQL Server e Access da Microsoft, DB2 da IBM
- **Código aberto:** PostgreSQL, MySQL

## Modelos

- **Tabular (ou plano):** como uma planilha eletrônica
- **Em rede:** ponteiros ou números indexadores entre tabelas
- **Em rede no modo hierárquico:** estrutura em árvore entre tabelas
- **Relacional (mais difundido)**
  - Dados estruturados
  - Integridade referencial
    - Chave primária
      - Dados únicos sem repetição
      - Principal forma de relacionamento entre tabelas
    - Chave secundária
    - Chave estrangeira
      - Valor de uma chave primária de outra tabela (estabelece o relacionamento)
- **Não relacional (No-SQL, modelo emergente)**
  - **Características**
    - Não implementa o conceito do modelo entidade-relacionamento (E-R)
    - Os dados são armazenados de forma não estruturada
    - Não existe integridade referencial
    - Melhor solução para dados que mudam regularmente, heterodoxos e voláteis, como no Big Data
    - Podem ser indexados por chaves múltiplas, grafos, etc.
  - **Classificação**
    - **Orientados a colunas (BigTable)**
      - Produtos: Google BigTable, Hadoop, HyperTable, Cassandra, etc.
    - **Orientados a Grafos**
      - A interconectividade dos dados são mais relevantes que os dados em si
      - **Elementos**
        - Nós (vértices ou nodes)
        - Relacionamentos (arestas)
        - Propriedades (atributos)
      - Produtos: Neo4J, Infinite Graph, HyperGraphDB, etc.
    - **Orientados a documentos**
      - Atributos multivalorados
      - Não possuem esquema (estrutura pré-formatada)
      - É possível fazer referência a outro documento dentro da mesma coleção por meio de um campo específico
        - O qual contém o endereço do documento referenciado
      - Produtos: MongoDb, CouchDB, RavenDb, etc.
    - **Esquema chave/valor**
      - Tabelas de hash distribuídas
      - Armazena objetos indexados por chaves
      - Produtos: DynamoDb, Riak, Azure Table Storage, Redis, Tokyo Cabinet, etc.

## Funcionalidades

- **Controle de acessos concorrentes**
  - Fila de transações
- **Política de permissões e restrições de acesso**
- **Rastreabilidade**
  - Rastrea o histórico de acessos e atualizações de cada dado (log)
- **Backup, Restore e Portabilidade**
  - Backup manual ou automático
  - Restore seletivo, apenas algumas tabelas
- **Storage e Backup**
  - Administração e operação de serviços de arquivamento
    - Gestão de sistemas e infraestrutura destinados a armazenar dados por longos períodos de tempo
    - Necessário para cumprir requisitos legais ou regulamentares de retenção de dados
    - Os dados estejam organizados, protegidos contra perdas e acessíveis quando necessário
      - Configuração de políticas de retenção de dados
      - Monitoramento do desempenho do sistema
      - Implementação de mecanismos de backup para garantir a integridade dos dados ao longo do tempo.
      - **Tipos de RAID (Redundant Array of Independent Disks)**
        - **RAID 0:** striping
        - **RAID 1:** espelhamento
        - **RAID 5:** distribuição com paridade 
          - Arranjo de discos que usa a paridade para garantir a segurança e redundância dos dados.
          - Espelhamento só ocorre no RAID 1 e 10.
          - $$ EspaçoDisponível = (NúmeroDeDiscos - 1) \times CapacidadeDoMenorDisco $$
        - **RAID 6:** distribuição com paridade dupla
        - **RAID 10:** combina espelhamento e striping
  - Implantação e administração de soluções de proteção e de recuperação de dados contra-ataques cibernéticos
    - Preocupação fundamental na administração de armazenamento e backup, dada a crescente ameaça de ciberataques, como ransomware
    - Envolve a configuração de firewalls, sistemas de detecção de intrusões, criptografia e medidas de segurança
    - Implementação de práticas de backup robustas, como backups regulares
      - Armazenamento offline seguro
      - Planos de recuperação de desastres para garantir a capacidade de recuperar os dados após um ataque
  - Implantação e administração de serviços de nuvem e multicamada
    - A migração para serviços de nuvem é uma tendência na gestão de armazenamento e backup
    - Envolve a implantação e administração de serviços em nuvem, como AWS, Azure ou Google Cloud
    - Abordagem multicamada
      - Combinação de diferentes níveis de armazenamento, como armazenamento local, em nuvem privada e em nuvem pública, para otimizar custos e desempenho
    - Gerenciar a alocação de recursos na nuvem
    - Monitorar a segurança e a conformidade dos dados na nuvem
    - Estabelecer estratégias eficazes de recuperação de dados na nuvem

- **Interface interativa e assistentes**

  - Comando de prompt ou Command Line Interface (CLI)

- **Drivers para diversas linguagens e ambientes de programação**
- **Gatilhos (ou triggers)**
- **Cursors (Non-Scrollable e Non-Updatable)**
- **Stored procedures**

  - Executa instruções SQL, DDL, DML e DCL diretamente no servidor de BD
  - **Vantagens**
    - Transferir a responsabilidade do processamento para o servidor de BD
    - Simplificar a manutenção do aplicativo
    - Maior performance
  - **Desvantagens**
    - Cada DB possui características próprias para as stored procedures
    - Cria ponto único de fragilidade de segurança

- **Functions ou funções como: COUNT() e SUM()**
- **Visões (views)**

  - **Definição**
    - Resultado de uma query (consulta) SQL
    - Pode ser utilizada como filtro para atualização dos dados nas tabelas-base
  - **Vantagens**
    - Mostrar colunas distintas para diferentes usuários
    - Utilizada com um conjunto de tabelas unidas com JOIN ou UNION
  - **Desvantagens**
    - Perda de performance desprezível

- **Structured Query Language (SQL), linguagem de script**
  - **Linguagem de Definição de Dados (Data Definition Language, DDL)**
    - Linguagem interpretada, autônoma
    - Comandos que permitem a criação e modificação das estruturas
      - `CREATE` (criar)
        ```sql
        CREATE TABLE funcionarios (
          Id INTEGER PRIMARY KEY,
          Nome CHAR(50) null,
          Sobrenome CHAR(75) not null,
          Aniversario DATE null
        );
        ```
      - `DROP` (eliminar)
        ```sql
        DROP TABLE funcionarios;
        ```
      - `ALTER` (alterar)
        - Exemplo 1
          ```sql
          ALTER TABLE funcionários ADD Salario INTERGER;
          ```
        - Exemplo 2
          ```sql
          ALTER TABLE `funcionarios`
          ADD CONSTRAINT `DeptoFunc`
          FOREIGN KEY(`depto`)
          REFERENCES departamentos`(`numdepto`)
          ON DELETE RESTRICT
          ON UPDATE RESTRICT
          ;
          ```
      - `ON DELETE` e `ON UPDATE` (constraints)
        - `RESTRICT`: não permite a remoção de registros ou a alteração de dados que possuam relacionamentos
        - `CASCADE`: elimina registros em todas as tabelas relacionadas
        - `SET NULL`: atribui o valor nulo às colunas relacionadas em outras tabelas
        - `NO ACTION`: faça nada
    - **Linguagem de Manipulação de Dados (Data Manipulation Language, DML)**
      - Comandos que permitem a manipulação de dados
        - `INSERT`
          - Padrão
            ```sql
            INSERT INTO [tabela] ([Campo 1], [Campo 2], [Campo 3],...) VALUES ([Valor Campo 1], [Valor Campo 2], [Valor Campo 3],...);
            ```
          - Exemplo
            ```sql
            INSERT INTO funcionários (nome, salario) VALUES ('Mário Alberto', 4500);
            ```
        - `UPDATE`
          - Padrão
            ```sql
            UPDATE [tabela] SET `campo1`=[valor1],`campo2`=[valor2],`campoN`=[valorN] WHERE [condição ou expressão lógica];
            ```
          - Exemplo
            ```sql
            UPDATE funcionarios SET salario = salario * 1.1 WHERE salario > 1000;
            ```
        - `DELETE`
          - Padrão
            ```sql
            DELETE FROM [tabela] WHERE [condição];
            ```
          - Exemplo
            ```sql
            DELETE FROM funcionarios WHERE situacao = “INATIVO”;
            ```
        - `SELECT`
          - Padrão
            ```sql
            SELECT <lista de campos> FROM <nome da tabela> [WHERE <condição>] [ORDER BY <lista de campos>] [...];
            ```
          - Exemplo
            ```sql
            SELECT matric, nome, depto, departamentos.nomedepto, salario, telefone
            FROM departamentos INNER JOIN funcionarios ON departamentos.numdepto=funcionarios.depto
            WHERE depto=2 AND salario>4000;
            ```
          - Exemplo (encadeamento)
            ```sql
            SELECT * FROM (SELECT * FROM funcionarios WHERE salario>4000) WHERE depto=2;
            ```
    - **Linguagem de Controle de Dados (Data Control Language, DCL)**
      - Comandos que permitem a criação, revogação de políticas de acessos e restrições aos dados
        - `GRANT`
        - `DENY`
        - `REVOKE`

## Modelagem de Dados Lógica (desenho dos campos das tabelas e seus relacionamentos)

- Independe de qual Sistema de Banco de Dados será utilizado

### Tipos de relacionamentos entre tabelas

- 1:1 (um para um)
- 1:N (um para muitos)
- N:N (muitos para muitos)

### Estrutura de tabelas

- Linha: registro único
- Coluna: campo de dado

### Tipos de dados

#### Numéricos

- TinyInt: -128 até 127 ou de 0 até 255 (unsigned)
- SmallInt
- MediumInt
- Int
- BigInt: maior intervalo
- Float
- Double: maior precisão
- Decimal
- Bit ou Bool: 0 ou 1

#### Data

- Date: ano-mês-dia
- Time: horas:minutos:segundos
- DateTime: Date + Time
- TimeStamp: data e hora configurável (mais usado)
- Year: de 1901 a 2155

#### Alfanumérico

- Char: de 0 até 255 caracteres
- VarChar: tamanho variável
  - TinyText e TinyBlob
- Text e Blob: até 65.535 caracteres
- MediumBlob e MediumText: até 16.777.215 caracteres
- LongBlob e LongText: até 4.294.967.295 caracteres
- Enum: único valor de uma lista especificada
- Set: nenhum, um ou mais de um valor de uma lista especificada, até 64 valores

### Valor default

- None: para tipos Enum ou Set
- As defined
- Null: valor inexistente
- Current Timestamp: para tipos data ou data-hora

### Índices

- Primary
  - Chave primária, apenas um por tabela
  - Dados únicos, sem repetição
  - Não aceita dados nulos
- Unique: aceita dados nulos
- Index: aceita repetição de dados e dados nulos
- Fulltext: para melhor indexação das palavras em um campo de texto

## MySQL

- Licença: GPL (General Public License – Licença Pública Geral)
- Compatível com o padrão Unicode, representa textos em quaisquer sistemas de escrita
- Login no monitor como admin: `mysql –u usuário senha`
- Acessar o BD: `USE [nome do banco de dados];`

### Funções

- NOW(): Retorna a data e a hora
- CURDATE(): Retorna a data atual
- CONCAT(): Retorna a concatenação de uma série de campos e expressões string
  - Exemplo: `SELECT matric, CONCAT(“Nome: “, nome), salario FROM funcionarios`
- COUNT(): Retorna a contagem ao invés das linhas de uma consulta SQL
  - Exemplo: `SELECT COUNT(*) FROM funcionarios`
- SUM(): Retorna o somatório de todos os valores de determinada coluna
  - Exemplo: `SELECT SUM(salario) FROM funcionarios`
- AVG(): Retorna a média aritmética de todos os valores de determinada coluna
  - Exemplo: `SELECT AVG(salario) FROM funcionarios`
- ROUND(): Arredonda os valores resultantes em seu argumento
  - Sintaxe: `ROUND(val, #)`, onde “val” é o resultado do valor a ser arredondado,
    e # significa a quantidade de casas decimais a serem consideradas no arredondamento
  - Exemplo: `SELECT ROUND(AVG(salario),2) FROM funcionarios`
- FORMAT(): Converte um determinado valor no formato monetário
  - Sintaxe: `FORMAT(val, #)`, onde “val” é o valor a ser formatado
    e # é a quantidade de casas decimais a ser considerada
  - Exemplo: `FORMAT(4000,2) → 4,000.00`
- RAND(): Retorna uma linha aleatória dentro de uma tabela
  - Deve ser utilizada dentro da cláusula ORDER BY
  - Exemplo: `SELECT nome, salario, depto FROM funcionarios ORDER BY RAND() LIMIT 1`

### Stored procedures

#### Padrão

```sql
DELIMITER $$
CREATE PROCEDURE nome_procedure()
BEGIN
  -- comandos SQL
END $$
DELIMITER
```

#### Exemplo

```sql
DELIMITER $$
CREATE PROCEDURE prog()
BEGIN
  SELECT * FROM `funcionarios`;
END $$
DELIMITER;
```

- Invocar SP: `CALL 'prog'();`

### Triggers (gatilhos)

#### Características

- Executam stored procedures na ocorrência de um evento
- Acionado sempre que determinada condição for satisfeita
- Sempre vinculado a uma tabela
- Não pode ser ignorado
- Não são executados diretamente
- Pode ser revertido pelo comando ROLLBACK
- Mesmas vantagens e desvantagens das stored procedures

#### Padrão

```sql
CREATE TRIGGER <nome> <momento> <evento>
ON <tabela>
FOR EACH ROW
BEGIN
  /*instrução SQL*/
END
```

#### Exemplo

```sql
CREATE TRIGGER `Add_Func` AFTER INSERT ON
`funcionarios` FOR EACH ROW BEGIN UPDATE departamentos
SET `departamentos`.`qtdfunc` =
`departamentos`.`qtdfunc` + 1 WHERE
`departamentos`.`numdepto` = NEW.`depto`; END
```

- Cláusulas
  - `NEW`: registro que está sendo incluído
  - `OLD`: registro que está sendo excluído

### Views (visões)

#### Padrão

```sql
CREATE [OR REPLACE]
[ALGORITHM = tipo de algoritmo]
VIEW (nome da view)
[(lista de colunas)]
AS (sentença SELECT)
[WITH [CASCADED | LOCAL] CHECK OPTION]
```

#### Exemplo sentença SELECT

```sql
SELECT departamentos.nomedepto, matric, nome, salario
FROM `funcionarios` INNER JOIN `departamentos` WHERE
salario > 5000 AND funcionarios.depto = departamentos.numdepto
AND funcionarios.depto = 2
```

- Exemplo de como usar a view: `SELECT * FROM <nome da view>`

# Gerenciamento de um servidor de banco de dados

## 1. Escolha de um host (hospedagem do BD)

- Dentro da própria organização (local host)
- Datacenter externo (terceirizado)
  - Espaço projetado para hospedar servidores de dados e componentes ativos de rede
- Na nuvem (cloud computing)
  - Compartilhamento da capacidade de processamento e armazenamento
  - Vantagens
    - Redução de custos com equipe de manutenção
    - Barateamento da infraestrutura de rede local
    - Alta disponibilidade dos servidores
    - Maior segurança, uma vez que os dados ficam replicados em servidores espalhados em locais diferentes
    - Flexibilidade de manutenção devido às ferramentas automatizadas
    - Licenciamento SaaS (Software as a Service)

## 2. Requisitos de hardware

- Velocidade e arquitetura do processador
- Memória RAM disponível
- Capacidade de armazenamento (magnético ou sólido)
- Velocidade e tecnologia da placa controladora do HD
