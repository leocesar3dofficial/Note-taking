# Sistemas Operacionais

## Conceito

### Antigo

- Software que controla o hardware

### Atual

- Realizar a separação entre as aplicações (software e hardware)
- Estabelecer controle de acesso
- Conjunto de serviços e permitir a comunicação entre eles

## História

### Primeira fase (1945 a 1955)

- Válvulas
- Chaves mecânicas com comandos bit-a-bit e convertidos em linguagem de máquina
- Cartões perfurados com uma sequência de comandos
- Linguagens: Fortran e Assembly
- Primeiro SO: GM-NAA I/O da General Motors, 1950, usado em computadores IBM
- Processadores escalares: instruções individuais
- Processamento em lote ou batch

### Segunda fase

- Transistor e memória magnética
- Fita magnética, 1957

### Terceira fase (1965 a 1980)

- Série 360 de computadores da IBM, tanto para uso científico quanto comercial
- Adoção dos Circuitos Integrados (CI) ou Small Scale Integration (SSI)
- Sistema Operacional OS/360
- Multiprogramação: execução simultânea de vários programas
- Time sharing: evolução da Multiprogramação
- Diminuição do tempo de resposta: de horas para segundos
- TSS, Multics e CP/CMS: memória virtual
  - Técnica que permite a execução de processos que não estão totalmente na memória.
  - Os programas podem ser maiores do que a memória física (RAM).
- Unix, 1971
  - AT&T Bell Laboratories
  - por Ken Thompson, Dennis Ritchie, Douglas McIlroy e Joe Ossanna
- Linguagem C, alto nível, 1973
- Transmission Control Protocol/Internet Protocol (TCP/IP)
- Ethernet, Xerox: redes locais, Local Area Network – LAN
- Primeiro microprocessador para computadores pessoais: Intel 8080

### Quarta fase (1981 em diante)

- Microchips de silício
- Popularização dos microcomputadores pessoais
- Interface humana: Graphical User Interface (GUI), Xerox, Mouse
- Microsoft MS-DOS, 1981 e Apple Macintosh, 1984
- Movimento de software livre, Richard Stallman, 1983
  - GNU é um sistema operacional tipo, mas não, Unix, composto por software livre
  - Free Software Foundation (FSF), 1985
  - Linux, Linus Torvalds, baseado no Unix
- Sistemas Operacionais distribuídos
  - Vários processadores
  - Modelo cliente/servidor (client/server)
- Multiprocessamento, final da década de 1980
  - Processadores vetoriais ou processadores de matriz
    - Conjunto de instruções
    - No formato de matrizes unidimensionais de dados ou vetores
  - Paralelismo: execução simultânea das tarefas
- Hardware plug-and-play
- Linux
  - Núcleo lançado em 1991, versão 0.02
  - Com licença GPL (General Public License), criada pelo Projeto GNU
  - Distribuições GNU/Linux
    - Arch Linux, CentOS, Debian, Fedora Linux,
    - Linux Mint, openSUSE, Ubuntu, Red Hat Enterprise, etc

## Categorias

### Sistemas embarcados

- Computadores dedicados ou embutidos
- Pervasivos ou ubíquos
- Presentes nos eletroeletrônicos, hardwares de rede,
  equipamentos hospitalares, automóveis, etc

### Sistemas de tempo real

- Lavadoras de roupa, DVD players, Smart TVs,
  Sistemas militares de defesa, controle de tráfego aéreo,
  respiração artificial de pacientes em UTIs, consoles de games

### Sistemas críticos em negócios

- Servidores web, servidores de bancos de dados

### Camada de virtualização

- A virtualização é uma tecnologia que permite a criação de ambientes virtuais que simulam o comportamento de um sistema operacional real
- Máquinas Virtuais (hypervisor)
  - VM opera de maneira independente e isolada
  - Não confundir com emulação
  - Criadas a partir de um software chamado hipervisor
    - Tipo 1: é executado diretamente no hardware do computador e é responsável por gerenciar as VMs
    - Tipo 2: é executado em cima de um sistema operacional já existente e é responsável por gerenciar as VMs
  - Exemplos
    - Xen
      - É um hypervisor de tipo 1
      - Permite a execução simultânea de vários sistemas operacionais em um único hardware
      - Usado em servidores e data centers
    - KVM (Kernel-based Virtual Machine)
      - É um hypervisor de tipo 1
      - Permite a execução simultânea de vários sistemas operacionais em um único hardware
      - Baseado no kernel do Linux e faz parte do código do Linux existente
      - Aproveita todas as funcionalidades, correções e avanços novos do Linux sem engenharia adicional
    - VirtualBox
      - É um hypervisor de tipo 2
      - Permite a execução de vários sistemas operacionais em um único hardware
      - Usado em desktops e laptops
    - Java Virtual Machine (JVM)
      - É um hypervisor de tipo 2
      - Executada em cima de um sistema operacional já existente e é responsável por gerenciar as VMs
      - Implementação: HotSpot da Oracle

