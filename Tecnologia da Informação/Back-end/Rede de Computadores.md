# Rede de Computadores

## Arquitetura TCP/IP

### Protocolos

- Conjunto de protocolos utilizados para a comunicação na Internet.
- TCP (Transmission Control Protocol).
- IP (Internet Protocol).
- Fundamentais para o funcionamento da Internet.

### Segmentação e Endereçamento

- O endereçamento IP é usado para identificar dispositivos em uma rede
- Os endereços IPv4 consistem em quatro grupos de números
  - Exemplos
    - 192.168.136 e 140 (Rede)
    - 192.168.137 (Host)
    - 192.168.139 (Broadcast)
- O IPv6 usa endereços muito mais longos
- Segmentação refere-se à divisão de dados em pacotes para transmissão pela rede

### Camadas

1. **Fisica:**

Modem, RDIS, RS-32, EIA- 422, RS-449, Bluetooth, USB

2. **Enlance:**

Ethernet, 802.11 WIFI, IEEE 802.1Q, 802.11G, HDLC, Token ring, FDDI, PPP, Switch, Frame relay

3. **Rede:**

IP (IPV4, IPV6), ARP, RARP, ICMP, IPSec, etc

4. **Transporte:**

- **TCP (Transmission Control Protocol)**

   - Orientado à conexão
   - Garantir a entrega ordenada e sem erros de dados entre aplicativos em uma rede
   - Controle de congestionamento, retransmissão de pacotes perdidos e confirmações
      - Garantir a confiabilidade na entrega dos dados
   - É utilizado em navegadores da web, e-mail e transferência de arquivos.

- **UDP (User Datagram Protocol)**

   - Não confiável e sem conexão
   - Transmite dados sem garantia de entrega ou ordenação
   - UDP é mais rápido e mais eficiente em termos de sobrecarga de rede do que TCP
   - Usado em aplicativos onde uma pequena perda de dados não é crítica
      - Streaming de vídeo
      - Jogos online
      - Transmissão de áudio em tempo real

- **RTP (Real-Time Transport Protocol)**

   - Projetado para transmissão em tempo real de dados
      - Videoconferência
      - Streaming de vídeo
      - Telefonia VoIP (Voice over IP)
   - Possui controle de atraso, compensação de jitter e sequenciamento de pacotes
   - Usado em conjunto com o RTCP

- **SCTP (Stream Control Transmission Protocol)**

   - Orientado a mensagens
      - Telefonia IP
      - Sinalização de redes de telecomunicações
      - Transferência de arquivos
   - Confiabilidade, entrega ordenada e controle de congestionamento
   - Suporta múltiplos fluxos de dados (multiplexada) dentro de uma única conexão
   - Robusto contra ataques
      - Negação de serviço (DoS)
      - Flooding

- **DCCP (Datagram Congestion Control Protocol)**

  - Combina algumas características do TCP e do UDP
  - Controle de congestionamento, semelhante ao TCP, e suporta transmissões não confiáveis, semelhante ao UDP
  - Usado em aplicações que exigem comunicação em tempo real com tolerância a perdas de dados, como jogos online e transmissões de vídeo
  - Os aplicativos escolhem diferentes perfis de serviço, dependendo das necessidades de confiabilidade e latência

5. **Aplicação:**

HTTP, SMTP (Envio de emails), FTP, SSH, TELNET, SIP, RDP, IRC, SNMP, NNTP (Network News Transfer Protocol, grupos de discussão, obsoleto),
POP3 (Post Office Protocol, receber emails),
IMAP (Internet Message Access Protocol),
- realiza o sincronismo entre o cliente e o servidor de e-mail
- acessa as caixas de mensagens que estão no servidor de correio
- replica as ações de leitura ou troca de diretório no servidor
- permite que as mensagens sejam guardadas tanto na máquina local quanto no servidor
- envia, recebe, sincroniza, webmail
- mais avançado que o POP3
  BitTorrent, DNS, PING, etc.

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
- **Dispositivos**
   - Network-Attached Storage (NAS)
      - Armazenar, Gerenciar e Compartilhar arquivos entre vários dispositivos conectados à rede local
      - Hardware de armazenamento conectado à rede

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
  - IEEE 802.11: É uma família de padrões para redes sem fio (Wi-Fi)
    - 802.11a e 802.11n: usados tanto para frequência 2.4 GHz quanto 5 GHz

### VSAT (Very Small Aperture Terminal)

- É uma tecnologia de comunicação por satélite
- Permite a conexão à internet e outros serviços de comunicação de longa distância
- Composta por estações terrestres de pequeno porte ou terminais VSAT
- Se comunicam com satélites em órbita
- Usadas em comunicações empresariais, governamentais, militares e de transporte
- Em locais remotos sem acesso à internet via cabo ou fibra ótica
- Oferecem uma solução de comunicação de alta velocidade e confiável para esses locais
- Não dependem de infraestruturas terrestres
- São menos suscetíveis a interrupções ou falhas devido a condições climáticas ou desastres naturais
- Projetadas para atender às necessidades de largura de banda em constante mudança e crescimento
- Oferece uma ampla gama de opções de serviços de comunicação, incluindo voz, dados e vídeo

## Topologia de rede

1. **Topologia de Estrela:**

   - Todos os dispositivos estão conectados a um ponto central, que geralmente é um hub ou switch.
   - A falha de um dispositivo não afeta diretamente os outros, mas se o ponto central falhar, toda a rede pode ser impactada.

2. **Topologia de Barramento:**

   - Todos os dispositivos compartilham um único meio de comunicação, que é geralmente um cabo coaxial ou uma linha de fibra ótica.
   - A comunicação ocorre ao longo desse canal compartilhado.

