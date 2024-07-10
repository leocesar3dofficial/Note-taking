# Open Web Application Security Project (OWASP)

Principais vulnerabilidades e remediações.

## Top Ten

1. **Broken Access Control**

   - Descrição:
     - Quebra de Controle de Acesso.
     - O usuário pode agir fora de suas permissões previstas.
   - Prevenções:
     - Negar acesso por padrão (deny by default).
     - Certificar que o usuário não possa acessar recursos ou ações para as quais não têm permissão.
     - Fazer uso de Cross-Origin Resource Sharing (CORS).

2. **Cryptographic Failures**

   - Descrição:
     - Falhas Criptográficas.
     - Trafegar plain text.
     - Usar algoritmos de criptografia fracos.
       - Hash functions: MD5 ou SHA1.
       - Padding methods: PKCS v1 ou v1.5.
   - Prevenções:
     - Não armazene dados confidenciais desnecessariamente.
     - Criptografe todos os dados em trânsito com protocolos seguros, como TLS, com criptografia de sigilo direto, Forward Secrecy (FS).
     - Não use protocolos legados, como FTP e SMTP, para transportar dados confidenciais.
     - Gerenciamento adequado de chaves criptográficas.

3. **Injection**

   - Descrição:
     - Os dados fornecidos pelo usuário não são validados, filtrados ou higienizados/sanitizados pelo aplicativo.
     - Injeção de código, como injeção SQL ou Cross-site Scripting (XSS).
   - Prevenções:
     - Garantir que todas as entradas sejam validadas e sanitizadas de forma apropriada.
     - Usar APIs e ORMs seguros.

4. **Insecure Design**

   - Descrição:
     - Design Inseguro.
     - Falta de perfil de risco do negócio inerente ao software ou sistema que está sendo desenvolvido.
     - Falha em determinar qual nível de design de segurança é necessário.
   - Prevenções:
     - Usar um ciclo de vida de desenvolvimento seguro.
     - Usar corretamente os design patterns, bibliotecas e componentes comprovadamente seguros e atualizados.

5. **Security Misconfiguration**

   - Descrição:
     - Configuração de segurança ineficiente ou errada.
     - Garanta que todas as configurações de segurança sejam corretas e atualizadas.
     - Inclui servidores, frameworks, bibliotecas e bancos de dados.
   - Prevenções:
     - Implantar a cultura e práticas de DevSecOps.

6. **Vulnerable and Outdated Components**

   - Descrição:
     - Uso de componentes com vulnerabilidades conhecidas.
     - Bibliotecas incompatíveis, desatualizadas, não testadas ou corrigidas.
   - Prevenções:
     - Manter bibliotecas e componentes atualizados.
     - Verificar regularmente por vulnerabilidades conhecidas.

7. **Identification and Authentication Failures**

   - Descrição:
     - Qualquer falha na identificação, autenticação e gestão da sessão do usuário.
   - Prevenções:
     - Garantir que a autenticação e o gerenciamento de sessão sigam as boas práticas.
     - Usar práticas como tokens de segurança, autenticação de duplo-fator, expiração de sessão e gerenciamento de senhas.

8. **Software and Data Integrity Failures**

   - Descrição:
     - Uso não auditado de software de terceiros.
     - Desserialização Insegura.
       - Objetos ou dados são codificados ou serializados em uma estrutura que o invasor possa ver e modificar.
   - Prevenções:
     - Implantar boas práticas de testes de segurança para software e serviços de terceiros.

9. **Security Logging and Monitoring Failures**

   - Descrição:
     - Fracassar nos Registros de Segurança e Monitoramento de Falhas.
     - Pŕaticas ineficientes ou insuficientes de registros e monioramento.
   - Prevenções:
     - Implantar a cultura e práticas de DevSecOps.

10. **Server-Side Request Forgery (SSRF)**

- Descrição:
  - Falsificação de Solicitação do Lado do Servidor.
  - Ocorre sempre que um aplicativo da web busca um recurso remoto sem validar a URL fornecida pelo usuário.
- Prevenções:
  - Camada da rede: segmentar recursos remotos em redes diferentes e aplicar o conceito de "deny by default".
  - Camada da aplicação: sanitizar e validar todo input do usuário e desabilitar redirecionamentos.

## Common Weakness Enumeration (CWE)

É uma lista desenvolvida pela comunidade de pontos fracos comuns de software e hardware.

### Cross-Site Scripting (XSS)

- Proteja seu aplicativo contra ataques XSS.
  - Utilizar tokens anti-CSRF.
    - Inclua tokens de segurança exclusivos em formulários e solicitações que exigem ações sensíveis.
    - Esses tokens devem ser verificados no lado do servidor para garantir a legitimidade da solicitação.
  - Implementar políticas de mesma origem (Same-Origin Policy).
    - Configure seu aplicativo para que ele só aceite solicitações de origens confiáveis.
    - Ajuda a prevenir solicitações de sites não autorizados.
  - Utilizar cabeçalhos HTTP apropriados.
    - Cabeçalhos.
      - Host: contém o DNS do servidor.
    - Configure cabeçalhos HTTP, como o cabeçalho "Referer" e o cabeçalho "Origin".
    - Para verificar a origem de solicitações e rejeitar solicitações de fontes não autorizadas.
  - Exigir autenticação sensível.
    - Solicitações que envolvem ações sensíveis devem exigir autenticação adicional.
    - Como a solicitação de senha ou autenticação de dois fatores.
  - Fornecer confirmação para ações críticas.
    - Como a exclusão de uma conta ou transferência de fundos.
    - Solicite que o usuário confirme a ação, mesmo que já esteja autenticado.
  - Validar e escapar adequadamente todas as saídas de dados.

### Cross-Site Request Forgery (CSRF)

- Implemente tokens anti-CSRF para evitar que um atacante force usuários a realizar ações indesejadas.
- Evite que os atacantes enganem os usuários para realizar ações não autorizadas por meio de solicitações maliciosas.

### Redirecionamentos e Encaminhamentos Inseguros

- Evite redirecionamentos (Redirects) e encaminhamentos (Forwards) inseguros que possam ser explorados por atacantes.

### Path Transversal

- Tem como objetivo acessar arquivos e diretórios que estão armazenados fora do diretório utilizado pela aplicação (Webroot).
