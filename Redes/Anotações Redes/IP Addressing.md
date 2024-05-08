## IP Terminology
- Bit é 0 ou 1
- Byte são 8 ou 7 bits
- Octeto são 8 bits
- Endereço de rede é o endereço de um dispositivo na rede
- Endereço de broadcast é o endereço que envia para todos os hosts, seja ele host de uma rede, uma rede inteira, subnetes etc
## Hierarchical IP Addressing Scheme
Com um IP de 32 bits de informação, é possível ter uma quantidade enorme de endereços IP, porém é inviável pois os servidores não tem como armazenar todos esses endereços, então surgiu a hierarquia de IP, que consiste em dividir os IP's em grupos a fim de não precisar cada computador ter um endereço IP único.
Podemos dizer que esses grupos são divididos em sessões como se fossem números de telefone:
- Área code, composto por uma área muito grande
- Prefixo, indica a área local dentro da área code
- O número, indicando o host
## Network Addressing
- O endereço IP é dividido em número da rede e host
- Cada tipo de divisão é um tipo de grupo, que são chamados de classe
- A classe A por exemplo te um grande número de hosts porém quantidade de rede pequena
- Já na C, é o inverso, possui um número grande de rede e uma pequena quantidade de host
- Na classe B é equilibrado
## Class A Addresses
É composta por 1 byte de rede, e 3 bytes de hosts, ou seja, rede.host.host.host
- Os IP's de classe A sempre começam com o primeiro bit 0
- O primeiro bit é reservado para essa classe, somente os outros 7 bits do octeto podem ser manipulados
- Na classe A, pode ter um total de 128 redes, pois já que os 7 bits que sobraram podem ser manipulados, então a combinatória é de 2^7, que é igual a 128
- Então uma rede da classe A pode ser de 0 a 127
- Como o 127 é usado para fazer diagnósticos e o 0 é usado para setar a rota padrão, então ficam disponíveis somente do 1 até 126
- Ou seja, a rede utilizável é a quantidade de redes possíveis menos 2, nesse caso, 128 -2 =126
- Um host não pode ser tudo 0 ou tudo 255 pois estes já estão reservados para gateway padrão e para broadcast respectivamente, ex: não pode ser 10.0.0.0, mas pode ser 10.0.0.1
- 127.0.0.1 é reservado para loopback
## Class B Addresses
rede.rede.host.host
- Possui 16 bits pois são dois octetos
- Os primeiros 2 bits DEVEM ser 1 e 0, não podendo ser modificados
- Com isso sobram 14 bits que podem ser manipulados, pois 16 - 2 = 14
- O range da rede tipo B é de 128 a 191
## Class C Addresses
rede.rede.rede.host
- Os primeiros 3 bits do primeiro octeto são 110
- Assim como são 3 bytes de rede, são 24 bits, porém como 3 bits são reservados para essa classe, sobram 21 bits
- O range de rede da classe C é de 192 até 223, 192 é caso todos os bits(tirando os que são reservados) estiverem desligados, e no caso de 223 é caso se esses bits estiverem ligados
## Class D and E Addresses
- O endereço de 224 a 255 é reservado para redes de classe D e E
- Classe D (224-239), usado para endereço de multicast
- Classe E (240-255) usado para casos específicos
- Endereço multicast é vai de 224.0.0.0 até 239.255.255.255
## Private IP Addresses
Para pouupar espaço de endereços IPs, foi criado o endereço IP privado, como por exemplo dentro de casa
- Network Address Translation (NAT) é usado para pegar esse IP privado e converter para que seja usado na internet também
## APIPA
Automatic Private IP Addressing
- Quando o servidor DHCP não estiver disponível, no windows tem uma feature que se chama APIPA, que seta para o computador seu endereço IP, máscara etc, parecido com que o servidor DHCP faz, porém não é recomendado.
## Broadcast Address
Existe alguns tipos de broadcasts
- Layer 2 broadcasts (é enviado para todos os hosts em uma LAN) - hardware broadcast, e não passa do roteador
- Layer 3 broadcasts (é enviado para todos os hosts na rede)
- Unicast (é enviado para somente um host)
- Multicast (pacotes que são enviado de um source para vários dispositivos em redes diferentes)
- Solicitações para um servidor DHCP é unicast, o host envia um unicast (FFF:FFF:FFF) para o roteador, e então o roteador busca o DHCP mais proximo, ou em outra rede
## Internet Protocol Version 6 (IPv6)
- Flexibilidade
- Eficiência
- Capacidade
- Otimizado
- Próxima geração de IP
- IPv4 possui só 4.3 bilhoes de IPs, o que é pouco
- Possui o IPSec, para segurança e mobilidade
- Possui endereços de 128 bits
- Tem o anycast, que encaminha o pacote para o host mais próximo com o mesmo endereço
- É dividido em 8 grupos de números e letras (hexadecimal)
- Quando fazer uma requisição http para um IPv6 é importante deixar o IP entre colchetes
## IPv6 Shortened Expression
- Pode remover os zeros que estiverem sozinhos e no lugar adicionar o ":" ex:2001:db8:3c4d:12:0:0:1234:56ab pode ser abreviado para 2001:db8:3c4d:12::1234:56ab 
- Isso só serve para quando tiver 1 zero
- Em casos de mais de um zero, pode ser substituido todos por somente 1 zero, ex: 2001:0000:0000:0012:0000:0000:1234:56ab para 2001::12:0:0:1234:56ab
- Isso só pode ser feito caso só tenha zeros em um grupo de caractéres
## IPv6 Address Types
- Unicast (Interface)
	- Unicast global(rota pública)
	- Link-local (não roteáveis)
	- Unique local (quase únicos globalmente)
- Multicast
	- Endereços multicast em IPv6 começam com FF
- Anycast
	- Identifica múltiplas interfaces
	- Um pacote anycast é entregue para só um endereço, o mais próximo
## Special IPv6 Addresses 
- 0:0:0:0:0:0:0:0 = ::