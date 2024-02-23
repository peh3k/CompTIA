## Common Network Connectivity Devices
#### Hub
- Dispositivo que conecta todos os seguimentos da rede juntos na topologia estrela
- Quando ocorre uma transmissão em um das portas, a transmissão é escutada por todas as outras portas
- Costumar ocorrer muitas colisões, por esse motivo não é mais utilizado em empresas
#### Repeater Ethernet
- Repetidor de ethernet possibilita transferência de dados a distância maiores
- Possui muita latência 
- Não é mais usado pois existem opções melhores
#### Modem
- Modulador e demodulador de sinais (MOdulator/DEModulator)
- Converte sinais digitais dos computadores em sinais analógicos(sinais elétricos) e vice-versa
- Quando se ouve o termo modem as primeiras coisas que devemos ter em mente são:
	- Tradicional(POTS)
	- DSL
	- Cable
###### Traditional (POTS)
- Esses modems estão conectados aos computadores, e convertem os sinais desses computadores a fim de transportar esses sinais através de linhas de telefones antigas (POTS)
- Alguns fabricantes colocam o modem diretamente na mobo do computador
###### DSL (Digital Subscriber Line)
- Substituiu os modems tradicionais (POTS) pois possui uma maior taxa de transferência (cerca de 3200Hz)
- É necessário ter uma NIC no computador para conseguir conectar o DSL
![[Pasted image 20240221095056.png]]

###### Network Interface Card (NIC)
- Vem junto com a placa mãe porém tem casos que não
- Pode ser on-board e off-board
- Adaptador de rede
![[Pasted image 20240221102746.png]]
###### Transceiver (Media Converter)
- Conecta varios tipo de cabos, por exemplo se eu tenho um cabo ethernet 100Base-TX e quero converter para fibra óptica eu conecto a entrada o cabo ethernet e no outro a fibra óptica
- Basicamente ele converte sinais
![[Pasted image 20240221103340.png]]
###### Bridge
- Dispositivo de rede que conecta os seguimentos de duas redes similares
- A função é dividir a rede para evitar colisões
![[Pasted image 20240221104021.png]]
###### Switch
- Conecta vários seguimentos da rede juntos como os hubs porém diferente do hub que é burro, o switch é capaz de distinguir endereços MAC, enviando somente para o MAC específico, o hub envia para todos
- Caso o switch não encontre a porta do MAC de destino, ele enviará os frames para todas as portas
- Está na camada de enlace
###### Wireless Access Point(AP)
- Permite usuários se conectarem á rede através de radio frequência
- Pode usar cabeamento ethernet também
###### Router
- Conecta várias redes
- Decide a rota na qual os pacotes irão passar, define o menor caminho
###### Firewall
- Segurança da rede
- Protege a sua LAN 
- Possui dois lados, o lado público e o privado, a pública está voltado á internet e a privada a rede
- Podem ter firewall entre servidores dentro de uma rede 
###### Dynamic Host Configuration Protocol (DHCP) Server
- Servers DHCP atribuem os endereços IP dinamicamente aos hosts na rede
1. Quando um host entra na rede ele envia um pacote em broadcast para descobrir servidores DHCP na rede, esse pacote se chama DHCPDISCOVER
2. Quando o servidor DHCP recebe esse pacote ele oferece a esse host um IP que não está sendo usado na rede, assim como a máscara, gateway padrão, servidor DNS etc, o servidor DHCP oferece tudo isso em forma de pacotes DHCPOFFER
3. Assim que o host recebe o DHCPOFFER ele retorna com um DHCPREQUEST para confirmar a oferta
4. Após a confirmação, o DHCP envia um pacote DHCPPACK, que contém o endereço IP, DNS etc que é oficialmente atribuído a esse host
5. Quando o host desconecta da rede ele envia um pacote chamado DHCPRELEASE, indicando que ele sairá da rede, assim o servidor DHCP libera esse IP
## Other Specialized Devices
- Multilayer switch 
- Content switch  
- Intrusion Detection or Prevention System (IDS/IPS) 
- Load balancer  
- Multifunction network devices  
- DNS server  
- Bandwidth shaper  
- Proxy server 
- Channel Service Unit/Data Service Unit (CSU/DSU)
#### Multilayer Switch
- Conhecido como MLS é um dispositivo que atua tanto na camada de enlace, lidando com endereçamento MAC quanto na camada de redes fazendo o papel do router
- Diferente do router, o MLS pode encaminhar tráfego via IP
#### Content Switch
- Onde em dia existem switchs capazes de agir em varias camadas do modelo OSI:
	- Layer 4-7 switches
	- Content switches
	- Content service switches
	- Web switches
	- Application switches