3. **Topologia de Anel:**

   - Os dispositivos são conectados formando um anel fechado.
   - Os dados fluem em uma direção ao longo do anel.

4. **Topologia de Malha:**

   - Cada dispositivo está conectado a todos os outros dispositivos na rede.
   - Oferece redundância e desempenho robusto, mas pode ser dispendiosa de implantar.

5. **Topologia de Árvore (ou Hierárquica):**

   - Assemelha-se a uma estrutura de árvore com uma raiz central e ramos conectados a ela.
   - Permite expansão fácil, mas pode ser complexa de gerenciar.

6. **Topologia Híbrida:**

   - Combina dois ou mais tipos de topologias.
   - Por exemplo, uma combinação de topologia de estrela e topologia de anel.

7. **Topologia de Ponto a Ponto:**

   - Cada dispositivo está conectado diretamente a outro dispositivo, formando uma rede ponto a ponto.
   - Muito comum em redes de comunicação entre dois dispositivos.

8. **Topologia de Grade:**
   - Dispositivos são organizados em linhas horizontais e verticais, formando uma grade.
   - Cada dispositivo está conectado aos dispositivos adjacentes.

## Equipamentos de rede

### Balanceador de carga

- Os recursos são combinados de forma eficaz para a distribuição das requisições por todos os sistemas.

### Switch

- Conecta dispositivos em uma rede local (LAN).

### Roteador

- Encaminha pacotes de dados entre redes computacionais.

### Access Point (Ponto de Acesso)

- Permite que dispositivos sem fio se conectem a uma rede com fio.

## Qualidade de Serviço (QoS)

- Capacidade de priorizar determinados tipos de tráfego na rede para garantir um nível adequado de serviço
- Serviços Diferenciados e Serviços Integrados: abordagens para implementar QoS em redes
- **Failover**: movimentação de direcionamento de sistemas primários para equipamentos de redundância, em caso de falhas

## Aplicações de Voz e Vídeo sobre Redes

- Voz sobre IP (VoIP): Permite a transmissão de chamadas telefônicas pela Internet
- Vídeo sobre IP: Permite a transmissão de vídeo pela rede

### Protocolos baseados na especificação H.323

Criado pelo International Telecommunication Union Telecommunication Standardization Sector (ITU-T)

#### Protocolos

- **H.225.0:** Registration, Admission and Status (RAS).
- **H.225.0** Call Signaling based on Q.931.
- **H.245** control protocol for multimedia communication,
  - Describes the messages and procedures used for capability exchange.
  - Opening and closing logical channels for audio, video and data, control and indications.
- Real-time Transport Protocol (RTP), for sending or receiving multimedia information (voice, video, or text) between any two entities.
- **H.235** series describes security within H.323, including security for both signaling and media.
- **H.239** describes dual stream use in videoconferencing, usually one for live video, the other for still images.
- **H.450** series describes various supplementary services.
- **H.460** series defines optional extensions that might be implemented by an endpoint or a Gatekeeper, including ITU-T Recommendations H.460.17, H.460.18, and H.460.19 for Network address translation (NAT) / Firewall (FW) traversal.

#### Codecs

- **Audio codecs:** G.711, G.729 (including G.729a), G.723.1, G.726, G.722, G.728, Speex, AAC-LD.
- **Text codecs:** T.140.
- **Video codecs:** H.261, H.263, H.264, H.265.

## Multicast, IGMP, PIM-SM

- Multicast: Transmissão de dados para múltiplos destinos simultaneamente
- IGMP (Internet Group Management Protocol): Usado por hosts para reportar sua associação a grupos multicast
- PIM-SM (Protocol Independent Multicast - Sparse Mode): Um protocolo de roteamento multicast

## Software Defined Networks (SDN)

- SDN: Uma abordagem de rede que separa o plano de controle do plano de dados, permitindo a programação dinâmica da rede.

## Padrões e Normas de Cabeamento Estruturado

- NBR 14565 e ISO/IEC 11801: Normas relacionadas ao cabeamento de redes internas em edifícios.
- NBR 16665 e ISO/IEC 24764: Normas para data centers.
- EIA/TIA 568A e 568B: Normas para a conectorização UTP (par trançado não blindado).

## Serviços de Rede Microsoft Windows Server

- DNS: Sistema de Nomes de Domínio.
  - Whois.
    - É um protocolo usado para consultar os bancos de dados.
    - Armazenam as informações sobre quem são os proprietários ou registrantes de um domínio.
    - Protocolo de consultas e respostas sobre DNS.
    - Um dos protocolos mais antigos da web.
- DHCP: Protocolo de Configuração Dinâmica de Hosts.
- RADIUS: Protocolo de autenticação e autorização.
- Autenticação, Certificados: Métodos de segurança.
- Active Directory (AD).
  - Serviço de diretório utilizado para gerenciar recursos em uma rede Windows.
  - Árvore, floresta, domínios Windows.
  - Comandos de terminal:
    - Remover um grupo e outros objetos: `dsrm <objeto>`  

## Modelo OSI (Open System Interconnection)

- Modelo de rede de computador referência da ISO dividido em camadas de funções
- Usado em uma rede local (Ethernet)
- Camadas
  1. Camada física
  2. Camada de enlace ou link de dados
  - Subcamadas
    - MAC (Media Access Control)
      - Próxima da camada física (inferior)
    - LLC (Logical Link Control)
      - Próxima da camada de rede (superior)
  3. Camada de rede
  4. Camada de transporte
  5. Camada de sessão
  6. Camada de apresentação
     - Criptografia e compactação de dados dos serviços web
  7. Camada de aplicação
