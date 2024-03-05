# Open Web Application Security Project (OWASP)

## Top Ten

1. **Injeção**

   - Evite injeções de código (SQL, XSS, etc.)
   - Garante que todas as entradas sejam validadas e sanitizadas de forma apropriada

2. **Quebra de Autenticação e Gerenciamento de Sessão**

   - Garanta que a autenticação e o gerenciamento de sessão sejam sólidos
   - Use práticas como tokens de segurança e expiração de sessão

3. **Cross-Site Scripting (XSS)**

   - Proteja seu aplicativo contra ataques XSS
     - Utilizar tokens anti-CSRF
       - Inclua tokens de segurança exclusivos em formulários e solicitações que exigem ações sensíveis
       - Esses tokens devem ser verificados no lado do servidor para garantir a legitimidade da solicitação
     - Implementar políticas de mesma origem (Same-Origin Policy)
       - Configure seu aplicativo para que ele só aceite solicitações de origens confiáveis
       - Ajuda a prevenir solicitações de sites não autorizados
     - Utilizar cabeçalhos HTTP apropriados
       - Cabeçalhos
         - Host: contém o DNS do servidor.
       - Configure cabeçalhos HTTP, como o cabeçalho "Referer" e o cabeçalho "Origin".
       - Para verificar a origem de solicitações e rejeitar solicitações de fontes não autorizadas.
     - Exigir autenticação sensível.
       - Solicitações que envolvem ações sensíveis devem exigir autenticação adicional.
       - Como a solicitação de senha ou autenticação de dois fatores
     - Fornecer confirmação para ações críticas
       - Como a exclusão de uma conta ou transferência de fundos
       - Solicite que o usuário confirme a ação, mesmo que já esteja autenticado
     - Validar e escapar adequadamente todas as saídas de dados

4. **Request Forgery (Cross-Site Request Forgery, CSRF)**

   - Implemente tokens anti-CSRF para evitar que um atacante force usuários a realizar ações indesejadas

5. **Quebra de Controle de Acesso (Broken Access Control)**

   - Certifique-se de que os usuários não possam acessar recursos ou ações para as quais não têm permissão

6. **Exposição de Dados Sensíveis**

   - Proteja dados confidenciais, usando criptografia e técnicas de mascaramento

7. **Configuração Incorreta de Segurança**

   - Garanta que todas as configurações de segurança sejam corretas e atualizadas
   - Incluindo servidores, frameworks e bibliotecas

8. **Cross-Site Request Forgery (CSRF)**

   - Evite que os atacantes enganem os usuários para realizar ações não autorizadas por meio de solicitações maliciosas

9. **Uso de Componentes com Vulnerabilidades Conhecidas**

   - Mantenha seus componentes de software atualizados e verifique regularmente se eles não têm vulnerabilidades conhecidas

10. **Redirecionamento e Encaminhamento Inseguros**
    - Evite redirecionamentos e encaminhamentos inseguros que possam ser explorados por atacantes

## Principais vulnerabilidades e remediações (OWASP Top Ten)

1. **Broken Access Control (Quebra de Controle de Acesso)**

   - User can act outside of his intended permissions

2. **Cryptographic Failures (Falhas Criptográficas)**

3. **Injection (Injeção)**

   - Cross-site Scripting

4. **Insecure Design (Design Inseguro)**

5. **Security Misconfiguration (Configuração Insegura)**

6. **Vulnerable and Outdated Components (Componente Desatualizado e Vulnerável)**

   - Bibliotecas incompatíveis, desatualizadas, não testadas ou corrigidas

7. **Identification and Authentication Failures (Falha de Identificação e Autenticação)**

8. **Software and Data Integrity Failures (Falha na Integridade de Dados e Software)**

   - Desserialização Insegura

9. **Security Logging and Monitoring Failures (Monitoramento de Falhas e Registros de Segurança)**

   - Registro e Monitoramentos Insuficientes

10. **Server Side Request Forgery (Falsificação de Solicitação do Lado do Servidor)**

## Common Weakness Enumeration (CWE)

É uma lista desenvolvida pela comunidade de pontos fracos comuns de software e hardware.
