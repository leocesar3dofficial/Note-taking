# DevOps

- **Definição**: Equivale à junção das equipes (Dev) e operações de TI (Ops).

## Processo

- **Shift left**: Planejar > Codificar > Build > Testar
  - A segurança do software é levada em consideração desde o início do desenvolvimento.
  - A segurança é uma prioridade fundamental para todas as equipes de DevOps.
- **Shift right**: Lançar > Deploy > Operar > Monitorar

## Princípios

1. **Cultura de colaboração**
   - As equipes de desenvolvimento e operações são integradas em uma única equipe.
   - Enfatiza a importância da colaboração e comunicação eficaz entre as equipes.
   - Envolve a quebra de barreiras e a criação de um ambiente de confiança e compartilhamento de responsabilidades.
   - Anti-padrão: Falta de colaboração entre equipes.
2. **Automação**

   - Permite a implantação e integração contínuas.
   - Reduz erros, aumenta a eficiência e acelera o tempo de entrega.
   - Anti-padrão: Falta de automação.

3. **Entrega contínua**

   - Entrega rápida e confiável de software.
   - Execução de atualizações frequentes, porém pequenas.
   - Automatiza o processo de compilação, teste e implantação.
   - Envolve a construção de pipelines de entrega contínua.
   - Permite a liberação frequente de novas versões do software.

4. **Monitoramento contínuo**

   - Uso de ferramentas de monitoramento e registro.
   - Coleta dados em tempo real.
   - Identifica problemas rapidamente, permitindo ações corretivas imediatas.

5. **Resiliência**

   - Necessidade de construir sistemas resilientes.
   - Capazes de lidar com falhas e se recuperar rapidamente.
   - Elementos:
     - Projeto de arquiteturas distribuídas.
     - Uso de práticas de teste de estresse.
     - Implementação de estratégias de recuperação automática.

6. **Infraestrutura como código (IaC, Infrastructure as Code)**

   - Automação da configuração, gerenciamento e provisionamento da infraestrutura de TI por meio de código.
   - Permite a criação e gerenciamento de ambientes de forma consistente e controlada.
   - Facilita a replicação do ambiente de produção em diferentes estágios do ciclo de vida do software.
   - O controle de versão é uma parte importante desse gerenciamento.

7. **Feedback rápido**
   - Gera aprendizado contínuo e melhoria.
   - Coleta de feedback dos usuários e das operações em tempo real.
   - Análise de métricas e indicadores para tomar decisões informadas e impulsionar a inovação.

# DevSecOps

## Características

- Combina os princípios do DevOps com a segurança da informação (Sec).
- Incorpora a segurança desde o início, como elemento essencial do processo de entrega de software.
- Integra a segurança de forma contínua e transparente em todos os estágios do processo.
- Garante a proteção dos dados, a conformidade regulatória e a confiança dos usuários finais.
- Na abordagem tradicional a segurança costuma ser tratada como uma preocupação secundária, sendo abordada no final do ciclo de desenvolvimento ou até mesmo após o lançamento.

## Princípios

1. **Colaboração entre equipes**

   - Colaboração entre equipes de desenvolvimento, operações e segurança.

2. **Automação de segurança**

   - Permite a detecção precoce de problemas de segurança e acelera a resposta a possíveis ameaças.
   - Realiza verificações de segurança automatizadas:
     - Testes de penetração.
     - Análise de código-fonte em busca de vulnerabilidades.
     - Gerenciamento de configuração segura.

3. **Segurança como código**

   - Alinhado com a ideia de infraestrutura como código do DevOps.
   - As políticas de segurança, configurações e regras são codificadas e versionadas juntamente com o código do aplicativo.
   - Garante que a segurança seja tratada de forma consistente e rastreável como parte do pipeline de entrega contínua.

4. **Testes de segurança contínuos**

   - Realiza testes de segurança contínua ao longo do ciclo de vida do software.
   - Execução de testes automatizados de segurança.
   - Revisões de código com foco em vulnerabilidades.
   - Análises estática e dinâmica.
   - Testes regulares de penetração.
   - Os resultados são monitorados e tratados de forma ágil.

5. **Monitoramento e resposta a incidentes**
   - Detecção e resposta a incidentes de segurança em tempo real.
   - Monitoramento constante das aplicações e infraestrutura.
   - Análise de logs.
   - Implementação de mecanismos automatizados de resposta a incidentes.
   - Ações corretivas rápidas são tomadas para mitigar ameaças em potencial e melhorar a segurança do sistema.
