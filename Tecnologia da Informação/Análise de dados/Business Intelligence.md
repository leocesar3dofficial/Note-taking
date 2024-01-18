# Business Intelligence

## Conceitos

- **Dado:** Registro não processado
- **Informação:** Dados processados e analisados
- **Conhecimento:** Informação + experiência

## Definição

Processo onde dados são captados e convertidos em informações úteis ao negócio. Metodologia de coleta, organização, avaliação, compartilhamento e controle de informações. Resultado: insights para o processo decisório.

### KPIs (Key Performance Indicators)

- **Eficiência:** Resultado obtido x recursos empregados
- **Eficácia:** Resultado obtido x resultado pretendido
- **Capacidade:** Quantidade produzida x tempo de produção
- **Produtividade:** Saídas x recursos utilizados
- **Qualidade:** Quantidade produzida x quantidade sem defeito
- **Lucratividade:** Lucro x vendas
- **Competitividade:** Organização x concorrência (market share)
- **Efetividade:** Eficácia x eficiência
- **Valor:** Valor percebido x valor real

Saída: relatórios ou dashboards em tempo real. Nível de precisão dos dados coletados: entre 50% e 90%.

## Benefícios

- Auxilia na integração dos canais de comunicação
- Gera inteligência e vantagem competitiva
  - Se preparar para as mudanças de mercado
  - Identificar riscos
  - Conhecimento sobre o negócio
- Processo decisório qualitativamente melhor
- Economia de custos
- Monitoramento de desempenho
- Identificar oportunidades de investimentos
  - Identificar novos mercados

## Princípios

1. Organizar os processos internos de forma estratégica
2. Automatizar serviços para integrar e ampliar a eficiência dos setores (arquitetura de dados)
3. Agrupar dados e transformá-los em informação confiável, exata e de qualidade
4. Tomar decisões com base em análises bem-calculadas
5. Ter uma visão clara dos objetivos a serem alcançados
6. Buscar falhas
7. Identificar oportunidades de investimentos
8. Aprimorar seu desempenho no mercado

## Gerenciamento

- **ETL (Extract, Transform, Load):**
  1. Identificar fontes de dados
  2. Traduzi-los em um formato padrão
  3. Carregá-los em um banco de dados
- **Processo de gestão:**
  1. Planejamento
  2. Automação e integração
  3. Tomada de decisões
  4. Análise de desempenho
  5. Controle de gastos
  6. Reconhecimento de oportunidades
- **Implementação:**
  1. Definição e quantificação de requisitos
  2. Análise da capacidade de coleta (infraestrutura)
  3. Coleta de dados
  4. Análise qualitativa
  5. Extração de informação
  6. Análise de dados

## Modelagem de dados

### Etapas

1. Definir fatos ou métricas
2. Determinar as dimensões
   - Dimensional (tabela única ou dataframe)
   - Multidimensional (em cubos ou tabelas relacionadas)
3. Estabelecer a granularidade dos dados em cada dimensão
4. Estabelecer a hierarquia e agrupamento dos dados
   - Tempo: dia, semana, mês, semestre, ano
   - Produto: item, linha, segmento
   - Geografia: armazém, cidade, estado, região

## Segurança

- Acesso e alçada
- Fontes de dados alternativas
- Arquivamento e descarte
- Backup e recovery / restore
  - Técnicas de backup:
    1. Completo
    2. Incremental
    3. Diferencial
    4. Espelhado
    5. Delta
  - Ferramentas:
    - Comando rsync no Linux: backup de arquivos remotos
    - Time Machine no MacOS: em dispositivos externos

## Infraestrutura

### Armazenamento

- Banco de dados
- Data Warehouse (DW)
  - Sistema que centraliza os dados coletados de diversas fontes
  - Elementos
    - Fontes de dados
      - Características
        - Incluem dados transacionais, externos, históricos e agregados.
        - Podem incluir DBMS, ERP e CRM, entre outros.
      - Formas de comunicação
        - OLTP (On-line Transaction Processing)
          - Transações em tempo real.
          - Suportam e otimizam operações diárias de uma organização, como inserção, atualização e exclusão de registros em bancos de dados.
        - OLAP (On-line Analytical Processing)
          - MOLAP (Multidimensional Online Analytical Processing)
            - Armazenamento multidimensional dos dados, frequentemente usando cubos OLAP.
            - Esses cubos são eficientes para consultas analíticas complexas e agregações.
          - ROLAP (Relational Online Analytical Processing)
            - Usa um modelo relacional para armazenar os dados analíticos.
            - Ele não pré-agrega os dados como em MOLAP, mas busca diretamente no banco de dados relacional para obter resultados.
          - HOLAP (Hybrid Online Analytical Processing)
            - Combina elementos do MOLAP e ROLAP.
            - Pode usar armazenamento multidimensional para resumos rápidos, mas também se integra com dados detalhados armazenados em bancos de dados relacionais.
      - Bancos de dados (backend)
        - Metadados
          - Dados sobre os dados
          - Atributos: descrição, ambiente, forma de manipulação, para onde é distribuído
          - Tipos
            - Técnicos (sintáticos, estruturais)
            - De negócio (semânticos)
        - Data Staging
          - Identificar e classificar dados sujos para posterior migração
      - Ferramentas ETL
        - Ferramentas para mineração, análise e geração de relatórios (frontend)
        - Processamento em lote
        - Exemplos: Tableau, Power BI, SAP Analytics Cloud
      - APIs (Application Programming Interfaces)
        - Para integração entre sistemas
  - Características
    - Orientado por assunto
    - Integrado
    - Variável no tempo (histórico dos registros)
    - Não volátil
    - Deve evoluir com o tempo com o uso de estratégias evolucionárias
  - Tipos
    - Quanto a dimensão
      - Enterprise Data Warehouse (EDW)
      - Data Marts (DM)
      - Operational Data Store (ODS)
    - Quanto a estrutura
      - Simples
      - Simples com área de preparo (staging de novos dados)
      - Hub and spoke
      - Áreas restritas
    - Níveis de redundância
      - Virtual
      - Central
      - Distribuído (serviço na nuvem - Cloud Computing)

### Data Lake

- Armazenamento de dados não estruturados

### Sistemas de Informação

1. **BPM (Business Process Management):**
   - Auxilia na interpretação e otimização de processos
2. **ERP (Enterprise Resource Planning):**
   - Objetivo de integrar todas as áreas e processos em uma única plataforma
3. **SCM (Supply Chain Management):**
   - Logística
4. **CRM (Customer Relationship Management):**
   - Gerenciar os relacionamentos e interações com clientes

### Planilhas eletrônicas

### Descoberta de Conhecimento em Banco de Dados (DCBD)

- Knowledge Discovery in Databases
- Identificação de padrões em um conjunto de dados
- Características dos dados explorados
  - Validade
  - Novidade
  - Utilidade
  - Assimilável
- Etapas
  1. Definição do problema
  2. Seleção dos dados
  3. Eliminação de incongruências/erros dos dados (limpeza dos dados)
  4. Enriquecimento dos dados
  5. Codificação dos dados
  6. Data Mining
  7. Geração de relatórios e comunicação dos resultados

### Data cleansing (limpeza de dados)

- Detecção, reparo ou a exclusão de dados

### Dashboard

- Painel de monitoramento das atividades do negócio
- Para clientes internos e externos
- Normalmente são atualizados em tempo real
