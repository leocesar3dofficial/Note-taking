# Segurança da Informação

## Conceitos de Segurança da Informação

- **Classificação de Informações**
- **Confidencialidade**

  - Garantir que os dados sejam mantidos em segredo ou privados.
  - O acesso às informações deve ser controlado.
    - Permitido apenas aos indivíduos autorizados.
  - Evitar o compartilhamento não autorizado de dados, seja intencional ou acidental.

- **Integridade**

  - Qualidade dos dados: corretos, precisos, consistentes, completos/integrados e aderentes às regras.

- **Disponibilidade**

  - Garantir que os dados estejam acessíveis aos usuários quando necessário.
  - Meios: redundância, recuperação de desastres, monitoramento, backup.

- **Não Repúdio ou Irretratabilidade**

  - Visa garantir que o autor não negue ter criado e assinado o documento.
    - Negação falsa de envolvimento em uma associação/transação.
  - Capacidade de provar a autoria de uma mensagem ou transação.
  - Meios: assinatura digital, carimbo (time stamp), auditoria.

- **Privacidade**

  - Conexão segura e criptografada entre dois pontos em uma rede.
  - Pode ser alcançada com o uso de uma VPN (Rede Privada Virtual).

    - Usa o protocolo ESP (Encapsulating Security Payload).

      - Adiciona autenticação e confidencialidade.
      - Garantir que somente os destinatários autorizados possam ter acesso ao conteúdo do pacote.
      - Protocolo da suíte do IPsec (IP Security).
      - Modalidade de operação Gateway-to-Gateway.

    - **Recursos de uma VPN**

      1. **Criptografia:** Utilizam protocolos de criptografia para proteger a integridade e confidencialidade dos dados transmitidos.

      2. **Autenticação:** Garante a identidade dos usuários e dispositivos, evitando acessos não autorizados.

      3. **Túneis Seguros (tunneling):** A comunicação entre os pontos é encapsulada em túneis seguros, protegendo-a contra ameaças externas (protocolo ESP).

      4. **Privacidade:** Ao ocultar o endereço IP do usuário, as VPNs ajudam a preservar a privacidade online.

      5. **Acesso Remoto Seguro:** Permite que usuários se conectem a redes corporativas de forma segura a partir de locais remotos, como em home office.

      6. **Prevenção contra Interceptação:** Dificulta a interceptação e monitoramento não autorizado da comunicação.

- **Controle de Acesso**
  - Segurança física e lógica.
    - Identificação (cadastro do usuário).
    - Autorização (gerenciamento de credenciais).
      - Acesso concedido apenas para recursos, funções ou usuários específicos.
    - Autenticação (permitir ou bloquear o acesso).
      - Violação do princípio de privilégio mínimo.
      - Ferramenta de segundo fator (2FA, Two-factor authentication).
        - Mais de um fator de autenticação ou multifator: ex. senha e um código gerado por um dispositivo 2FA.

## Gestão da Segurança

- **Firewall**

  - Atua como uma barreira entre uma rede privada e a rede pública, como a Internet.
  - Monitora o tráfego de entrada e saída de rede.
  - Permite ou bloqueia com base em regras de segurança.
    - Funciona como um filtro de pacotes
    - Permite ou não a liberação de pacotes.
  - Pode ser implementado em hardware (dispositivos dedicados) ou software (programas em execução em servidores).
  - Baixo custo e eficácia satisfatória.

- **Next Generation Firewall (NGFW)**

  - Firewall com recursos adicionais.
  - Análise mais profunda no pacote e vê seu conteúdo.
    - Analisar se um download que está sendo feito contém algum tipo de ameaça.
  - URL Filtering.
    - Controlar o acesso a milhares de sites não desejados.
  - Prevenção contra vazamento de dados (DLP) sensíveis ao negócio.

- **Web Application Firewall (WAF)**

  - Filtra, monitora e bloqueia o tráfego HTTP de e para um aplicativo ou site da Web.
  - Capaz de filtrar o conteúdo de aplicativos web específicos.
  - Pode evitar ataques decorrentes de falhas de segurança de aplicativos Web.
    - Como injeção de SQL, XSS (Cross-Site Scripting), inclusão de arquivos e configurações erradas de segurança.
  - Serviços Cloud oferecem essa opção como a AWS (Amazon) e GoCache.

- **Intrusion Detection System (IDS)**

  - Monitora o tráfego de rede em busca de atividades suspeitas ou intrusões.
  - Identifica potenciais ameaças e emite alertas quando atividades maliciosas são detectadas.
    - Tipos de ameaças
      - **Bot:** é um programa que se comunica com o invasor e permite que a máquina seja controlada remotamente.
        - Infecção e propagação similar ao do worm.
      - **Botnet:** rede formada por centenas ou milhares de computadores zumbis e que permite potencializar as ações danosas executadas pelos bots.
  - Não toma medidas diretas para interrompê-las.

- **Intrusion Prevention System (IPS)**

  - É uma evolução do IDS.
  - Detecta ameaças, mas também toma medidas proativas para bloquear ou prevenir ataques em tempo real.
  - Pode reagir automaticamente para conter uma ameaça, como bloquear um endereço IP suspeito.

- **Security Information and Event Management (SIEM)**

  - Fornece uma visão holística da segurança da informação de uma organização.
  - Agrega e analisa eventos e logs de várias fontes em toda a infraestrutura de TI.
  - Combina a capacidade de coletar e analisar informações de segurança de vários dispositivos e sistemas em uma única plataforma.
  - Fornece insights em tempo real sobre a segurança da rede.
  - Ajuda na detecção de ameaças e auxilia na conformidade com regulamentações de segurança.

