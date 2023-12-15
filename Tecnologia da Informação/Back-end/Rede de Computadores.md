# Rede de Computadores

## Arquitetura TCP/IP

### Protocolos

- Conjunto de protocolos utilizados para a comunicação na Internet
- TCP (Transmission Control Protocol)
- IP (Internet Protocol)
- Fundamentais para o funcionamento da internet

### Segmentação e Endereçamento

- O endereçamento IP é usado para identificar dispositivos em uma rede
- Os endereços IPv4 consistem em quatro grupos de números
- O IPv6 usa endereços muito mais longos
- Segmentação refere-se à divisão de dados em pacotes para transmissão pela rede

## Protocolos de Roteamento

### Roteamento Estático

- As rotas são configuradas manualmente pelo administrador de rede
- OSPF (Open Shortest Path First)
  - É um protocolo de roteamento dinâmico que utiliza o algoritmo SPF para calcular as rotas mais curtas
- BGP (Border Gateway Protocol)
  - É um protocolo utilizado em redes externas à internet e é usado para roteamento entre sistemas autônomos

## Tipos de redes

### LAN (Local Area Network)

- É uma rede de curto alcance, geralmente em um único local físico

### PAN (Personal Area Network)

- Conecta dispositivos eletrônicos dentro da área imediata de um usuário
- O alcance varia de alguns centímetros a alguns metros

#### NFC (Near Field Communication)

- **Casos de uso da comunicação com campo de aproximação**
  - Cartão de crédito por aproximação
  - Chave/Cartão de hotel ou para acesso à área restrita
  - Smartphone para fazer pagamento

### VLAN (Virtual LAN)

- Permite a segmentação lógica de redes em uma LAN física

### MAN (Metropolitan Area Network)

- Uma rede metropolitana abrange uma área geográfica maior, como uma cidade

### WAN (Wide Area Network)

- Redes de longa distância que conectam locais geograficamente distantes

### Rede sem fio (Wireless)

- Permitem a conexão de dispositivos sem fio, usando padrões como 802.11 (Wi-Fi)
  - Frequências Licenciadas
    - São frequências de rádio que requerem uma licença para uso devido à regulamentação governamental
  - Propagação de Sinais
    - Forma como os sinais de rádio se propagam no ambiente, sofrendo atenuação e interferência
  - 802.11: É uma família de padrões para redes sem fio

### VSAT (Very Small Aperture Terminal)

- É uma tecnologia de comunicação por satélite
- Permite a conexão à internet e outros serviços de comunicação de longa distância
- Composta por estações terrestres de pequeno porte ou terminais VSAT
- Se comunicam com satélites em órbita
- Usadas em comunicações empresariais, governamentais, militares e de transporte
- Em locais remotos sem acesso à internet via cabo ou fibra óptica
- Oferecem uma solução de comunicação de alta velocidade e confiável para esses locais
- Não dependem de infraestruturas terrestres
- São menos suscetíveis a interrupções ou falhas devido a condições climáticas ou desastres naturais
- Projetadas para atender às necessidades de largura de banda em constante mudança e crescimento
- Oferece uma ampla gama de opções de serviços de comunicação, incluindo voz, dados e vídeo

## Equipamentos de rede

### Balanceador de carga

- Os recursos são combinados de forma eficaz para a distribuição das requisições por todos os sistemas
- TODO: OUTROS EQUIPAMENTOS

## Qualidade de Serviço (QoS)

- Capacidade de priorizar determinados tipos de tráfego na rede para garantir um nível adequado de serviço
- Serviços Diferenciados e Serviços Integrados: abordagens para implementar QoS em redes
- **Failover**: movimentação de direcionamento de sistemas primários para equipamentos de redundância, em caso de falhas

## Aplicações de Voz e Vídeo sobre Redes

- Voz sobre IP (VoIP): Permite a transmissão de chamadas telefônicas pela Internet
- Vídeo sobre IP: Permite a transmissão de vídeo pela rede

## Multicast, IGMP, PIM-SM

- Multicast: Transmissão de dados para múltiplos destinos simultaneamente
- IGMP (Internet Group Management Protocol): Usado por hosts para reportar sua associação a grupos multicast
- PIM-SM (Protocol Independent Multicast - Sparse Mode): Um protocolo de roteamento multicast

## Software Defined Networks (SDN)

- SDN: Uma abordagem de rede que separa o plano de controle do plano de dados, permitindo a programação dinâmica da rede

## Autenticação 802.1x

- 802.1x: Um protocolo de autenticação utilizado em redes com e sem fio

## Padrões e Normas de Cabeamento Estruturado

- NBR 14565 e ISO/IEC 11801: Normas relacionadas ao cabeamento de redes internas em edifícios
- NBR 16665 e ISO/IEC 24764: Normas para data centers
- EIA/TIA 568A e 568B: Normas para a conectorização UTP (par trançado não blindado)

## Serviços de Rede Microsoft Windows Server

- DNS: Sistema de Nomes de Domínio
  - Whois
    - É um protocolo usado para consultar os bancos de dados
    - Armazenam as informações sobre quem são os proprietários ou registrantes de um domínio
    - Protocolo de consultas e respostas sobre DNS
    - Um dos protocolos mais antigos da web
- DHCP: Protocolo de Configuração Dinâmica de Hosts
- RADIUS: Protocolo de autenticação e autorização
- Autenticação, Certificados: Métodos de segurança
- Active Directory (AD)
  - Serviço de diretório utilizado para gerenciar recursos em uma rede Windows
  - Árvore, floresta, domínios Windows

## Modelo OSI (Open System Interconnection)

- Modelo de rede de computador referência da ISO dividido em camadas de funções
- Usado em uma rede local (Ethernet)
- Dividido em 7 camadas
  1. Camada física
  2. Camada de enlace de dados
  3. Camada de rede
  4. Camada de transporte
  5. Camada de sessão
  6. Camada de apresentação
  7. Camada de aplicação
