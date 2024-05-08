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
- Overhead são dados adicionais enviados juntos aos dados normais
![[Pasted image 20240216154611.png]]
- Enquanto os dois hosts estão transferindo dados, periodicamente é feita uma checagem para saber se a comunicação está correndo bem
#### Flow Control
- Controle de fluxo que garante que os dados do emissor não sobrecarreguem o receptor
- Em casos de overflow(quando entra mais dados do que a rede pode processar) o dado não é perdido e sim armazenado no buffer, porém quando o buffer fica cheio, os novos dados que estão chegando são jogados fora
- Existem duas principais técnicas de flow control:
	- Windowing: Os intervalos das comunicações são aproveitados enviando pequenas quantidades de seguimentos, ambos os lados decidem o tamanho da jenela(número de bytes) e os dados são enviados preenchendo esse tamanho
	- Acknowledgments(Reconhecimentos): Quando o emissor envia seguimentos para o receptor, existe os ACKs(Acknowledgments), que é responsável por retornar informações ao emissor se o seguimento chegou com sucesso, é como se fosse um feedback, dependendo da resposta do ACK, o emissor pode mudar o tamanho da janela, taxa de transmissão etc
## Network Layer
- Responsável por gerenciar o endereçamento físico e lógico e determinar o melhor caminho para movimentar os dados através da rede, responsável pelo tráfego
- Roteadores fazem parte dessa camada
- Quando os pacotes chegam no roteador ele verifica o IP de destino desses pacotes e envia-o para o destinatário, caso não tenha o destinatário o pacote é dropado(perdido)
- Existem dois tipos de pacotes na camada de redes:
	- Data packets: Dados do usuário
	- Rout-update packets: Atualiza roteadores vizinhos sobre as redes e rotas
- Network address: O roteador guarda uma tabela contendo os endereços de rede, IP e IPv6 por exemplo
- Interface: Interface de saída que um pacote utilizará quando for destinado a uma rede específica
- Metric: Distância da rede remota
- Roteadores quebram domínios de broadcast e switches quebram colisões de domínios
## Data Link Layer (Camada de enlace)
- Garante que os pacotes chegaram no host através do endereçamento físico
- Responsável pela identificação do host na rede
- Sub-camadas da camada de enlace
	- Media Access Control (MAC): Endereço físico do host
	- Logical Link Control (LLC): Fornecer serviços de controle de erro e controlar o acesso para as camadas superiores, essa camada fica em cima da camada MAC
## Physical Layer
- Envia e recebe bits
- Lida com tudo o que é físico, cabos por exemplo
- Converte sinais elétricos em bits
## Encapsulamento
Basicamente as camadas quando enviam dados para a próxima camada encapsulam os pacotes e quando a próxima camada recebe esse pacote encapsulado, ela desmembra esse pacote e quando vai enviar os dados para outra camada faz o mesmo procedimento
