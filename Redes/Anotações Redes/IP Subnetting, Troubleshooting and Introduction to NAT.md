## Subnetting Basics
- Dividir uma rede grande em menores
- Fácil gerenciamento
- Menos congestionamento de tráfego
## How to Create Subnets
- Para definir subredes, é necessário reservar IP de hosts, ou seja, quanto mais subredes, menos hosts tem
- Definir ID da rede
	- Um ID para cada subnet 
- Determinar quantos hosts cada subnet deve ter
- Criar máscara de subnet
- ID único de subnet para cada segmento físico
- O range de hosts para cada subnet
## Subnetting Class C Addresses
Caso eu queira aplicar uma máscara de subnet 25, ou seja, 25 bits ativos, 11111111.11111111.11111111.10000000, na rede 192.168.10.0
- A subnet é definida pela quantidade de bits ativios no octeto de hosts, nesse caso 1 bit está ativo, então a partir dessa rede usando essa máscara de subnet, é possível ter 2 subnets, pois 2^1 = 2, e sobrou 7 bits para hosts
- Esses 7 bits que sobraram indica a quantidade de hosts em cada subnet, nesse caso são 128 hosts, como 2 são reservados para gateway e broadcast, então no total fica 126 hosts usáveis
- Para achar onde começa e onde termina uma subnet, devemos subtrair 256 do número da máscara em decimal, nesse caso como o último octeto da máscara é 10000000, isso é igual a 128, portanto 256 - 128 = 128, logo a rede está dividida em 2 partes contendo 128 em cada
- Logo a primeira subnet começa em 192.168.10.0, e a segunda começa em 192.168.10.128
- Esse espaço entre 0 e 128 é para os hosts, gateway e broadcast
- Na primeira subnet, o IP 192.168.10.0 é do gateway e o 192.168.10.127 é do broadcast, do 1 até o 126 é destinado aos hosts
- O mesmo para a segunda subnet, o 128 é para o gateway e o 255 é para broadcast, do 129 até o 254 é destinado aos hosts
## Troubleshooting IP Addressing
- Antes de tudo pingar o seu host local, 127.0.0.1
	- Caso falhar será necessário reinstalar o TCP/IP no host
- Pingar o IP do localhost 
	- Caso falhar está com problema no NIC
- Pingar o gateway padrão
	- Se falhar quer dizer que você tem um erro físico na LAN
- Se voce pingar um servidor pelo IP, porém não achar ele na internet tem um problema de DNS
## Determining IP Address Problems
- Verificar se todos os dispositivos na rede atendem aos requisitos de gateway padrão correto, máscara correta e subnet correta
## Introduction to Network Address Translation (NAT)
- Consegue fazer merge de duas intranet com o mesmo IP
- Possui delay
- Diminui a rastreabilidade end-to-end
- Algumas aplicações não funcionam com o NAT ativado
## Types of Network Address Translation
- Static NAT(SNAT)
	- One-to-one mapping entre o endereço local e global
	- Acha os hosts através do IP e não da porta igual o overloading faz
- Dynamic NAT
- Overloading
	- A mais popular
	- Trabalha junto com PAT
	- Many-to-one, é capaz de vários dispositivos se conectem à ela através de portas diferentes, e ela se conectar a internet global com somente 1 IP, assim, o IP do host não fica exposto e tem menos IPs na internet global
