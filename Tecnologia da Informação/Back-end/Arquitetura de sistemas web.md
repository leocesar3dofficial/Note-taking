# Arquitetura de sistemas web

## Protocolo HTTP

- Hypertext Transfer Protocol.
- O HTTP é o protocolo utilizado para comunicação entre clientes (geralmente navegadores) e servidores web.
- Define como as informações são solicitadas e transmitidas na web.
- Permite a transferência de recursos como páginas HTML, imagens e outros elementos da web.
- É stateless: ou seja não guarda estado das conexões.

## SSL (Secure Sockets Layer)

- É um protocolo de segurança que fornece comunicação criptografada entre o cliente e o servidor.
- Garante que os dados transmitidos estejam protegidos contra interceptação e adulteração.
- É essencial para a segurança de transações online e a proteção de informações sensíveis.

## Servidores Proxy

- Atuam como intermediários entre os clientes e os servidores web.
- Podem ser usados para melhorar a segurança, o desempenho e o controle de acesso.
- Permite que os clientes acessem recursos da web por meio do proxy em vez de diretamente com os servidores originais.

## Cache

- É uma técnica que armazena temporariamente cópias de recursos web em um servidor intermediário.
- Reduz o tempo de carregamento e alivia a carga dos servidores originais, melhora o desempenho e a eficiência.

## DNS (Domain Name System)

- É um sistema que traduz nomes de domínio (por exemplo, www.example.com) em endereços IP.
- Permite que os navegadores encontrem os servidores corretos para acessar um site.
- Subdomínio: Inserir um Resource Record (RR) no mapa da zona
  - Exemplo: `rh IN NS ns2.exemplo.com`
    - NS: Name Server (Servidor de Domínio), especifica servidores DNS para o domínio ou subdomínio.
      - Pelo menos, dois registros NS devem ser definidos para cada domínio.
      - Um principal e outro secundário.
    - CNAME: Canonical NAME.
      - Especifica um apelido (alias) para o hostname (A). É uma forma de redirecionamento.

## Balanceamento de Carga

- Distribui o tráfego de entrada entre vários servidores.
- Garante que cada um tenha uma carga equilibrada.
- Melhora o desempenho, a disponibilidade e a escalabilidade de um sistema web.

## Tolerância a Falhas

- Capacidade de um sistema web continuar funcionando mesmo em caso de falha de componentes individuais.
- Usa-se redundância e replicação de recursos.

## Escalabilidade

- Capacidade de um sistema de expandir seus recursos, como servidores e capacidade de armazenamento.
- Atende a um aumento na demanda sem comprometer o desempenho.

## Alta Disponibilidade (High Availability)

- Envolve projetar sistemas de modo que eles estejam sempre disponíveis e operacionais.
- Minimiza interrupções não planejadas.
- 99,99% de disponibilidade ou 52'30'' de indisponibilidade ao ano.

## Clusterização

- Prática de agrupar vários servidores ou recursos em um cluster para aumentar a disponibilidade e o desempenho.

## HAproxy e Nginx

- São servidores proxy e balanceadores de carga populares.
- Usados para melhorar o desempenho e a confiabilidade de sistemas web.

## Plataforma e Infraestrutura como Serviço (SaaS, PaaS, IaaS)

- São modelos de computação em nuvem.
- Fornecem diferentes níveis de abstração e gerenciamento de infraestrutura.
- Desde uma simples hospedagem de aplicativos até a gestão completa de recursos de infraestrutura.

## DevOps e DevSecOps

- Abordagens para integração e colaboração contínua entre equipes de desenvolvimento e operações.
- Visam melhorar a entrega de software e sua segurança.

## CI/CD (Integração Contínua e Entrega Contínua)

- Práticas que automatizam a integração, testes e implantação de código.
- Permitem entregas de software mais frequentes e confiáveis.

## [Docker e Kubernetes](<../Linguagens e padrões/Plataformas de desenvolvimento.md#docker>)

- São tecnologias de contêinerização e orquestração.
- Simplificam o empacotamento, implantação e gerenciamento de aplicativos em ambientes de contêiner.

## [Gerência de Configuração de Software](<Gestão de Configuração.md>)

- Envolve práticas como o uso de sistemas de controle de versão (como o Git).
- Rastrear e gerenciar alterações no código-fonte.
- Organização de repositórios em multirepos ou monorepos.
- Fluxos de trabalho como o Gitflow.