## Componentes

### Centrais

- Núcleo (kernel).
- Escalonador de processos.
- Memória.
  - Componentes (do mais rápido para o mais lento).
    - Registradores.
    - Memória cache da CPU.
    - Memória principal, RAM.
      - Memória lógica.
      - Memória física.
    - Memória de armazenamento em massa (disco e sólido).
  - Gerenciador.
    - Alocar a memória aos processos, quando for necessário.
    - Liberar a memória, quando um processo terminar.
    - Tratar do problema de swapping, isto é, quando a memória é insuficiente.
- Gerenciador de E/S.
  - Estruturado em camadas.
    - Software.
      - Sistema de arquivos.
      - Device drivers.
    - Hardware.
      - Controladores.
      - Dispositivo de E/S.
- Gerenciador de comunicação interprocessos (IPC).
  - Modelos de comunicação.
    - Difusão (broadcast).
    - Produtor-consumidor (unidirecional).
    - Cliente-servidor.
    - Peer-to-Peer (P2P).
    - Caixa de correio (mailbox).
    - Diálogo.
- Gerenciador de sistemas de arquivos.
  - Elementos: arquivo e diretório.
  - Tipos de arquivo: executável, dados, multimídia.
    - Pipe: é um canal de comunicação, ou um redirecionamento de dados entre dois processos.

## Objetivos

- Eficiência
- Robustez
- Escalabilidade
- Extensibilidade
- Portabilidade
- Segurança
- Interatividade
- Usabilidade

## Arquitetura

- Monolítica
- Em camadas
  - Firmware -> Sistema Operacional -> Aplicativos
- Micronúcleo (MicroKernel): alto grau de modularidade
- SO de Redes (SOR)
  - Servidores de arquivos, bancos de dados, impressão, comunicação, gerenciamento
- Distribuído
  - Computadores ligados a uma rede e independentes entre si

## Interação hardware e software

### Nome dos arquivos

- Limite de caracteres
- O uso de caracteres especiais
- A distinção de caracteres em letra maiúscula
  - O MS-DOS não permite o uso
- Extensão
  - UNIX
    - É opcional
    - Um arquivo pode ter mais de uma extensão
    - Não vincula o conteúdo do arquivo à extensão

### Alocação de dados

- Setor 0 do disco rígido ou Master Boot Record (MBR) para o boot da máquina
  - Armazena a tabela de partição
- Tipos
  - Contígua
  - Lista encadeada
  - Lista encadeada usando uma tabela na memória
  - Inode, I-node ou Nó-i (UNIX / Linux)
    - Estrutura de dados que descreve um objeto do sistema de arquivos, como um arquivo ou diretório

### Sistema de arquivos

- FAT, 1977, Microsoft.
- EXT (Extended File System), 1992, Linux.
  - Atributos do EXT4 (atual).
    - Identificação do usuário (UID) dono do arquivo.
    - Identificação do grupo (GID) ao qual o arquivo pertence.
    - Permissões de acesso de leitura, de escrita e de execução.
      - Privilégios de root: `su <senha do superusuário>`.
      - Permissões de arquivos com o comando Chmod no modo octal:
        - Valores de 0 a 7: `chmod Setuid (root, opcional) | Proprietário | Grupo | Outros <nome do arquivo>`
        - **Permissões:**
          - 0: Sem permissão.
          - 1: Execução.
          - 2: Gravação.
          - 3: Execução e Gravação.
          - 4: Leitura.
          - 5: Leitura e Execução.
          - 6: Leitura e Gravação.
          - 7: Leitura, Execução e Gravação.
- NTFS, 1993, Microsoft
- FAT16, 1995, Microsoft
- FAT32, 1996, Microsoft

### Interpretadores e compiladores

- Linguagens de montagem (assemblers)
- FORTRAN, 1950
- Common Business Oriented Language (COBOL), 1959
- C, 1970
- C++, 1980
- Java, 1995
- C#, 2000