- **Proxy**

  - Um servidor proxy age como intermediário entre um dispositivo e a Internet.
  - Componentes responsável por intermediar a comunicação entre estações e os servidores da rede externa.
  - Usado para ocultar o endereço IP do dispositivo.
  - Filtra conteúdo da web e melhora a segurança.
  - Protege a rede interna contra ameaças externas.
  - Proxy reverso.
    - Um proxy regular com uma camada adicional.
    - É um servidor que é colocado por cima do "servidor web interno" para que possa ser o primeiro ponto de contato com clientes do lado da web.

- **Identity Access Management (IAM)**

  - É um conjunto de políticas, tecnologias e processos que gerenciam e controlam o acesso de usuários a sistemas e dados.
  - Define permissões com base nas identidades dos usuários, suas funções e suas necessidades de acesso.

- **Privileged Access Management (PAM)**

  - É uma subcategoria do IAM que se concentra na gestão e controle de acesso a contas privilegiadas.
    - Administradores de sistemas.
  - Minimiza os riscos associados a essas contas.
  - Garante que o acesso privilegiado seja monitorado e restrito.

- **Antivírus**

  - É um software projetado para detectar, bloquear e remover malware.
  - Como vírus, cavalos de Troia e worms, que podem infectar um sistema ou dispositivo.
  - É essencial para proteger computadores contra ameaças de software malicioso.

- **Antispam**

  - Projetado para filtrar e bloquear mensagens de e-mail indesejadas.
  - Reduz o volume de e-mails não solicitados que chegam às caixas de entrada dos usuários.
  - Protege contra ameaças que podem ser distribuídas por meio de e-mails.

## Planos de Continuidade de Negócio e Serviços Essenciais

### Características

- Garantir que uma organização possa continuar operando.
- Mesmo diante de eventos adversos.
  - Desastres naturais, ciberataques, interrupções de serviços.
  - Ou qualquer outra situação que possa afetar sua capacidade de funcionar normalmente.

### Plano de Continuidade de Negócio (PCN)

- Documento que detalha as medidas que uma organização deve tomar para garantir a continuidade de suas operações críticas.
  - Em caso de incidentes que possam afetar adversamente seus processos de negócios.
- Documento que orienta a organização a responder a uma disrupção e retomar, recuperar e restaurar a entrega de produtos e serviços, de acordo com os objetivos de continuidade de negócios (ABNT ISO 22301).

#### Etapas

1. **Identificação de Processos Críticos**

   - Identificar quais processos de negócios são essenciais para a organização e que não podem ser interrompidos por longos períodos.

2. **Avaliação de Riscos**

   - Avaliar os riscos potenciais que podem afetar esses processos.
     - Desastres naturais, ataques cibernéticos, falhas de infraestrutura, entre outros.

3. **Desenvolvimento de Planos de Resposta**

   - Criar estratégias detalhadas para lidar com esses riscos.
     - Incluindo procedimentos de recuperação, backups de dados, alocação de recursos e comunicação de crises.

4. **Testes e Treinamento**

   - Realizar testes regulares e treinamento de funcionários.
   - Garantir que todos compreendam seus papéis e responsabilidades durante uma interrupção.

5. **Atualização Contínua**
   - O PCN deve ser revisado e atualizado regularmente.
   - Para se manter relevante em relação às mudanças no ambiente de negócios e nas ameaças potenciais.

### Plano de Serviços Essenciais

- Parte fundamental do PCN que se concentra na identificação, proteção e recuperação de serviços críticos.

#### Etapas

1. **Identificação de Serviços Essenciais**

   - Identificar quais serviços são críticos para a operação da organização.
     - E têm um impacto direto na satisfação do cliente e no cumprimento das obrigações contratuais.

2. **Estratégias de Proteção**

   - Implementar medidas de segurança para garantir a disponibilidade contínua desses serviços.
     - Como redundância de servidores, backup de dados, sistemas de monitoramento e segurança cibernética.

