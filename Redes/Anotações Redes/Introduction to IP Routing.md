## Routing Basics
- Roteadores não se importam com os Hosts, apenas com as redes e os melhores caminhos para que um pacote percorra
- Para um roteador funcionar ele precisa:
	- Endereço de destino
	- Roteadores vizinhos
	- A melhor rota
	- Como manter cada rede remota
- O roteador aprende sobre a rede remota através de roteadores vizinhos ou de um administrador, então o roteador monta uma tabela de roteamento (um mapa da rede) que descreve como achar redes remotas
- Caso a rede esteja conectada fisicamente, ele não precisa procurar pela melhor rota
- Caso contrário ele tem duas formas de definir a rota:
	- Rota estática (muito trabalho)
	- Rota dinâmica, roteadores próximos se comunicam entre si através de um protocolo próprio, e se atualizam das mudanças que tiveram na rede de cada um, assim ambos os roteadores atualizam suas tabelas de rotas automaticamente para não ter conflito de pacotes
## IP Routing Process
Enviando um pacote ICMP de uma rede para outra, host A para host B
1. Pelo IP de destino é possível saber se está na mesma rede ou não, nesse caso não está
2. Host A encapsulaos dados, contentoo IP de origem e destino
3. Host A verifica em sua tabela de roteamento se tem uma rota definida para o host b
4. Se não tiver rota, o host A envia o pacote para o gateway padrão
5. O roteador verifica em sua tabela de roteamento, caso mesmo assim não possua na tabela de roteamento, o pacote pula de roteador a roteador até chegar na rede do host B
6. Quando o pacote chega a rede do host B é finalmente entregue à ele
7. Host B responde e faz todo o processo invertido
## IGP e EGP
O roteamento dinâmico é dividido em dois protocolos
- IGP(interior gateway protocol)
- EGP(exterior gateway protocol)
	- Border gateway protocol (BGP), usado por ISPs
	