### Firmware e middleware

- Instruções executáveis armazenadas em memória não volátil
- Middleware
  - Permite que uma aplicação seja executada em um computador e se comunique com outra em outro computador

### Processadores

- Modos de execução: usuário, núcleo (supervisor)
- Tipos
  - Complex Instruction Set Computing (CISC), 1960
    - Exemplos: modelos 386 e 486 da Intel
  - Reduced Instruction Set Computing (RISC) e Advanced RISC Machine (ARM)
    - Exemplos: PowerPC da IBM, smartphones, tablets e no Raspberry PI
- Projeto
  - Unidade de Controle (UC): busca das instruções na memória principal
  - Unidade de Execução
    - Unidade de Lógica e Aritmética (ULA)
    - Registradores: armazenar os dados
  - Interface de barramento: interação do processador com a memória e os outros dispositivos
    - Tipos: dados, endereços e controle
- Multiprocessadores: acoplamento forte (Pentium da Intel) ou fraco (escalabilidade, mas lento)

### Memória

- Princípio da localidade: localidade, temporal, espacial, sequencial
- Hierarquia: Registradores > Caches > Memória principal > Disco magnético > Fita magnética
- Armazenamento primário
  - Principal (RAM) é volátil
  - Complementary Metal Oxide Semiconductor (CMOS): manter a data e a hora do computador atualizadas
  - ROM (Read Only Memory) onde reside o bootstrap loader
- Armazenamento secundário
  - Sólido, Disco e fita
- Tipos: real (física) e virtual (paginação e segmentação)
- Estratégias de Gerenciamento
  - Busca: determina o que vai ser transferido para a memória principal
  - Posicionamento: first fit (FF), best fit (BF), worst fit (WF)
  - Substituição: quais dados deverão ser removidos da memória principal

### Barramentos

- Dados, endereços
- Portas
  - USB
  - Interface de Pequeno Sistema de Computadores (SCSI)
  - FireWire (Apple)
- Canais E/S

### Processos

- Basicamente um programa em execução.
- Estados: execução, pronto, bloqueado.
- Transições de estado: acordado ou adormecido.
- Elementos de um processo (espaço de endereçamento).
  - Número de Identificação de Processo (Process Identification Number – PIN).
  - Bloco de Controle de Processo ou descritor de processo (Process Control Block – PCB).
- Processo Init no Linux.
  - kswapd: gerenciamento de memória.
  - khubd: operações de dispositivos.
  - xfs: operações do sistema de arquivos.
  - login: autenticação dos usuários, bash.
  - klogd: log do kernel.
- Chaveamento de contexto.
  - Interrompe a execução de um processo e começa a executar outro que estava no estado pronto.
- Interrupções.
  - Habilitam o software a responder aos sinais do hardware via sinais.
- Threads: processos concorrentes.
  - Estados.
    - Nascido.
    - Pronto.
    - Em execução, em espera, adormecido, morto.
    - Bloqueado/Deadlock.
      - Dois ou mais processos não podem continuar suas execuções.
      - cada um deles espera pelos recursos alocados entre eles.
  - Tipos: de usuário, de núcleo, híbrido.
  - Mecanismos de sincronização de processos:
    - **Semáforos:** Permitem que vários processos acessem um recurso compartilhado, mas controlam o número máximo de acessos simultâneos.
    - **Mutex (Mutual Exclusion):** Tipo de semáforo, permite que apenas um processo acesse um recurso compartilhado por vez.
    - **Monitores:** Permitem que vários processos acessem um conjunto de recursos compartilhados, mas controlam o acesso a cada recurso individualmente.
    - **Condições de Variável:** Permitem que os processos esperem que uma condição específica seja satisfeita antes de continuar a execução.
    - **Sinais (Signals):** notificar um processo sobre eventos.
    - **Filas de Mensagens (Message Queues):** Os processos trocam mensagens de forma assíncrona.
    - **Barreiras (Barriers):** Pontos de sincronização de processos.
- Algoritmos ou políticas de escalonamento.
  - Critérios para determinar a ordem de execução dos processos, dentre os que concorrem pela utilização do processador
  - Critérios de comparação:
    - Turnaround: Afere o tempo total, desde a submissão do processo até a sua conclusão.

#### Modos de endereçamento de uma instrução

- Determinam como os operandos são especificados para uma instrução de máquina.
- Permitem flexibilidade na forma como os dados são acessados, fornecendo diferentes maneiras de referenciar os operandos.

