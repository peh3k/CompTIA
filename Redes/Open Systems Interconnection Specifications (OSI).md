## Internetworking Models
- Antigamente somente havia comunicação de entre computadores do mesmo fabricante
- A ISO criou o modelo OSI para quebrar essa limitação
- Modelo OSI possui 7 camadas
- Foi o primeiro modelo a ser criado
## The Layered Approach
- Conceito de como a comunicação entre dispositivos funciona dividida em camadas
- O termo binding é usado para falar que cada layer(camada) tem sua própria função
## Advantages of Reference Models
- Como o modelo OSI divide a rede em pequenas peças, fica mais fácil de encontrar problemas e fazer manutenções
- Permite que vários fabricantes utilizem o modelo a fim de padronizar
- Previne que uma camada interfira negativamente na outra
## The OSI Reference Model
- Uma das funcionalidades boas do modelo OSI ajudar na transferência de dados entre hosts (MAc, Linux, Windows etc)
- O modelo OSI não é um modelo físico e sim um conceito
- Modelo OSI possui 7 camadas
	![[Pasted image 20240216143620.png]]
- As camadas são divididas em dois grupos
	1. Aplicação que se comunica com o usuário
	2. Como os dados são transferidos end-to-end
## Application Layer
- Interface e protocolos para o usuário (HTTP)
- Fornece serviços de rede aos aplicativos e usuários finais
## Presentation Layer
- Apresenta os dados para a camada de aplicação
- Compressão de dados e criptografia entram nessa camada
- Converte dados
## Session Layer
- Gerencia sessões de comunicação
- Inicia e encerra sessões, sessão é um período de comunicação entre dois dispositivos
- Garante que ambas as pontas estão sincronizadas
- Garante que os dados são enviados e recebidos na ordem certa
## Transport Layer
- Reúne dados em stream de dados
- Estabelece conexão lógica entre o host que está enviando e o que está recebendo
- Fornece transporte end-to-end
#### Connection-Oriented Communication
- Antes do host que envia os dados comece a envia-los, primeiro ele estabelece uma conexão entre o recebedor, o nome disso é virtual circuit, esse tipo de conexão é chamada de connection-oriented
- handshake éo termo usado para quando a connection-oriented é estabelecida (aperto de mãos)
- Quando o handshake é feito, ambos os lados estão prontos para começarem a transferir dados, isso se chama overhead
![[Pasted image 20240216154611.png]]
- Enquanto os dois hosts estão transferindo dados, periodicamente é feita uma checagem para saber se a comunicação está correndo bem