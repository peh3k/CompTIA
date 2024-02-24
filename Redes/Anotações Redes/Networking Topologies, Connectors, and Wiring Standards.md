## Physical Media
- Todas as redes tem uma parte que usa cabeamento
	- Coaxial
	- Twisted pair (par trançado)
	- Fiber optic
#### Coaxial Cable
- Possui um condutor de cobre central envolvido com uma capa de plástico(PVC) e u escudo trançado sobre a capa
- Possui pouca perda de sinais
- Cabos usados para sinais em TV a cabo
- Pouco utilizado em redes de computadores
![[Pasted image 20240217210109.png]]
Conectores BNC:
![[Pasted image 20240217210118.png]]
- RG-58 U
- RG-58 A/U
- RG-8
- RG-59
- RG-6
- RG-62
#### Twisted-Pair Cable
- Múltiplos fios trançados em pares
- As vezes tem um escudo de metal em volta dos fios - shielded twisted pair(STP)
- Cabos sem o shield são os UTP (unshield twisted-pair)
#### Ethernet Cable Descriptions
- Os tipos de cabos ethernet são descritos como N<sinalização>-X
	- O N é a velocidade em Mbps
	- A sinalização pode ser baseband ou broadband
	- o X é uma identificação única
	- 100Base-X é um cabo de 100 Mbps do tipo baseband
- Os cabos são trançados em pares para evitar um evento chamado crosstalk quando há interferência de sinal caso eles não estejam em pares
- É mais barato que outros cabos
- É fácil trabalhar com ele
- Permite uma transmissão de dados boa
- Os cabos UTP são divididos em categorias:
	- Categoria 1: Dois pares de fios, usado em telefonia nos anos 80 e limitado a sinais de 1MHz de frequência
	- Categoria 2: Quatro pares de fios, 4Mbps de transferência e frequência de 10MHz, hoje em dia é obsoleta
	- Categoria 3: Quatro pares de fios, 10Mbps e 16Mhz de limite, também é obsoleto hoje m dia
	- Categoria 4: Quatro pares de fios limitado a 20 MHz também obsoleto
	- Categoria 5: Quatro pares de fios limitado a 100 MHz
	- Categoria 5e (Cat 5 melhorado): Quatro pares de fios limitado a 100 MHz porém capaz de lidar com turbulências nos quatro pares ao mesmo tempo
	- Categoria 6: Quatro pares de fios limitado a 250 MHz, é o padrão de fios UTP
	![[Pasted image 20240217213251.png]]
