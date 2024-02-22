# Internet das Coisas - IoT

## Histórico

- 1958, DARPA, Defense Advanced Research Projects Agency
  - Desenvolveu o programa de comunicação entre computadores
  - Recebeu o nome de Interfaces Message Processors (IMP)
  - Parceria com as universidades da Califórnia, Stanford e UTAH
- 1978, BBS, Bulletin Board System, similar to email
- 1992, Internet como a conhecemos
  - Tim Bernes-Lee criou a World Wide Web, WWW
  - Hipertexto

## Conectividade

### Redes

- PAN, Personal Area Network
  - Bluetooth: o mais comum para redes de curto alcance
  - Zigbee: para lâmpadas, tomadas, sensores e smart objects
  - IRDA, Infrared Data Association: via luz, ex. controle remoto da TV
- WiFi, conexão sem fio
- LAN, rede Local
- MAN, Metropolitan Area Network
  - Utilizada em serviços públicos de segurança, saúde, etc.
- WAN, ou Internet

### Meios de transmissão de dados

- Luz (fibra ótica), ar (Wi-Fi) e metal (cabos de cobre, alumínio)

### DNS, Domain Name System

- **Definição**
  - Traduz nomes de domínio legíveis por humanos em endereços IP legíveis por máquina
  - Exemplo: www.websitename.com para um intervalo alfanumérico
    - IPV6: de 0000:0000:0000:0000:0000:0000:0000:0000 até ffff:ffff:ffff:ffff:ffff:ffff:ffff:ffff
    - Capacidade: 340 undecilhões (10 elevado a 36) de endereços
- **Infraestrutura**
  - Servidor local e nacional
  - Sistema de tradução de domínios

### Domínio

- É o endereço de um site na internet na forma de um nome
- **Tipos**
  - Genéricos: art, com, eco, emp, net, ong
  - Universidades: edu
  - Entidades: gov, mil, org
- **Registro**
  - Tabela DNS
    - Endereço MAC de Origem (ID de fábrica da placa de rede)
      - Pode ser usado para detectar aparelhos conectados sem autorização
    - IP de Origem
    - Nome da máquina de origem (configurado no Sistema Operacional)
    - Requisição
    - IP de destino
    - Nome da máquina/domínio de destino

### TCP, Transmission Control Protocol

- Pacote ou package.

### IP, Internet Protocol

### Velocidade de navegação

- Medida em Mbps (Megabits por segundo)
- Tempo de download = tamanho do arquivo (MB) / velocidade (MBps)
- MBps = Mbps / 8

### Nuvem ou cloud

- Serviços oferecidos via Internet
- Infraestrutura, software e dados remotos
- **Exemplos**
  - Amazon AWS, Microsoft Azure, NETFLIX
- **Tipos**
  - Pública (Serviços Google, Microsoft, Amazon)
  - Privada (servidores da própria organização)
  - Híbrida (utilizada por médias e grandes empresas)
- **Benefícios**
  - Economia e Retorno de Investimento
  - Disponibilidade e menor downtime
  - Escalabilidade e balanceamento de capacidade
  - Resiliência e redirecionamento de processamento
  - Mobilidade
  - Sustentabilidade e Eco-responsabilidade
  - Otimizar equipes de TI
- **Desafios**
  - Acesso deficitário à Internet
  - Medidas de segurança para os usuários
    - Atualizar os equipamentos
    - Alterar a senha padrão dos dispositivos
    - Testes Periódicos
    - Criação de uma rede específica
    - Uso de Antivírus, Firewall e Proxy
  - Confiabilidade perante os stakeholders

## Hardware e infraestrutura

### Equipamentos

- **Roteador (Router)**
  - Conecta duas redes, normalmente residência/negócio ao provedor
- **Switch**
  - Conexões ou portas para os equipamentos se conectarem ao roteador (cabo ou WiFi)
    - Padrões
      - IEEE 802.11 (Wi-Fi)
      - IEEE 802.3 (Fast Ethernet [cabo que usa MAC])
        - 10BASE-T ➜ limite de 10 Mbps
        - 100BASE-T ➜ UTP ➜ cat 3 ➜ 4 pares trançados ➜ Codificação Manchester
          - Modo Half-duplex ou Full-duplex
        - 100BASE-TX ➜ UTP ➜ cat 5 ➜ 2 pares trançados ➜ Full duplex ➜ Codificação 4B/5B
        - 100BASE-FX ➜ Fibra ➜ Multimodo ➜ Full duplex
      - IEEE 802.5 (Token Ring)
      - IEEE 802.8 (Fibra ótica)
        - 100BASE-F
      - IEEE 802.15 (Bluetooth)
- **Hub**
  - Tipo de switch onde toda a comunicação e disponibilizada para todos os equipamentos
  - Não é comum utilizá-lo atualmente, foi substituído pelo Switch
- **Ponto de Acesso (Access Point)**
  - Repetidor de WiFi
- **Dongle WiFi**
  - Pendrive para conexão em rede para dispositivos móveis
- **Links de conexão**
  - ADSL (linha telefônica), Cabo de TV, Rádio, Fibra ótica e móvel ( 4G, 4,5G e 5G)

### Eletricidade

- **Corrente elétrica**
  - Alternada (Nickolas Tesla)
    - Longa distância com perdas pequenas e menos geradores
  - Contínua (Thomas Edison)
    - Mais segura
    - Amplamente utilizada

### Componentes eletrônicos

- **Transformador**
  - De corrente alternada da tomada para corrente contínua para os equipamentos eletrônicos
- **Resistor ou Resistência**
  - Diminuir a intensidade da corrente elétrica
- **Capacitores**
  - Armazenar cargas elétricas em um campo elétrico
  - Unidade de medida: microfarad (µF), nanofard(nF) ou picofarad(pF)
- **Indutores**
  - Armazenar cargas elétricas em um campo magnético
  - Unidade de medida: HENRYS (H)
- **Diodos**
  - Determinar o sentido da corrente elétrica
  - Evitar que outras partes do equipamento sejam queimadas, só o diodo é perdido
- **LED (Ligth-Emitting Diode, Diodo Emissor de Luz)**

### Automação

- **Raspberry PI (micro computador)**
  - Fundação criada em 2006, Universidade de Cambridge
  - Preço acessível
  - Configurar um servidor DNS para receber comandos via Internet
- **Arduino (micro controlador)**
  - Placa de hardware livre
  - Massimo Benzi, David Cuartielles, Tom Igoe, Gianluca Martino e David Mellis, Itália
  - **Entradas**
    - Sensores como ultrassom, termômetros
    - Motores
    - Módulos de conexão: Ethernet, Bluetooth e WiFi
    - Outras placas controladoras
  - **Modelos** Uno, Mega ou Nano
- **Emulador Fritzing**

## Legislação

- Lei nº 12.965/2014, Marco Civil da Internet
- Lei nº 13.709/2018, Lei Geral de Proteção de Dados
- Decreto nº 9.854/2019, Plano Nacional de Internet das Coisas

## Mercado de trabalho (Indústria 4.0)

- Quarta revolução industrial
- **Especialidades**
  - Segurança para IoT
  - Redes LP SP e LP WAN
  - Processadores e Microcontroladores
  - Sistemas Operacionais de tempo real e de Cloud
  - Padronizações
  - Ecossistemas
