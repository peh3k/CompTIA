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
