# DevOps

- **Definição**: Equivale à junção das equipes (Dev) e operações de TI (Ops).

## Processo

- **Shift left**: Planejar > Codificar > Build > Testar.

  - Os testes devem ser feitos desde as fases iniciais do ciclo de vida do produto. 
  - A segurança do software é levada em consideração desde o início do desenvolvimento.
  - A segurança é uma prioridade fundamental para todas as equipes de DevOps.
  
- **Shift right**: Lançar > Deploy > Operar > Monitorar.

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

## Boas Práticas

1. **Automação de Infraestrutura:**

   - Utilização de ferramentas de automação, como o Ansible, Chef, ou Puppet, para provisionamento e configuração automatizados de ambientes de infraestrutura.

2. **Monitoramento Contínuo:**

   - Implementação de soluções de monitoramento que acompanham o desempenho do aplicativo e da infraestrutura em tempo real, possibilitando a detecção rápida de problemas.

3. **Logs Centralizados:**

   - Agregação e análise centralizada de logs do aplicativo e dos componentes da infraestrutura, facilitando a solução de problemas e a compreensão do comportamento do sistema.

4. **Testes de Performance:**

   - Realização de testes de desempenho e escalabilidade para garantir que o aplicativo atenda aos requisitos sob carga e que seja possível identificar e corrigir gargalos de desempenho.

5. **Orquestração de Containers:**

   - Utilização de plataformas de orquestração de containers, como Kubernetes, para facilitar a implantação, o gerenciamento e a escalabilidade de aplicativos baseados em containers.

6. **Pipeline de Entrega Completa (Full CI/CD Pipeline):**

   - Desenvolvimento de pipelines de entrega que abranjam todas as fases, desde a integração contínua até a entrega contínua, com testes automatizados, revisões de código e implementação.

7. **Segurança DevSecOps:**

   - Integração da segurança no ciclo de vida do desenvolvimento, garantindo que as práticas de segurança estejam presentes desde a concepção até a implantação.

8. [**Gestão de Configuração:**](<../Back-end/Gestão de Configuração.md>)

   - Utilização de ferramentas de gestão de configuração para controlar e versionar as configurações do ambiente, garantindo consistência e reproducibilidade.

9. **Políticas de Retenção e Backup:**

   - Implementação de políticas de retenção de dados e procedimentos de backup para garantir a recuperação eficiente em caso de falhas ou perda de dados.

10. **Feedback Contínuo:**
    - Estabelecimento de uma cultura de feedback contínuo, incentivando a comunicação eficaz entre equipes de desenvolvimento, operações e outros stakeholders.

Essas práticas, quando combinadas, contribuem para a construção de um ambiente de desenvolvimento robusto, ágil e orientado pela automação, promovendo a entrega de software de alta qualidade de maneira eficiente e segura.

## Desenvolvimento com containers/contêineres

1. **Integração Contínua (CI):**

   - A integração contínua é uma prática em que os desenvolvedores integram seu código no repositório compartilhado com frequência, várias vezes ao dia.
   - Cada integração desencadeia a execução de testes automatizados para garantir que as alterações não quebrem a funcionalidade existente.
   - O objetivo é detectar e corrigir problemas de integração rapidamente, melhorando a qualidade do código e permitindo um desenvolvimento mais ágil.

2. **Entrega Contínua (CD):**

   - A entrega contínua é uma extensão da integração contínua que leva a automação um passo adiante.
   - Após a integração bem-sucedida e a execução de testes, o código é automaticamente construído (build), testado e preparado para implantação em ambientes de produção (deploy).
   - A entrega contínua busca garantir que o software esteja sempre pronto para ser entregue ao cliente, reduzindo os tempos de espera e os riscos associados às implantações manuais.

3. **Feature Flags (Toggles):**

   - As feature flags são mecanismos que permitem ativar ou desativar determinadas funcionalidades do software durante a execução.
   - Essas flags permitem que as equipes controlem o lançamento de novas funcionalidades, mesmo que estas estejam presentes no código, mas ocultas aos usuários.
   - As feature flags são úteis para realizar testes A/B, lançar funcionalidades gradualmente e realizar rollouts controlados.
   - Exemplos: adição/remoção de botões, filtros de pesquisa, etc.

4. **Deploy A/B:**

   - O deploy A/B envolve a implantação simultânea de duas versões diferentes do aplicativo, A e B, para diferentes grupos de usuários.
   - Esse método permite comparar o desempenho e a aceitação entre as duas versões e tomar decisões informadas sobre a implementação completa da versão mais bem-sucedida.

5. **Deploy Canário:**
   - O deploy canário é uma técnica que envolve a implantação gradual de uma nova versão do software para um pequeno subconjunto dos usuários ou servidores.
   - Uma pequena porção do tráfego do usuário (ou uma parte específica da infraestrutura) é direcionada para a nova versão do software, enquanto o restante continua a ser atendido pela versão anterior.
   - Esse subconjunto é chamado de "canário" e serve como um indicador antecipado de problemas potenciais antes da implantação em escala total.
   - Se a versão canário for bem-sucedida, a implementação é estendida para os demais usuários ou servidores.