#### Connecting UTP
- Os conectores BNC usados em cabos coaxiais não encaixam nos cabos UTP, para isso é necessário um conector Registered Jack (RJ), mais especificamente o RJ-11 para telefones que usa dois pares de fios e o RJ-45 usa quatro pares de fios para conectar redes de computadores
- A esquerda conector RJ-11 e a direita RJ-45
![[Pasted image 20240217213731.png]]
#### Fiber-Optic Cable
- Transmite os sinais através de pulsos de luz
- Imune ao EMI (interferência eletromagnética) e RFI (interferência de radiofrequência) 
- O condutor pode ser vidro ou plástico, o de vidro permite distâncias maiores porém é mais caros que os de plásticos
- Pode ser do tipo SMF(single-mode fiber) ou MMF(multimode fiber), a diferença é o número de raios de luz (número de sinais) que podem carregar
- SMF usado em longas distâncias
- MMF usado em curtas distâncias
#### Fiber-Optic Connectors
- Os mais comuns são os ST (straight tip) e SC(square)
- O mais utilizado são os ST que usa o mesmo mecanismo dos BNC
Tipo ST:
![[Pasted image 20240217221641.png]]
Tipo SC:
![[Pasted image 20240217221655.png]]
#### Small Form Factor Fiber-Optic Connectors (SSF)
- Permite mais terminais de fibra óptica no mesmo espaço da fibra óptica padrão
- Os dois tipos de SSF mais populares são os MT-RJ(mechanical transfer registered jack) e o LC (Local connector)
- Os LC vieram depois dos MT-RJ e são usados para transferência de dados de gigabits
![[Pasted image 20240217222200.png]]
![[Pasted image 20240217222206.png]]
## Serial Cables
- Serial significa que um bit é transferido por vez
#### RS-232(Recommended Standard 232)
- Usado para transferir serial de dados
- Foram substituídos pelos USB
![[Pasted image 20240217222454.png]]
#### Universal Serial Bus (USB)
- É mais flexível pois consegue conectar até 127 dispositivos externos
- Hubs podem disponibilizar muitas conexões USB
## Properties of Cables
#### Transmission Speeds
Diferentes tipos de cabos permitem velocidade de transferência de dados diferentes, menores e maiores, cabos podem ter velocidades superiores a 10Gbps, a velocidade do cabo define a velocidade da rede
#### Distance
Dependendo do cabo e a distância que os dados deverão percorrer pode haver perdas de pacotes ou interferência, tipos de cabos trançados permitem no máximo uma distância de 100 metros
#### Duplex
- Todas as comunicações são half-duplex ou full-duplex
- A diferença é que os dispositivos podem falar e escutar ao mesmo tempo (full-duplex)
- Half-duplex os dispositivos podem somente enviar informação ou receber por vez
#### Noise Immunity (Security, EMI)
- Quando passam os bits através dos fios (1 e 0), já que gera uma corrente elétrica é possível ler a mensagem que está passando por esse fio sem precisar corta-lo, essa técnica é chamada de tapping ou grampo
- Fibras ópticas são mais difíceis de grampear
- Por isso é importante que os cabos fiquem em locais seguros
#### Frequency
Cada capo tem uma frequência específica, por exemplo Cat 5e  tem 100MHz e o Cat 6 tem 250MHz
- Os sinais são medidos em bandwidth (largura de banda) que é o mesmo que a frequência da mesma
## Wiring Standards
- Cabos ethernet é importante saber principalmente para trabalhar com redes LAN
- Alguns tipos desse cabo:
	- Straight-through cable (586A)
	- Crossover cable (586B)
	- Rolled cable (rollover)
	- Hardware loopback
#### 586A vs. 586B
- As posições dos pares são diferentes na saída do cabo
- Ambos possuem quatro pares de fio trançado
#### Straight-Through Cable
- Usado para conectar um host ou roteador em um switch ou hub
- Usado quatro fios
![[Pasted image 20240218124100.png]]
#### Crossover Cable
- Cabo UTP
- Usado quatro fios
- Pode conectar:
	- Switch to switch
	- Hub to hub
	- Host to host
	- Hub to switch
	- Router to host
	![[Pasted image 20240218124332.png]]
	
#### Rollover Cable
- Usado para conectar um host a um roteador
- Usado oito fios
![[Pasted image 20240218124650.png]]
- Esse é um cabo simples de fazer pois basta pegar os fios e inverete-los
#### Hardware Loopback
- Não é considerado bem um tipo padrão de cabo pois ele só redireciona os dados
- É usado para testar as funcionalidades das portas de comunicação
- Bastante usado para saber se um NIC está funcionando
## Installing Wiring Distributions
#### Vertical and Horizontal Cross-Connects
- Um cross-connect é um lugar central onde estão todos os cabos juntos
- Horizontal cross-connect são os cabos que saem do centro de comunicação até as tomadas pois normalmente são usados no mesmo andar
- Vertical cross-connect são usados para conectar salas diferentes por exemplo

#### Patch Panels
- É um rack que conecta os cabos
- Usado para melhor administração dos cabos
![[Pasted image 20240218131804.png]]
#### 66 Block
- É um tipo de patch panel
- Hoje em dia é mais usado e instalações telefônicas
![[Pasted image 20240218131924.png]]
#### MDF/IDF
- Main distribution frame
- Centro de distribuição de cabos
- Geralmente junta os sinais de telecomunicações
#### 25 Pair
- Constituído de 25 pares de fios
- Usado em cabos de telefonia
- Usado como cabo de alimentação
#### 100 Pair
- Usados para instalações telefônicas robustas
- 100 parede de fios
#### 110 Block
- Desde 25 até 500 pares de fios
#### Smart Jack
- Também chamado de network interface device (NID)
- Interface usada entre o provedor de serviço e a rede interna