- Usado como load balance quando tem muitos servers
#### Intrusion Detection or Prevention System (IDS/IPS)
- Ferramenta de segurança contra exploits
- IDS detecta vírus ou ataque
- IPS combate o vírus ou ataque fechando certos tipos de portas ou destruindo pacotes suspeitos na rede
- Monitoramento da rede em tempo real
#### Load Balancer
- Enquanto um rotador encaminha os pacotes para o IP de destino específico, o load balancer pode encaminhar pacotes para destinos dentro de um IP
- É possível aplicar regras como fault tolerance e redundância
- É um gerenciador
#### Multifunction Network Devices
- Qualquer dispositivo que possui multifunções na rede ex: impressora pois ela é capaz de imprimir, fazer cópia, scanning etc
#### Domain name Service (DNS) Server
- Converte IP em domínio, chama-se name resolution
- O DNS é parecido com o Microsoft's Windows Internet naming Service (WINS), a diferença é que o WINS não armazena IPs e seus respectivos domínios e sim realiza um broadcast para todos da rede para achar o domínio
- .com: organizações comerciais (empresas)
- .edu: estabelecimento de educação
- .gov: domínio do governo
- .int: organização internacional
- .mil: domínio militar
- .net: organização de internet
- .org: organizações sem fim lucrativo
- Nomes dos IPs, no caso IPv6 são salvos como quad-A, ou AAAA já os nomes dos domínios são salvos como pointer recorder(PTR)
- DNS possui mail exchanger (MX), o MX é responsável por identificar servidores de emails
- DNS possui o canonical name (CNAME), é como o segundo nome dos hosts, por exemplo o www.google.com, o www é o canonical name do google (que é o host)
#### Bandwidth Shaper
- Ferramenta para otimizar a performance da rede
- Controle o tráfego da rede e causa dalays em certos pacotes a fim de diminuir o tempo de resposta
- Muito caro
![[Pasted image 20240222205444.png]]
#### Proxy Server
- Tipo de servidor que lida com solicitações de cliente, proxy server encaminha a requisição do cliente para o servidor de destino e depois devolve a resposta para o cliente
- Fica entre o cliente e o servidor de destino
- É possível aplicar regras nele
- Existem dois tipos de servidores proxy:
	- Caching proxy server: Armazena requisições feitas por um cliente anteriormente, logo da próxima vez que o cliente fazer outra requisição igual, o tempo de resposta será menor
	- Web proxy server: Cria um web cache com os dados de sites que o cliente já visitou, por exemplo quando ja entramos em um site e quando vamos entrar de novo e fazer o cadastro, os campos do cadastros já vem preenchidos
#### Channel Service Unit/Data Service Unit (CSU/DSU)
- Serve para conectar um dispositivo a uma linha de comunicação digital como T1 ou T3
- A CSU é responsável por verificar a integridade dos sinais na linha de comunicação
- DSU é responsável por converter os dados do dispositivo para sinais na linha de comunicação
## Network Segmentation
- Lista de coisas que mais causa congestão do tráfego na LAN:
	- Vários host em um domínio de broadcast
	- Broadcast storms(grande número de pacotes para broadcast ao mesmo tempo)
	- Multicasting (quando um host envia pacotes para um grupo de hosts)
	- Baixa largura de banda
	- Hubs
- A resposta para acabar com a lentidão e uma rede é quebrar ela em várias redes menores, isso se chama network segmentation
- A segmentação da rede é feita por switches e routers pois eles quebram broadcasts domains  e colision domains
- Vantagens de usar routers na rede:
	- Não fazem broadcast por padrão
	- Pode filtrar as informações da camada de rede, como por exemplo os IPs
- Principais funções do roteador:
	- Troca de pacotes
	- Filtragem de pacotes
	- Conexão com a WAN
	- Seleção de rotas
- Routers são switches
- Cada porta de um switch é um colision domain porém os switches tem somente um broadcast domain enquanto o router possui vários broadcast domain
- Switch usa tecnologia bridge para separar esses colision domains






