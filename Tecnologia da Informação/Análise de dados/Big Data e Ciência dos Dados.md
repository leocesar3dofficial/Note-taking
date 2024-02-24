# Big Data e Ciência dos Dados

## Conceito

### Big Data

- Não há um consenso sobre o conceito
- Alto volume de dados
- Dados complexos, variados, heterogêneos (não estruturados) e derivam de múltiplas fontes
- Variedade, Velocidade, Veracidade e Valor (descritos a seguir)
- Controles distribuídos e não centralizados
  - Heterogeneidade
    - Um dos requisitos de um sistema de arquivos distribuídos
    - Interfaces de serviço
      - Softwares clientes e servidores podem ser implementados para diferentes sistemas operacionais

### Ciência de dados

- Método para extração de informações úteis de bases de dados complexas
- Realiza previsões utilizando modelos matemáticos, estatísticos e informacionais
- Arcabouço teórico advém da Ciência da Informação
- Visão utilitária, de negócio, da informação e conhecimentos gerados
- A utilização de Big Data não é obrigatória; pode-se valer de bases de dados de menor volume

## História

- Não há um consenso sobre a época de seu surgimento
- 1990, NASA
- 2000, meio acadêmico

## Objetivos

- Gerar insights
- Identificar padrões e sentidos

## Características

- **Volume**
- **Velocidade**
  - Maior velocidade com o uso da automação
  - Sistemas e ferramentas ETL (Extract, Transform, Load) para mineração de dados
- **Variedade**
  - Se vale de dados estruturados e não estruturados
- **Veracidade**
  - As fontes dos dados são confiáveis?
- **Valor**
  - Diminui com o passar do tempo

## Profissional da área: Cientista de dados

### Habilidades

- Pensamento crítico/analítico
- Conhecimento em engenharia de software
- Conhecimento em matemática e estatística
- Conhecimento de Inteligência Artificial e Aprendizado de Máquina

### Funções

- Equipe de extração
- Coordenador de infraestrutura
- Estatístico e/ou minerador de dados
- Especialista em ferramentas específicas
- Database Administrator (DBA)
- Programador
- Analista de negócio
- Designer

## Impactos na organização/negócio

- **Governança**
  - Como a organização/negócio conduz suas atividades em relação aos stakeholders
- **Planejamento**
  - O direcionamento das ações é afetado pelos resultados obtidos com a atividade de Big Data
- **Utilização**
- **Garantia da qualidade dos dados**
- **Privacidade**
  - Seguir a legislação vigente, ter responsabilidade social e ambiental

## Benefícios

- Reduzir custos
- Antecipar ações
- Elaborar estratégias
- Criar novos produtos
- Prever a demanda
- Realizar melhores ofertas
- Vantagem competitiva

## Áreas de aplicação

- **Educação**
  - Programm for International Student Assessment (PISA)
    - Compara o desempenho dos estudantes de diversos países
  - Plataformas de aprendizado personalizadas
  - Avaliação inteligente
- **Negócios**
  - Serviços financeiros
  - Telecomunicações
  - Meios de comunicação
  - Transporte
  - Serviços profissionais
  - Varejo e atacado
- **Saúde**
  - Melhoria no diagnóstico de doenças
- **Política**
  - Análise de clima eleitoral, aceitação nas redes sociais
- **Biologia/química**
- **Projetos sociais**

## Ferramentas

### Analytics

- **Hadoop**
  - Sistema de armazenamento de arquivos distribuídos
  - Hadoop Distributed File System (HDFS) é um software em Java
  - Alta tolerância a falhas
  - Usa hardware de baixo custo e escalável
- **Spark/Storm**
  - Frameworks de processamento e análise de dados
- **MapReduce**
  - Modelo de programação que permite o processamento de dados massivos
  - Algoritmo paralelo e distribuído
    - Velocidade de processamento de uma aplicação
      - Não é linearmente proporcional ao número de processadores usados
      - Fatores que podem limitar o ganho de desempenho
        - O grau de paralelismo da aplicação
        - A eficiência do algoritmo
        - A arquitetura do sistema
  - Processamento em cluster de computadores
    - Distribuir o processamento entre diferentes computadores
- **NoSQL**
  - **Conceito**
    - Sistema de Banco de Dados de documentos no formato JSON
    - Eficiente para organizar dados não estruturados
  - **Tipos**
    - Chave-valor
      - Garantir que não ocorra redundância via tabela hash
    - Orientado a documentos
    - Orientado a grafos

### Visualização

- **Características**
  - Apresentação de informações em formato imagético ou gráfico
  - Facilita a compreensão de grandes volumes de dados
  - Elemento da análise exploratória
- **Processo cíclico**
  - Pré-processamento: filtragem, limpeza e transformação dos dados
  - Mapeamento visual: geração de variáveis e respectivas representações gráficas
  - Representação: imagem ou gráfico final
- **Técnicas e ferramentas**
  - **Data Cube e Nanocube**
    - Matriz multidimensional de valores
    - Operations: slicing, dicing, pivoting, and aggregation
  - **Stream processing**
  - **Stream computing**
    - Analisar os dados em movimento
    - Tratamento dos dados estáticos em tempo real
  - **imMens**
    - Plataforma online que oferece interações em tempo real
  - **Oracle Data Mining**
  - **Tableau**
  - **Pentaho**
  - **Chartio**
    - Relatórios no navegador web
  - **Alteryx**
    - No code para análise de dados
  - **Talend**
    - Ferramenta ETL
  - **Knime**
    - Plataforma de análise de dados
  - **Python**
    - Jupyter, Pandas, Anaconda (distribuidora de pacotes/bibliotecas)

## Projeto de Ciência de Dados

### Fases

1. Identificar o problema
2. Entender o problema
3. Coleta de dados (datasets)
   - Fontes
   - Ontologia
     - Dados semi estruturados
     - Termos de uma área de conhecimento
     - Busca semântica
   - Data Warehouse
4. Limpar e transformar os dados
5. Entender o relacionamento entre os dados
6. Produzir modelos que representem os relacionamentos
7. Realizar predições
8. Entregar valor e resultado

### Ciclo de Vida dos Dados

1. Produção
2. Armazenamento
3. Transformação
4. Análise
5. Descarte

## Nuvem ou Cloud Computing

### Benefícios

- Redução de custos
- Flexibilidade
- Escalabilidade
- Desempenho

### Modelos

- [**SaaS (Software como Serviço)**](../../Linguagens%20e%20padr%C3%B5es/Plataformas%20de%20desenvolvimento.md#saas-software-como-serviço)
- [**PaaS (Plataforma como Serviço)**](../../Linguagens%20e%20padr%C3%B5es/Plataformas%20de%20desenvolvimento.md#paas-plataforma-como-serviço)
- [**IaaS (Infraestrutura como Serviço)**](../../Linguagens%20e%20padr%C3%B5es/Plataformas%20de%20desenvolvimento.md#iaas-infraestrutura-como-serviço)
