Network significa uma rede, conjunto de computadores conectados que transferem dados entre si.
## The Local Area Network (LAN)
- Lugar geográfico restrito, como casas.
- Não se pode colocar mais de 30 worktations na mesma LAN 
- Possui limite de distância entre os computadores
- Workgorups são grupos divididos de uma LAN a fim de facilitar a administração
- Para um workgroup falar com outro é necessário conecta-los fisicamente, para isso pode ser usado o router
## Common Network Components
- Workstations
- Servers
- Hosts
#### Workstations
- Computadores potentes
- Ficam no client side porém não significa o mesmo que host
#### Servers
- Usado para prover recursos para o cliente
- Tem hardware mais caros 
- Precisam estar em um ambiente controlado e seguro
- Existem serves que fazem tarefas específicas:
	- File server: Armazena e retorna arquivos
	- Mail server: Serviços de email
	- Print server: Gerencial todas as impressoras na rede
	- Web server: Gerencia páginas web (HTTP)
	- Application server: Gerencia aplicações de rede
	- Remote-access server: Fornece acesso remoto de usuários através de modem, IP ou sem fio
	- Proxy server: Lida com tarefas no lugar de outras máquinas na rede
#### Hosts
- Host é qualquer tipo de dispositivo que contém um IP na rede dentro do escopo TCP/IP
- O termo host surgiu na época dos mainframe (que eram os hosts da época)
## Virtual LANs (VLANs)
- É o mesmo que os workgroups
- Diferente das LANs, que é construída fisicamente, as VLANs são construídas logicamente
- Se você estiver fisicamente no departamento 1 porém na rede da VLAN 2, é como se você estivesse fisicamente no departamento 2, assim substituindo o roteador
- VLAN membership é um grupo de hosts, pois cada host é um membro de uma VLAN
- As VLANs são conectadas por um switch
## Wide Area Network (WAN)
- Precisam de portas
- Cobre uma área grande
- Normalmente lenta
- Podem fornecer transporte público ou privado de dados
- Usam endereços lógicos (IP) para se comunicar com hosts de LANs diferentes
- Os roteadores são responsáveis por ligar as LANs a WAN
- WANs conectam duas ou mais LANs remotamente usando seu ISP (Internet Service provider) - que é o seu provedor de internet
## Virtual Private Networks (VPNs)
- Fica entre a WAN e a LAN
- Funciona como um link entre LANs porém estabelece segurança
- Basicamente faz o seu host como se estivesse fisicamente na outra ponta da VPN, pertencendo a outra LAN
## Network Architecture: Peer-to-Peer or Client/Server?
- Existem duas principais tipos de rede, peer-to-peer e client/server
#### Peer-to-Peer Networks
- Não existe um server principal
- Todos os computadores podem ser clientes e servers
- Usado quando não é necessário implementar segurança e quando o número de usuários é baixo
- Difícil de administrar
#### Client/Server Networks
- Possui um server principal onde todos os computadores acessam
- Rede mais organizada
## Physical Network Topologies
- Topologias de rede física significa como o mapa da rede é feita, como os dispositivos são organizados fisicamente na rede
- Topologia vem de top, imagine uma rede vista de cima
- Existe diferentes tipos de topologia:
	- Bus
	- Star
	- Ring
	- Mesh
	- Point-to-point
	- Point-to-multipoint
	- Hybrid
#### Bus Topology
- Todos os dispositivos estão conectados no mesmo cabo
- Fácil de instalar e barato
- Difícil de resolver erro
- Fault tolerance baixa
![[Pasted image 20240216113225.png]]
#### Star Topology
- Todos os dispositivos estão conectados ao um Hub central com cabos próprios
- Fácil de resolver falhas
- Se um cabo falhar não vai influenciar a rede por inteira como na topologia bus
- Mais caro
- São configurados com conexões point-to-point
 ![[Pasted image 20240216113208.png]]
#### Ring Topology
- Parecido com a topologia bus
- Todos os dispositivos estão conectados a dois dispositivos, o anterior e o posterior
- Formato de círculo
- Não é mais utilizados em LANs porém é usado em algumas WANs
![[Pasted image 20240216113153.png]]
#### Mesh Topology
- Maior quantidade de cabos de todas as topologias pois todos os dispositivos se conectam com todos igual na topologia bus porém ao invés de usar um cabo utiliza-se vários 
- Se em uma sala contém 10 computadores, são 45 cabos para conecta-los (n(n-1)/2)
- Complicado de gerenciar
- Não é mais utilizada em LANs
- Fault tolerance alta
- No partial mesh, não são todos os dispositivos que serão conectados um com o outro, diferente do full mesh
![[Pasted image 20240216113141.png]]
#### Point-to-Point Topology
- Apenas um caminho de comunicação entre dois dispositivos
- Não é escalável 
- Mais utilizado para fazer o link das WANs
![[Pasted image 20240216113118.png]]
#### Point-to-Multipoint Topology
- Um ponto de acesso que transmite dados para vários dispositivos
- Pode ser via wifi ou cabo
![[Pasted image 20240216113555.png]]

#### Hybrid Topology
- Combinação de dois ou mais tipos de topologias físicas ou lógicas na mesma rede
- Na imagem é um hub na topologia estrela que conecta com os computadores na topologia bus
![[Pasted image 20240216113828.png]]
## Topology Selection, Backbones and Segments
#### Selecting the Rigth Topology
- Qual o orçamento?
- Qual a fault tolerance que precisa?
- Precisa ser configurada rapidamente?
- O quão escalável precisa ser?
#### The Network Backbones and Segments
A rede é dividida em seguimentos e backbones, os backbones é a estrutura da rede que junta todos os seguimentos
![[Pasted image 20240216134046.png]]


