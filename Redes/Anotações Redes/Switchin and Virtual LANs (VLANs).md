## Switching Services
- Diferente das bridges que usam um software para gerenciar as tabelas, os switches usam o ASICs(application-specific integrated circuits)
- São mais rápidos que roteadores
- Baseado em bridge, pode ser considerado um bridge multiportas
- Baixo custo e baixa latência
- Os switches são mais rápidos porque ele lê apenas o frame encapsulado no pacote
## Bridging vs. LAN Switching
- Bridge é baseado em software e switch em hardware porque usa chips ASIC para ajudar a filtrar as decisões
- Switch é uma bridge multiporta
- Ambos leêm endereço MAC examinando o endereço de origem de cada frame recebido
## Three Switch Functions at Layer 2
- Aprendizado de enderaçamento
- Filtros 
- Evitar ter loop
## Address Learning
- Todos os frames que passam pelo switch, ele pega o endereço MAC da origem desses frames e armazena-os em uma base de dados chamada filter table ou foward table
- Quando o switch acaba de ser ligado, essa tabela inicialmente vem vazia
- Quando ele recebe um frame e precisa enviar para um host, ele não tem ideia de quem é o MAC de destino, portanto ele envia para todas as portas, a que responder é o MAC respectivo desse frame
## Filter Decisions
- Caso o destination MAC de um frame estiver na base de dados do siwtch, ele envia apenas para a porta(interface) correspondente, isso é chamado de frame filtering
- Caso contrário, o switch irá mandar para todas as interafaces, exceto a interface de origem
## Loop Avoidance
- Broadcast storm é quando os switches mandam sem parar broadcastas para toda a rede, isso acontece quando frames são enviados em links redundantes ao mesmo tempo
- Thrashing é quando há tanto congestionamento, que os switches se preocupam mais em atualizar suas tabelas do que enviar os frames, assim os frames não são envidos
## Spanning Tree Protocol (STP)
- STP usa o spanning-tree algorithm(STA), que primeiro monta toda a topologia da rede em uma base de dados e então evita que existam links redundantes
- Servem para evitar loop
- Bridge Protocol Data Units (BPDU), é um protocolo que é transmitido dentro do switch para todas as portas, assim todos os links entre os switches podem ser achados
## Spanning-Tree Port States
- As portas de uma bridge ou de um switch que rodam o STP possuem 5 estados
	- Blocking: A porta não deixa passar nenhum frame, todas as portas são blocking por padrão quando o switch é ligado
	- Listening: Fica escutando os frames que passam mas não popula a tabela de MAC, ela faz isso para ter certeza que nenhum loop está ocorrendo na rede
	- Learning: Todos os frames que passam ela popula em sua tabela MAC porem não encaminha os frames adiante
	- Forwarding: Recebe e envia todos os frames
	- Disabled: nonoperational, com se ela não existisse
- Switches populam a tabela MAC somente no estado learning e forwarding
- Assim que um switche determina o melhor caminho para a bridge root, todas as outras portas redundantes são determinadas como blocking
## STP Convergence
- É quando todas as portas dos switches e bridges ficam no modo forwarding ou blocking, quando isso acontece nenhum frame é passado pelas portas até que esse evento de convergencia acabe
- Para a convergencia acabar, todos os hosts devem parar de enviar frames para os switches
- Leva 50 segundos para ir do modo blocking para o modo forwarding
## Virtual LANs (VLANs)
- Switches quebram collision domains em vários e roteadores quebram collision broadcast (sub-redes)
- Para fazer com que os switches quebrem collision broadcast também é necessário criar VLANs
- Agrupar logicamente uma rede
## VLAN Basics
- Todos os devices são do VLAN 1, a Cisco não recomenda mudar o nome da VLAN 1, pois é usado para propósitos administrativos
- Para ter uma inter-VLAN (comunicação entre as VLANs) é necessário um roteador
- VLAN é configurada manualmente nos switches, basicamente é colocado o nome da VLAN e a sub rede que ela pertence
## Dynamic VLANs
- Quando um host muda a porta do switche, é possível ele ser direcionado para a VLAN que ele pertencia, pois existe softwares que contém uma tabela com os MAC respectivos
## Indentifying VLANs
- Trunk port é uma porta que se comunica com outros switches de VLANs diferentes, ou seja, nessa porta passa informações de várias VLANs
- Access port só passa informação de uma única VLAN, o contrário da trunk port
- As trunk ports podem ser configuradas manualmente ou automaticamente (dynamic trunking protocol (DTP))
## VLAN Identification Methods
#### Inter-Switch Link (ISL)
- É um jeito de colocar uma tag da VLAN em um frame, para identificar qual VLAN esse frame pertence
- ISL funciona na camada 2
- Encapsula o frame com um novo header contendo a tag
- Funciona só nos switches da Cisco
#### IEEE 802.1Q
- Método padrão de colocar tag em um frame criado pela IEEE
- Coloca um espaço no frame para identificar a VLAN
- É usado um ID para cada VLAN
## Switching and Network Security
#### Port Security/Authentication
- Um método é configurar o switch para aceitar os MACs pré definido, caso um MAC que não está na lista for plugado em alguma porta, vai dar access denied
- Porém em casos de muitos switches essa técnica não é tão boa, então é usado um authentication server 802.1x
#### How VLANs Enhance Network Security
- Como ela cria vários broadcast domains então é possível ter um crontrole maoior dos hosts que estão na respectiva VLAN
#### Two Additional Advanced Features of Switches
- Power over Etheret (PoE)
- Port Mirroring/Spanning
## Power over Ethernet (PoE)
- Sistema que transmite eletricidade junto com dados através de par trançado, assim não precisa de cabos separados um para energia e outro só para dados
- Serve para transmitir VoIP, wireless LAN access point, network cameras etc
- Padrão PoE é o 802.3af
- Está presente em alguns switches
## Port Mirroring/Spanning
- Também chamado de Switch Port Analyzer (SPAN)
- Permita sniffar o tráfego na rede
- É uma porta especifica para sniffing
- Cuidado quando for usar essa porta pois pode quebrar a rede