3. **Recuperação de Serviços**

   - Desenvolver planos de recuperação específicos para cada serviço essencial.
     - Inclui tempos de recuperação aceitáveis e procedimentos de [failover](../Rede%20de%20Computadores.md#qualidade-de-serviço-qos).

4. **Testes e Treinamento**

   - Assim como no PCN, é importante realizar testes regulares e treinamento.
   - Garantir que os serviços essenciais possam ser restaurados com sucesso em caso de interrupção.

5. **Manutenção Contínua**
   - O plano de serviços essenciais deve ser revisado e atualizado regularmente para garantir sua eficácia.

## Conceitos de Segurança da Informação

### Criptografia

#### Características

- Técnicas para tornar a informação ininteligível para pessoas não autorizadas.
- Texto legível para texto cifrado.
- Usa algoritmos e chaves criptográficas.

#### Tipos

- **Simétrica**

  - Chave única para criptografar e descriptografar os dados.
  - Modos de operação.

    - **Electronic Codebook (ECB)**

      - Modo mais simples.
      - Cada bloco de dados é cifrado independentemente.
      - Revela padrões.

    - **Cipher Block Chaining (CBC)**

      - Cada bloco de dados é XORed (operação de OU exclusivo).
      - Texto cifrado do bloco anterior como base para o próximo bloco de dados.
      - Dependência entre os blocos, gerando texto cifrado diferente.
      - Requer um vetor de inicialização (IV) para o primeiro bloco.

    - **Cipher Feedback (CFB)**

      - Usa um gerador de sequência de números pseudoaleatórios.
      - Usado em criptografia síncrona.

    - **Output Feedback (OFB)**

      - Semelhante ao modo CFB.
      - Keystream: bloco de texto livre de um valor conhecido.

    - **Counter (CTR)**

      - Um contador é cifrado e usado como chave.
      - Permite paralelismo na cifragem.
      - Implementações em hardware e criptografia em tempo real.

- **Assimétrica (duas chaves)**

  - Chave pública para criptografar.
  - Chave privada para descriptografar.

### Esteganografia

- Técnica que oculta informações dentro de outros tipos de dados.
- Incorporando-as em arquivos de imagem, áudio, vídeo ou qualquer outro formato.
- Preserva a aparência e funcionalidade do container.

### Criptoanálise

#### Características

- Processo de analisar e quebrar sistemas criptográficos.
- Objetivo: revelar a informação original ou descobrir as chaves de criptografia.

#### Técnicas

- Força bruta.
- Análise de padrões.
- Exploração de fraquezas matemáticas ou estatísticas.

## Funções ou Algoritmos Digestores (Hashes)

- Input de dados de tamanho arbitrário e gera uma saída de tamanho fixo, chamada de digesto ou hash.

### Propriedades

- Integridade dos dados.
  - Alteração nos dados de entrada resulta em um hash diferente.
- Tamanho fixo.
- Irreversibilidade.
  - As funções digestoras são unidirecionais.
- Colisões.
  - Duas entradas diferentes podem gerar o mesmo hash, mas é raro.
- Eficiência.

### Aplicações

- Verificação de integridade de arquivos.
- Autenticação de mensagens.
- Armazenamento seguro de senhas em bancos de dados.
- Identificação de duplicatas.

### Tipos (dos mais vulneráveis aos mais seguros)

- **MD5 (Message Digest Algorithm 5)**
  - Algoritmo de hash de 128 bits.
  - Considerado inseguro.
    - Suscetível a ataques de colisão.
- **SHA-1 (Secure Hash Algorithm 1)**
  - Hash de 160 bits.
  - Considerado inseguro.
- **SHA-256 (Secure Hash Algorithm 256-bit)**
  - Hash de 256 bits.
  - Parte da família de algoritmos SHA-2.
  - Considerado seguro.
  - Usos:
    - Utilizado para garantir a integridade de dados e autenticação.
    - Criptomoedas, assinaturas digitais e autenticação de arquivos.
- **SHA-3 (Secure Hash Algorithm 3)**
  - Algoritmo de hash mais recente.
  - Diferentes tamanhos de saída, como SHA-3-224, SHA-3-256, SHA-3-384 e SHA-3-512.
- **RSA (Rivest-Shamir-Adleman)**
  - Algoritmo de criptografia de chave pública.
  - Protege as comunicações e estabelece confiança nas transações digitais.
  - Usado para estabelecer conexões seguras, como nos protocolos HTTPS.
  - Sua segurança depende da dificuldade computacional de fatorar grandes números primos.
  - Usos:
    - Criptografia de dados.
    - Assinaturas digitais.
    - Gera chaves para outros algoritmos.
- **AES (Advanced Encryption Standard)**
  - Algoritmo de criptografia simétrica.
  - Usado para criptografar dados em repouso e em trânsito.
  - Algoritmo mais usado na atualidade e aprovado pelo governo dos EUA.
  - Usado por plataformas de mensagens seguras como WhatsApp e Signal messenger (similar ao WhatsApp).
  - Alta segurança, velociade e efetividade.
  - Usado em conjunto com o algoritmo RSA. Os dois formam a espinha dorsal da Internet no quesito segurança.
  - Tamanhos de chave: AES-128, AES-192 e AES-256.
    - Limita o tamanho do bloco a 128 bits.
  - Usos:
    - Criptografar dados confidenciais.
    - Criptografia de arquivos e dispositivos.
    - Comunicação segura.

## Protocolos de Autenticação e Autorização

### OpenID Connect (OIDC)

- Permite que os usuários autentiquem sua identidade em um provedor de identidade.
  - Como uma conta do Google ou do Facebook.
- Obtêm um token de identidade: informações pessoais sobre o usuário, que o autentica.
  - ID Token como objeto JSON.
- Suporte a autorização delegada.
  - Um aplicativo cliente solicita acesso aos recursos de um servidor de recursos em nome de um usuário.
  - Usa um gateway de autenticação.
    1. Autenticar o usuário.
    2. Gerar o token de acesso.
    3. Entregá-lo ao aplicativo cliente.
- Baseado no OAuth2.

### SSO (Single Sign-On)

- Um token é usado para autenticar o usuário em vários sistemas.
- É um conceito e uma abordagem.
- Elimina a necessidade de fazer login em diferentes sistemas.

### OAuth2

- Permitir que aplicativos de terceiros acessem recursos em nome do usuário.
- Protocolo de autorização.
- Usado por provedores de serviços (como redes sociais).

### SAML (Security Assertion Markup Language)

- Protocolo de autorização baseado em XML.
- Usado em cenários de SSO (Single Sign-On).
- Utilizado em ambientes corporativos e acadêmicos.
- Atores:
  1. Provedor de identidade (IdP).
  - Assertion: token de autenticação assinado digitalmente.
    - Enviado ao SP para autenticação e autorização.
  2. Provedor de serviços (SP).
  3. Usuário.

### LDAP (Lightweight Directory Access Protocol)

- Protocolo de acesso a diretórios.
  - Informações organizadas em forma de árvore.
  - Cada diretório possui um DN (Distinguished Name).
- Versão mais leve do protocolo X.500.
- Abordagem cliente-servidor.
- Operações: pesquisa, adição, exclusão e modificação.
- Possui recursos de autenticação e autorização.
- Implementação: Microsoft Active Directory e OpenLDAP.

### SSL (Secure Sockets Layer) / TLS (Transport Layer Security, sucessor do SSL)

- Protocolos de segurança para estabelecer uma conexão criptografada.
- Fornecem autenticação, integridade e confidencialidade dos dados transmitidos.
- **Usos**
  - Transações financeiras online.
  - E-mails seguros.
  - Acesso a sites por meio de HTTPS.
    - O servidor é sempre autenticado e o cliente é opcionalmente autenticado.
    - Mensagens do handshake
      1. ClientHello, enviada pelo cliente (obrigatório).
      2. ServerHello, enviada pelo servidor.
         - Contém os parâmetros criptográficos que serão utilizados na conexão.
- **Autenticação no TLS**
  - O cliente e o servidor negociam qual método de autenticação será usado.
  - O servidor envia seu certificado digital ao cliente.
  - O cliente verifica o certificado do servidor para garantir que ele é confiável.
  - Se o cliente for autenticado, ele envia seu certificado digital ao servidor.
  - O servidor verifica o certificado do cliente para garantir que ele é confiável.
  - **Vantagens**
    - Garante a identidade do servidor
      - O cliente tem certeza de que está se comunicando com o servidor correto.
    - Protege contra ataques de phishing
      - O cliente não pode ser enganado a se conectar a um servidor falso.
    - Protege contra ataques de man-in-the-middle
      - O invasor não pode interceptar e modificar os dados que estão sendo transmitidos.

### SSH (Secure Shell Protocol)

- **Conceito:**
  - Utilizado para permitir o acesso seguro a sistemas remotos.
  - É um protocolo de rede projetado para fornecer comunicações seguras e autenticadas em uma rede não confiável, como a Internet.
  - Transferência segura de dados entre computadores.
- **Características:**
  - **Autenticação Segura:**
    - Oferece autenticação robusta para verificar a identidade das partes envolvidas na comunicação.
    - Baseada em chave pública/privada ou autenticação com senha.
    - A autenticação baseada em chave é geralmente considerada mais segura, pois não envolve a transmissão de senhas pela rede.
  - **Criptografia:**
    - Usa criptografia para proteger os dados durante a transmissão.
    - Garante que mesmo se alguém interceptar as comunicações, os dados permanecerão ilegíveis sem a chave de descriptografia apropriada.
    - Os algoritmos de criptografia podem variar, mas o SSH suporta algoritmos robustos.
  - **Acesso Remoto:**
    - Utilizado para acesso remoto a sistemas Unix, Linux e outros sistemas operacionais.
    - Permite que os administradores acessem e gerenciem servidores e dispositivos de rede de forma segura, mesmo a partir de locais distantes.
  - **Transferência de Arquivos Segura:**
    - Suporta a transferência segura de arquivos.
    - O utilitário mais comum para isso é o `scp` (Secure Copy).
      - Permite copiar arquivos de e para sistemas remotos com segurança.
  - **Túneis SSH:**
    - Útil para proteger o tráfego de outros serviços que não são nativamente seguros.
    - Por exemplo, você pode criar um túnel SSH para redirecionar o tráfego da web, criando uma conexão segura para navegar em uma rede pública.
  - **Porta Padrão:**
    - Utiliza a porta 22.
    - Essa porta pode ser alterada para aumentar a segurança.
    - Torna mais difícil para os atacantes explorarem vulnerabilidades conhecidas do SSH.
  - **Chaves SSH:**
    - Os usuários geram um par de chaves SSH, uma pública e uma privada.
    - A chave pública é colocada no servidor remoto e a chave privada é mantida com segurança no cliente.
    - Essas chaves são usadas para autenticação sem a necessidade de senha, como usado no GitHub.

### Kerberos

- Protocolo de autenticação de código aberto baseado em bilhetes.
- Fornece um alto nível de segurança e é utilizado em ambientes Windows e em sistemas Unix-like.
- É considerado mais seguro que o NTLM devido à sua criptografia forte e outras características.
- **Características:**
  - **Baseado em Bilhetes:**
    - Utiliza bilhetes criptografados para autenticação.
    - Os usuários obtêm um bilhete de autenticação após o login, que é usado para acessar serviços na rede.
  - **Segurança Robusta:**
    - Oferece criptografia forte e autenticação mútua.
    - Torna-o mais resistente a ataques como captura de tráfego e ataques de repetição.
  - **Single Sign-On (SSO):**
    - Suporta SSO, os usuários não precisam inserir suas credenciais várias vezes ao acessar recursos na rede.
  - **Delegação de Direitos de Autenticação:**
    - Permite que os usuários deleguem seus direitos de autenticação a outros sistemas ou serviços.
    - Facilita a autenticação em cascata.

### NTLM (Windows NT LAN Manager)

- É um protocolo de autenticação legado desenvolvido pela Microsoft.
- Foi introduzido no Windows NT.
- Ainda é suportado em versões mais recentes do Windows por razões de compatibilidade.
- **Características:**
  - **Baseado em Desafio-Resposta:**
    - Funciona em um sistema de desafio e resposta.
    - O servidor envia um desafio para o cliente, que responde com um valor hash baseado na senha do usuário.
    - **Segurança Limitada:**
      - Possui vulnerabilidades conhecidas, como a possibilidade de ataques de força bruta e ataques de passagem de hash.
    - **Compatibilidade:**
      - É compatível com sistemas mais antigos da Microsoft e pode ser usado em ambientes heterogêneos.
  - **Não Transmite Tokens de Segurança:**
    - Não fornece tokens de segurança, o que dificulta a delegação de direitos de autenticação para outros sistemas.

## Frameworks de Segurança

### MITRE ATT&CK (Adversarial Tactics, Techniques, and Common Knowledge)

- Descreve as táticas, técnicas e procedimentos (TTPs) usados por adversários cibernéticos em suas operações.
- Fornece um modelo de matriz que mapeia as fases de um ataque, desde a inicialização até a exploração, persistência, movimento lateral, e assim por diante.
- Usado para a detecção de ameaças, permitindo estratégias de defesa mais eficazes ao compreender o comportamento dos invasores.
- Ferramenta de pesquisa e referência para profissionais de segurança.
- Permite a compreensão e comunicação das táticas utilizadas pelos adversários.
- **Ataques**
  - Evasão de defesa.
    - dDesinstalar / desativar software de segurança.
    - Ofuscar / criptografar dados e scripts.

### Cyber Security Body Of Knowledge (CyBOK)

- Projeto de pesquisa e desenvolvimento que visa mapear o corpo de conhecimento da cibersegurança.
- Fornece diretrizes educacionais e profissionais abrangentes.
- Oferece uma estrutura para entender várias disciplinas da cibersegurança, desde criptografia e gerenciamento de riscos até segurança de redes e conformidade.
- Usado para definir os domínios de conhecimento em segurança cibernética.
- Guia para a educação e treinamento de profissionais de segurança.
- Padroniza a terminologia e práticas em cibersegurança, facilitando a comunicação e o desenvolvimento profissional.

### NIST Cybersecurity Framework (Framework de Cibersegurança do NIST)

- Conjunto de diretrizes e melhores práticas desenvolvido pelo Instituto Nacional de Padrões e Tecnologia (NIST, National Institute of Standards and Technology) dos Estados Unidos.
- Fornece orientações para organizações melhorarem sua postura de segurança cibernética.
- Foco na identificação, proteção, detecção, resposta e recuperação de ameaças.
- Composto por cinco funções principais: Identificar, Proteger, Detectar, Responder e Recuperar.
- Possui categorias e subcategorias de controles de segurança que as organizações podem adotar.
- Usado por organizações públicas e privadas como referência para aprimorar práticas de segurança.

## Gestão de Incidentes de Segurança

### NIST SP 800-61 (Computer Security Incident Handling Guide)

#### Características

- Orientações sobre como as organizações devem lidar com incidentes de segurança.

#### Etapas

1. **Preparação**
   - Definição de políticas e procedimentos.
   - Identificação e treinamento de equipes de resposta a incidentes.
   - Criação de um plano de resposta a incidentes.
2. **Detecção e Análise**
   - Monitoramento contínuo dos sistemas de informação.
   - Análise de incidentes para determinar natureza e gravidade.
3. **Contenção, Erradicação e Recuperação**
   - Tomar medidas para conter o incidente, erradicar a ameaça e restaurar a normalidade.
   - Jump Kit:
     - Estojo portátil de materiais.
     - Contem um laptop carregado com software apropriado.
       - Farejadores de pacotes e ferramentas de forense digital.
     - Dispositivos de backup, mídia virgem e cabos de rede.
4. **Comunicação**
   - Notificar partes interessadas internas e externas, incluindo autoridades reguladoras, conforme necessário.
5. **Documentação e Relatórios**
   - Ajuda a melhorar a preparação e a resposta a incidentes futuros.

### SANS (SysAdmin, Audit, Network, Security) Incident Handler's Handbook

#### Características

- Referência para profissionais de segurança e equipes de resposta a incidentes.
- Enfatiza a importância da compreensão profunda dos sistemas e redes para uma resposta a incidentes.

#### Etapas

1. **Planejamento e Preparação**
   - Enfatiza a importância da preparação.
   - Criação de políticas, procedimentos e planos de resposta a incidentes.
   - Formação de uma equipe de resposta a incidentes.
2. **Análise e Triagem**
   - Análise detalhada e triagem adequada de incidentes.
   - Priorização da resposta e alocação eficaz de recursos.
3. **Coleta de Evidências**
   - Apoio a investigações e processos legais.
4. **Mitigação e Recuperação**
   - Mitigação de incidentes em tempo real.
   - Redução de impacto e recuperação de sistemas e serviços afetados.
5. **Lições Aprendidas**
   - Revisão pós-incidente para identificar lições aprendidas e implementar melhorias.

## Plataforma Keycloak

### Características

- Gerenciamento de identidade e acesso federado.
- Desenvolvida pela Red Hat, código aberto.
- Facilita a integração de recursos de segurança em aplicativos.
- Altamente configurável e escalável, multiambiente (local, cloud).

### Suporte a Protocolos de Autenticação e Autorização e Protocolos da Camada de Aplicação

- **OpenID Connect (OIDC)**

  - Protocolo de autenticação baseado em OAuth 2.0.
  - Permite login em aplicativos web ou móveis usando contas de identidade existentes.
  - Fornece informações de identificação do usuário em formato JSON Web Tokens (JWT).
  - Utilizado para autenticação única (Single Sign-On) em sistemas online.

- **OAuth 2.0**

  - Protocolo de autorização para permitir que aplicativos acessem recursos protegidos em nome de um usuário, sem compartilhar sua senha.
  - Emissão de tokens de acesso que concedem permissão para ações específicas.
  - Usado em cenários de autorização de terceiros.

- **SAML (Security Assertion Markup Language)**

  - Padrão de troca de informações de autenticação e autorização entre sistemas.
  - Usado em cenários de autenticação federada.
  - Permite que um sistema autentique um usuário em seu nome e emita um token de afirmação.
  - Usado em ambientes empresariais e acadêmicos para autenticação única entre sistemas.

- **LDAP (Lightweight Directory Access Protocol)**

  - Protocolo de comunicação para acessar e manter informações em diretórios de informações.
  - Usado em redes de empresas para centralização da autenticação e autorização de usuários.
  - Gerencia informações de diretório, como usuários e grupos em sistemas de autenticação centralizada, como serviços de diretório ativos.

- **SMTP (Simple Mail Transfer Protocol)**

  - Protocolo de texto simples para enviar e-mails pela Internet.
  - Responsável pelo envio de mensagens de e-mail entre servidores.
  - Opera nas portas
    - 25, 587 (conexões seguras usando STARTTLS).
    - 465 (conexões seguras usando SSL/TLS).
  - Permite o envio de mensagens aos destinatários corretos.
  - Funciona em conjunto com outros protocolos como POP3 e IMAP para receber e gerenciar e-mails em clientes de e-mail.

- **CIFS (Common Internet File System)**

  - Protocolo de compartilhamento de arquivos
  - Permitir que dispositivos em uma rede acessem e compartilhem arquivos
  - Usado em ambientes Windows

- **NFS (Network File System)**

  - Protocolo de sistema de arquivos de rede.
  - Permite o compartilhamento de arquivos e diretórios entre sistemas em uma rede.
  - Utilizado em ambientes UNIX e Linux, permitindo acesso a arquivos remotos como se estivessem armazenados localmente.
  - Opera em várias versões (NFSv2, NFSv3, NFSv4, etc.), cada uma com melhorias em relação à versão anterior.
  - Baseado em uma arquitetura cliente-servidor, onde um servidor NFS exporta diretórios e arquivos para que os clientes NFS possam montá-los e acessá-los.

- **SMB (Server Message Block)**
  - Protocolo de rede usado em ambientes Windows para compartilhamento de recursos.
  - Permite que computadores em uma rede acessem e interajam com recursos compartilhados.
  - Suporta autenticação e permissões.
  - Nas versões mais recentes, chamado de SMB2 e SMB3, traz melhorias em desempenho, segurança e eficiência.

### Recursos

- **Gerenciamento de Identidade**
  - Registro de usuário.
  - Armazenamento de senhas.
- **Gerenciamento de Sessões**
- **Gerenciamento de Permissões e Grupos**
- **Suporte a Fluxos de Autenticação Personalizáveis**

## Assinatura Digital

- Garantia da integridade, confidencialidade e não repúdio.
- Permite que uma pessoa ou entidade assine um documento eletronicamente.
- Utiliza um par de chaves criptográficas, uma pública e outra privada.
- Mecanismo que fornece confiança na identidade das partes envolvidas.

### Processo

1. O remetente utiliza sua chave privada para criar a assinatura digital.
   - Garante que o documento não tenha sido alterado após a assinatura.
2. O destinatário utiliza a chave pública para verificar a autenticidade da assinatura.

## Certificação Digital

- Mecanismo que fornece confiança na identidade das partes envolvidas.
- Autoridades certificadoras (ACs) emitem os certificados digitais.
- Arquivo eletrônico que contém informações sobre a identidade.
  - Com o nome, chave pública, período de validade e a assinatura digital da AC.
- Usos:
  - Comércio eletrônico.
  - Serviços bancários.
  - Assinatura eletrônica de documentos públicos ou privados (cartório).
    - Emitido para Pessoa Física.
      - Assinatura Digital apenas da Autoridade Certificadora (AC).

## Infraestruturas de Chaves Públicas (PKI – Public Key Infrastructure)

### Características

- Conjunto de tecnologias, políticas e procedimentos de gerenciamento do uso de criptografia de chave pública.
- Permite que uma pessoa criptografe dados usando a chave pública de outra pessoa.
- Somente o detentor da chave privada poderá descriptografar esses dados.

### Componentes

1. Autoridade Certificadora (CA - Certification Authority).
   - Autoridade de chave pública.
   - Responsável por emitir e gerenciar certificados digitais.
   - Garante a autenticidade do certificado.
   - Garante a identidade do titular da chave pública.
2. Repositório de Chaves.
   - Local onde as chaves e os certificados digitais são armazenados e consultados.
   - Podem ser públicos ou privados.
3. Política de Certificação.
   - Regras, diretrizes e práticas.
   - Regem o processo de emissão, revogação e gerenciamento dos certificados.
4. Infraestrutura de Gestão de Chaves (KMI - Key Management Infrastructure).
   - Geração, armazenamento, distribuição, revogação e renovação das chaves.
   - Padrão UIT-T X.509.
     - Padrão internacional desenvolvido pela União Internacional de Telecomunicações (ITU-T).
     - Descreve um formato de certificado digital e as regras para sua utilização em uma PKI (Infraestrutura de Chaves Públicas).
     - Os certificados digitais X.509 são usados para vincular uma chave pública a uma entidade específica.
       - Pessoa, organização ou um servidor.
       - Fornece um meio de verificar a identidade dessa entidade em transações online.
       - Utilizados para autenticação, assinatura digital e criptografia.
       - Informações contidas no certificado.
         - Chave pública do titular.
         - Identificação (como nome e número de série).
         - Autoridade de certificação que emitiu o certificado.
         - Datas de validade e outras informações relacionadas à segurança.
5. Protocolos de Segurança.
   - SSL/TLS (Secure Sockets Layer/Transport Layer Security).
   - S/MIME (Secure/Multipurpose Internet Mail Extensions) para e-mails.
   - mTLS (Mutual Transport Layer Security).
     - É uma extensão do protocolo SSL/TLS e oferece um alto nível de segurança.
     - Características:
       - Autenticação Mútua.
         - Tanto o cliente quanto o servidor se autenticam um ao outro.
         - O cliente e o servidor apresentam certificados digitais durante o processo de negociação do TLS.
         - Esses certificados são emitidos por uma Autoridade Certificadora confiável (CA).
         - e são usados para provar a identidade de cada parte.
         - Garante que o cliente esteja se comunicando com o servidor esperado e que o servidor possa verificar a identidade do cliente.
       - Criptografia e Confidencialidade.
         - Uso de chaves de sessão que são negociadas durante o handshake TLS.
       - Chave Pública e Privada.
         - A chave privada é mantida em sigilo e nunca é compartilhada, enquanto a chave pública é divulgada.
         - O cliente e o servidor usam suas chaves privadas para assinar digitalmente mensagens e seus certificados.
         - e usam as chaves públicas uns dos outros para verificar as assinaturas.
       - Autoridades Certificadoras (CAs).
         - São entidades de confiança que emitem certificados digitais e garantem que as chaves públicas em um certificado pertençam à entidade correta.
         - Os certificados são verificados usando a hierarquia de confiança das CAs, garantindo que os certificados sejam válidos e confiáveis.
     - Casos de uso:
       - Autenticação de serviços da web.
       - Autenticação de clientes em aplicativos móveis.
       - Acesso seguro a APIs e comunicações seguras em redes corporativas.

## Gestão de Segredos (Secret Management)

### Conceito

- É a prática de gerenciar, armazenar, distribuir e proteger informações confidenciais.
  - Senhas, chaves de criptografia, tokens de autenticação e outros dados sensíveis.
- Os segredos são essenciais para a segurança de sistemas, aplicativos e serviços.
- Se caírem nas mãos erradas, podem ser explorados por atacantes para comprometer a segurança.

### Atividades

- Armazenamento Seguro.
  - Cofres de segredos (vaults) criptografados.
- Acesso Controlado.
  - Apenas pessoas e sistemas autorizados têm acesso aos segredos.
  - Seguindo rigorosas políticas de controle de acesso.
- Rotação de Chaves.
  - Senhas e chaves são rotacionadas periodicamente para minimizar o risco de comprometimento.
- Monitoramento e Auditoria.
  - As atividades são monitoradas e registradas para detecção de atividades suspeitas.
- Integração com Aplicativos.
  - Os segredos são integrados a aplicativos e sistemas de forma segura.
  - Permite a autenticação e a criptografia adequadas.

## Segurança de Confiança Zero (Zero-Trust Security)

### Conceito

- É um modelo de segurança que assume que nenhum usuário ou dispositivo, dentro ou fora da rede corporativa (ameaças internas e externas), deve ser automaticamente confiável.
- Exige autenticação rigorosa e verificação contínua de identidade e acesso, independentemente da localização ou do dispositivo usado.
- Princípio fundamental: "nunca confiar, sempre verificar".

### Componentes

- **Identidade e Autenticação Fortes**
  - Os usuários e dispositivos devem ser autenticados de forma rigorosa antes de obterem acesso a recursos.
  - Pode envolver autenticação de múltiplos fatores (MFA) e outras técnicas de verificação.
- **Segmentação da Rede**
  - A rede é segmentada em microperímetros de segurança.
  - O acesso é concedido apenas a recursos específicos com base na necessidade e na autenticação.
- **Políticas de Acesso Dinâmicas**
  - Definidas com base em contexto, considerando fatores como identidade, dispositivo, localização e comportamento.
- **Monitoramento Contínuo**
  - Para identificar comportamento suspeito ou não autorizado.
- **Tolerância a Falhas e Resposta Rápida**
  - Detectar e responder a ameaças de maneira rápida e eficaz.

## Múltiplos Fatores de Autenticação (MFA)

### Características

- Abordagem de segurança que requer que os usuários forneçam mais de uma forma de autenticação.
- Verificar sua identidade antes de acessar um sistema ou aplicativo.
- Fortalece a segurança, uma vez que um invasor precisa superar múltiplos obstáculos para ganhar acesso não autorizado.

### Componentes

- **Fator de Autenticação**
  - É uma categoria ou tipo de método de autenticação.
  - Os fatores mais comuns incluem:
    - Algo que você sabe (senha, PIN).
    - Algo que você tem (cartão de acesso, token de segurança).
    - Algo que você é (impressão digital, reconhecimento facial).
- **Autenticação em Dois Fatores (2FA)**
  - Forma mais comum de MFA e envolve o uso de dois fatores distintos para verificar a identidade do usuário.
  - Por exemplo, a combinação de uma senha (algo que o usuário sabe) com um código de autenticação temporária gerado em um aplicativo móvel (algo que o usuário tem).
- **Autenticação em Três Fatores (3FA)**
  - É uma extensão do 2FA que inclui um terceiro fator, como uma impressão digital (algo que o usuário é).
  - Torna a autenticação ainda mais segura.
- **Autenticação em Vários Fatores (MFA)**
  - Pode incluir mais de três fatores de autenticação para um nível mais elevado de segurança.

### Equipes de Segurança (Jogo de Gato e Rato)

#### Blue Team

- É a equipe responsável pela defesa e manutenção da segurança de um sistema, rede ou organização.
- **Responsabilidades**
  - Monitoramento de Segurança: Acompanhar a segurança da rede e dos sistemas para identificar ameaças em potencial.
  - Resposta a Incidentes: Agir em resposta a incidentes de segurança, como ataques cibernéticos, e mitigar os danos.
  - Configuração de Segurança: Configurar firewalls, sistemas de detecção de intrusão e outras medidas de segurança.
  - Atualizações de Segurança: Garantir que sistemas e software estejam atualizados com os patches de segurança mais recentes.
  - Treinamento e Conscientização: Educar os usuários e funcionários sobre práticas de segurança e políticas da organização.
  - Implementação de MFA: Configurar e gerenciar sistemas de MFA para fortalecer a autenticação.

#### Red Team

- **Características**
  - É uma equipe de especialistas em segurança que atua de forma independente.
  - Simulam ataques cibernéticos em um ambiente controlado.
- **Responsabilidades**
  - Testes de Penetração: Realizar testes de penetração e avaliações de segurança para identificar vulnerabilidades em sistemas, redes e aplicativos.
  - Simulação de Ataques:
    - **Características**
      - Simular ataques cibernéticos reais, incluindo ataques de hackers, engenharia social e outras táticas.
      - Testar a resiliência da defesa da organização.
    - **HoneyPOT**
      - **Características**
        - Um honeypot é uma ferramenta de segurança da informação.
        - Simula um sistema vulnerável para atrair cibercriminosos e coletar informações sobre suas táticas e técnicas.
      - **Tipos**
        - De baixa interatividade: São mais simples e simulam apenas alguns serviços de rede.
        - De alta interatividade: São mais complexos e simulam sistemas operacionais completos.
      - **Espécies**
        - Honeytokens: São informações falsas, como logins, números de cartões de crédito, tabelas de bancos de dados, etc. São usados para detectar tentativas de acesso não autorizado a sistemas de informação.
        - Honeyposts: São testes de segurança que simulam ataques cibernéticos em sistemas de informação para avaliar sua segurança. Usados para identificar vulnerabilidades e melhorar a postura de segurança de uma organização.
        - Honeynet: É uma rede de honeypots.
  - Identificação de Fraquezas: Identificar pontos fracos na segurança da organização e relatar essas descobertas para o Blue Team.
  - Melhoria da Segurança: Auxiliar o Blue Team na melhoria das medidas de segurança, aprimorando a postura de segurança da organização.
  - Treinamento e Conscientização: Realizar treinamentos e conscientização com a equipe do Blue Team. Ajudam a aprimorar a capacidade de resposta a incidentes.

## Legislação

### Organização da ICP-Brasil (Infraestrutura de Chaves Públicas Brasileira)

#### Objetivos

- Estabelecer diretrizes, normas e procedimentos para a emissão e o uso de certificados digitais.
- Garantir a autenticidade, integridade e validade jurídica dos documentos eletrônicos.

#### Aspectos legais

- Criada pela Medida Provisória nº 2.200-2/2001.
- Regulamentada pelo Decreto nº 3.996/2001.

#### Estrutura

- Autoridade Certificadora Raiz (AC Raiz).
  - É a entidade de topo da hierarquia.
  - Emite os certificados digitais para as Autoridades Certificadoras (ACs) de primeiro nível.
- Autoridades Certificadoras (ACs).
  - Emitir os certificados digitais para pessoas físicas, empresas e outras entidades.
  - Segue as normas estabelecidas pela ICP-Brasil.
  - Responsáveis por verificar a identidade dos solicitantes antes de emitir os certificados.
- Autoridades de Registro (ARs).
  - Intermediárias entre os solicitantes de certificados e as ACs.
  - Receber os pedidos de emissão de certificados.
  - Verificar a identidade dos solicitantes.
  - Encaminhar as solicitações às ACs.
- Comitê Gestor.
  - Estabelecer as políticas, diretrizes e normas técnicas.
  - Composto por representantes do governo, setor empresarial e sociedade civil.

### Norma de segurança ISO/IEC 27.001

#### Características

- Padrão internacional para operar um Sistema de Gestão de Segurança da Informação (SGSI).
- Define os requisitos para estabelecer, implementar, manter e melhorar continuamente.
- Abordagem para gerenciar os riscos de segurança.
- Baseada na abordagem de ciclo de vida Plan-Do-Check-Act (PDCA), melhoria contínua.
- Promove uma cultura de segurança da informação em toda a organização.

#### Visão geral: NBR ISO/IEC 27.000 (Sistema de Gestão de Segurança da Informação - SGSI)

#### Implementação do SGSI: ISO/IEC 27.002

#### Requisitos

1. Estabelecer uma política de segurança da informação.
2. Identificar ativos de informação.
3. Avaliar riscos.
4. Implementar controles de segurança.
5. Monitorar e análisar o desempenho.
6. Melhoria contínua.

### Lei nº 13.709/2018 (Lei Geral de Proteção de Dados Pessoais - LGPD)

- Inspirada no Regulamento Geral de Proteção de Dados (GDPR) da União Europeia.
- Vigência a partir de setembro de 2020.
- Objetivo: garantir a privacidade e a segurança dos dados pessoais.
  - Análise de Impacto de Privacidade (PIA, Privacy Impact Assessment).
    - Potenciais impactos de um processo, sistema de informação, programa, módulo de software ou dispositivo.
    - Relatório com medidas tomadas para o tratamento de riscos.
    - Consulta às partes interessadas.
    - NBR ISO 29134:2020.

#### Princípios

- Finalidade.
  - Propósitos legítimos, específicos e informados aos titulares.
- Adequação.
  - O tratamento dos dados deve ser compatível com a finalidade.
- Necessidade.
  - Coletar apenas os dados necessários para atingir a finalidade.
- Transparência.
  - Informações claras e acessíveis sobre o tratamento dos dados.
  - Necessidade de consentimento expresso.
  - Exceções:
    - Cumprimento de obrigações legais.
    - Proteção da vida.
    - Execução de contratos.
- Segurança.
  - Proteger os dados pessoais contra acesso não autorizado, perda ou vazamento.
- Prestação de contas.
  - Conformidade com a LGPD.
  - Adoção de medidas de segurança adequadas.

#### Direitos dos cidadãos

- Acesso aos dados.
- Correção de informações incorretas.
- Exclusão dos dados.
- Portabilidade para outros serviços.
- Revogação do consentimento.
- Obtenção de informações claras sobre o tratamento dos dados.

#### Sanções

- Advertências.
- Multas de até 2% do faturamento.
- Limitação do tratamento de dados.
- Proibição das atividades relacionadas ao tratamento de dados.

#### ANPD (Autoridade Nacional de Proteção de Dados)

- Regulamentar, fiscalizar e fazer cumprir a LGPD no Brasil.
- Fomentar uma cultura de proteção de dados pessoais.

#### Agentes

- De tratamento:
  - Controlador: decide sobre o tratamento de dados pessoais.
  - Operador: realiza o tratamento de dados pessoais.
- Encarregado: mediador indicado pelos agentes de tratamento entre os titulares e a ANPD.

### ISO 27000, gestão da segurança da informação

#### Características

- Base para o desenvolvimento de um sistema de gestão de segurança da informação (ISMS - Information Security Management System).
- Em acordo com a norma ISO 27001.

#### Conceitos

- Confidencialidade.
  - Proteção das informações contra o acesso não autorizado.
  - Apenas pessoas ou entidades autorizadas devem ter acesso a informações sensíveis ou restritas.
  - Para garantir a confidencialidade, são utilizados controles como criptografia, autenticação e autorização para restringir o acesso.
- Integridade.
  - Garantia de que as informações permaneçam completas e precisas ao longo do tempo e não sejam modificadas de forma não autorizada.
  - Controles que detectam e protegem contra a adulteração de dados, como assinaturas digitais, hashes e sistemas de controle de versões.
- Disponibilidade.
  - Garantir que as informações e sistemas estejam disponíveis quando necessário, sem interrupções não planejadas.
  - Inclui a prevenção e a mitigação de interrupções causadas por falhas técnicas, desastres naturais, ataques cibernéticos e outros eventos imprevistos.
  - São usados mecanismos como redundância, backup e planos de recuperação para manter a disponibilidade.

### Resolução CNJ nº 396/2021 (Estratégia Nacional de Segurança Cibernética do Poder Judiciário - ENSEC-PJ)