1. **Imediato**
   - O operando é especificado diretamente na instrução.
   - Exemplo: `MOV A, #5` (o valor 5 é movido para o registrador A).

2. **Direto ou Absoluto**
   - A instrução contém o endereço do operando na memória.
   - Exemplo: `MOV A, 1000H` (o valor na posição de memória 1000H é movido para o registrador A).

3. **Indireto**
   - A instrução especifica um registrador ou endereço de memória que contém o endereço completo do operando.
   - Exemplo: `MOV A, @R0` (o valor no endereço contido em R0 é movido para o registrador A).

4. **Registrador**
   - O operando está em um registrador, e a instrução especifica qual registrador.
   - Exemplo: `MOV A, B` (o valor do registrador B é movido para o registrador A).

5. **Indexado**
   - O endereço do operando é obtido somando um valor constante (deslocamento) a um registrador.
   - Exemplo: `MOV A, 1000H[R1]` (o valor no endereço 1000H mais o valor no registrador R1 é movido para o registrador A).

6. **Base**
   - Similar ao endereçamento indexado, mas usa um registrador base em vez de um índice.
   - Exemplo: `MOV A, 1000H[BX]` (o valor no endereço 1000H mais o valor no registrador BX é movido para o registrador A).

7. **Relativo**
   - O endereço do operando é determinado somando um deslocamento ao endereço da instrução atual.
   - Exemplo: usado frequentemente em instruções de salto, como `JMP +5` (salta para a instrução 5 posições à frente da instrução atual).

8. **Implícito**
   - O operando é implícito na própria instrução e não precisa ser especificado.
   - Exemplo: `CLR` (limpa o registrador A, onde A é o operando implícito).

9. **por Pilha**
   - Os operandos são empilhados e desempilhados da pilha.
   - Exemplo: `PUSH A` (empilha o valor do registrador A) e `POP B` (desempilha o valor para o registrador B).

## Segurança

### Criptografia

- Conceito.
  - Codificação e decodificação de dados, interpretados apenas pelos receptores.
  - Cifra: sistema criptográfico, um algoritmo para a criptografia das mensagens.
    - Ex. cifra de César: transposição, na qual a ordem das letras é alterada.
  - Cadeias binárias com uma chave de tamanho determinado, 64 bits.
- Chave secreta ou criptografia simétrica.
- Processo:
  - Emissor > Texto comum > Criptografa > Texto cifrado > Meio de comunicação (como internet) > Mesma chave simétrica secreta > Texto comum > Receptor.
- Central de distribuição de chaves (Key Distribution Center – KDC).
- Autoridade certificadora (AC): valida os certificados.
- Tipos:
  - Rivest-Shamir-Adleman (RSA), 1970.
  - Privacidade Razoável (Pretty Good Privacy – PGP), 1991.
- Assinaturas digitais de documentos.
  - Message Digest 5 – (MD5), gera um hash de 16 bytes.
  - Secure Hash Algorithm – (SHA-1), gera um hash de 20 bytes.

### Autenticação

- Meios
  - Senha, Biometria, smart cards (armazena chaves privadas, certificados digitais, etc.)
- Ataques
  - Internos
    - Bombas lógicas: código que executa ação danosa se não entrar com uma senha diariamente
    - Alçapões (trap door): códigos inseridos por um programador para evitar uma verificação
    - Logro na autenticação do usuário: falso login para coletar dados dos usuários
  - Externos
    - Vírus de setor de boot, transiente, residente
    - Worm: se propaga em uma rede infectando outros arquivos, independe de ação do usuário
    - Cavalo de Troia (Trojan Horse)
    - Backdoor
    - Denial-of-Service – DoS
    - Ataque de sistema de nome de domínio (Domain Name System – DNS)
- Remédios
  - Sistemas de assinatura única
    - Scripts de acesso de estações de trabalho
    - Scripts de servidor de autenticação
    - Autenticação por ficha (token)
  - Antivírus, Firewall
  - Sistema de detecção de intrusos

### Controle de acesso

- Princípio do mínimo privilégio
- Matriz ou listas de controle de acesso
- Requisitos: Privacidade, Integridade, Autenticação, Autorização, Não rejeição

### Protocolos

- Secure Sockets Layer – SSL
- Transport Layer Security – TLS
- Internet Protocol Security – IPSec
- Wi-Fi Protected Access – WPA
