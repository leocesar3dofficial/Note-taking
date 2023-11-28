# Resiliência de Aplicações

## Características
- Capacidade de uma aplicação ou sistema de software continuar funcionando, mesmo quando ocorrem falhas, interrupções ou eventos inesperados.
- Garante que os usuários tenham uma experiência contínua, mesmo em situações adversas.
- Fundamental para manter a continuidade dos serviços e a satisfação do cliente.

## Técnicas

### Cache
- Armazenamento temporário de dados frequentemente acessados em um local de fácil acesso.
- Reduz a necessidade de acessar fontes de dados lentas, como bancos de dados.
- Melhora o desempenho e a disponibilidade da aplicação.
- Requer estratégias de invalidação para garantir que os dados em cache estejam sempre atualizados.

### Fallback
- Fornece um plano de contingência quando um serviço ou recurso primário falha.
- Inclui a comutação para um serviço secundário ou a exibição de conteúdo de backup para os usuários.

### Circuit Breaker
- É um padrão de projeto que ajuda a evitar chamadas repetitivas a um serviço que está falhando.
- Detecta falhas repetidas e abre um "disjuntor" para evitar chamadas subsequentes, permitindo que o sistema se recupere.

### Disaster Recovery
- Garante que os sistemas da aplicação possam ser restaurados após uma falha catastrófica, como incêndios, terremotos ou falhas de energia.
- Envolve a criação de cópias de segurança e planos de continuidade de negócios.

### Contingência
- Criação de estratégias de contingência para responder a falhas específicas.
- Inclui a disponibilização de servidores ou recursos de backup em caso de falha.

### Balanceamento de Carga Global de Servidores (GSLB)
- Distribui o tráfego da aplicação por vários servidores em diferentes locais geográficos.
- Melhora o desempenho e a disponibilidade da aplicação, redirecionando o tráfego para servidores disponíveis quando ocorrem falhas.

### Site Ativo X Ativo
- Estratégia de alta disponibilidade.
- Envolve a configuração de vários sites ou data centers para atender ao tráfego simultaneamente.
- Se um site falhar, o tráfego é redirecionado automaticamente para outro site ativo.
