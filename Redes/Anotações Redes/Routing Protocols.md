- Os protocolos abordados aqui está relacionado com dynamic route
## Routing Protocol Basics
- autonomous system (AS) é o conjunto de IPs ou rede que são administrados por uma organização
- IGP(interior gateway protocol), usado para fazer comunicação entre roteadores da mesma AS (autonomous system)
- EGP(exterior gateway protocol),  usado par trocar informações entre múltiplas ASs
## Administrative Distances (AD)
Usado para avaliar a confiabilidade das informações de roteamento de um roteador que vieram de roteadores vizinhos
- Um AD vai de 0 a 255, onde o 0 significa a rota mais confiável e o 255 a menos confiável, o 255 quer dizer que nenhum tráfego pode passar por essa rota
- Se o roteador receber dois updates de lista na mesma rede, ele verifica se a nova lista possui AD maior ou menor, e sempre vai preferir o com AD menor
- Caso os dois ADs tenham o mesmo valor, ele define pela contagem de saltos ou pela banda-larga qual será o AD escolhido
- Caso ainda sim os dois fiquem com métricas iguais, o roteador começa a enviar vários pacotes nos dois caminhos para ver o melhor
## Classes of Routing Protocols
- Distance vector (RIP, RIPv2, IGRP(interior gateway routing protocol))
	- Acha o melhor caminho para os pacotes que tenham menos pulos
	- Após preencher sua tabela com os melhores caminhos, ele passa essa tabela para todos os roteadores próximos
- Link state(OSPF(open shortest path first), e IS-IS(intermediate system-to-system))
	- Roteadores possuem 3 tabelas
		1. Track dos roteadores conectados diretamente
		2. Topologia da rede
		3. Tabela de roteamento
	- Roteadores link state sabem mais da rede do que qualquer distance-vector
- Hybrid(EIGRP(Enhanced Interior Gateway Routing Protoco))
	- Funciona só em equipamentos CISCO
## Distance-Vector Routing Protocols
Essa classe de protocolo passa tabelas de roteamento adiante
- Quando ela recebe uma tabela de roteamento, ela completa ela e joga para o próximo roteador
- Esse tipo de roteamento é chamado de routing by rumor, pois ele não verifica se a informação da tabela de roteamento que está chegando é verdadeira, apenas completa ela e passa para o próximo roteador
- Já que essa classe só leva em consideração como melhor rota a quantidade de putlo, se mais de uma rota tiver a mesma quantidade de pula, acontece o que chamamos de round-robin load balancing
## Routing Information Protocol (RIP)
- Faz parte da classe distance-vector routing 
- Envia para todas as interfaces a tabela de roteamento a cada 30 segundos
- Usa a quantidade de pulos para decidir a melhor rota
- O máximo de pulos possíveis é 15
- Classful routing
- RIPv1 usa só uma máscara de rede, ou seja, todos os dispositivos devem estar na mesma máscara 
## RIP Version 2 (RIPv2)
- Classless porque a informação da máscara é informada para os routes
- Suporta VLSM
## VLSM and Discontiguous Networks
- Fazer com que seja possível criar subredes de diferentes tamanhos
- Para implementes VLSM na rede, é necessário ter protocolos de roteamento que forneçam informações da subrede (RIPv2, EIGRP, OSPF)
## EIGRP (enhanced distance-vector protocol)
- Classless
- Permite uso de VLSMs
- Usado em redes grandes
- Suporta IP e IPv6
- Criado pela Cisco
- AD = 90
## Border Gateway Protocol (BGP)
- Usado para juntar ASs 
- Distance vector
## Link-State Routing Protocols
- Mantém muito mais informação do que protocolos distance-vector
- Armazena tabelas dos roteadores vizinhos
## Open Shortest Path First (OSPF)
- Cria um mapa hierárquico de rotas
- Mais eficiente porém mais complexo que o RIP e RIPv2
- Suporta VLSM e auto-sumarização
## Intermediate System to Intermediate System (IS-IS)
- É um IGP (interior gateway protocol), ou seja, trabalha dentro das ASs
- Cada roteador tem uma imagem da topologia da rede inteira igual o OSPF
- Utiliza serviços de rede sem conexão (CLNS)
- Rede de grande escala
## IPv6 Routing Protocols
- RIPng(trabalha na porta 521 UDP)
- EIGRPv6
- OSPFv3
- Todos fazem as mesmas coisas a diferença é que foram adaptados para usar link-local do IPv6



