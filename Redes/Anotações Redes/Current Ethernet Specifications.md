## Network Basics
Basicamente na mesma rede o host A não sabe o endereço IP nem o endereço MAC do host B, o qual ele quer se comunicar, para isso ele envia um protocolo NBNS para o broadcast(o broadcast são todos os hosts), então quer dizer que ele envia um pacote NBNS para todos os hosts na rede perguntando quem tem o nome do destino, que no caso é o host B. Após isso, o host A envia um pacote ARP para todos os hosts da rede perguntando quem tem o endereço IP para quem o host A quer se conectar, o protocolo ARP retorna o endereço MAC e seu respectivo IP do host, que no caso é o host B.
## Ethernet Basics
- A ethernet é um meio de acesso onde todos os hosts compartilham a mesma banda larga
- Ethernet está presente tanto na camada de enlace quanto na camada física
## Collision Domain
- É um termo que da Ethernet que é quando um dispositivo envia pacotes na rede, todos os outros dispositivos na rede prestam atenção nesse pacote
- Colisão é ruim porque quando dois hosts enviam pacotes na mesma rede eles acabam se colidindo e um deles terá que reenviar o pacote
- Isso acontece em casos em que dois ou mais hosts estão conectados no mesmo hub com um único collision domain e um único broadcast domain
## Broadcast Domain
- Significa quando todos os dispositivos na rede vão escutar esse broadcast
- Domínio de broadcast pode ser feito tanto lógico quanto físico
## CSMA/CD
- As redes Ethernet usa o Carrier Sense Multiple Access with Collision Detection(CSMA/CD)
- Permite que dispositivos compartilhem a mesma largura de banda sem haver colisões
- Processo para a comunicação:
	1. Antes do host transmitir dados na rede, ele verifica se tem algum sinal lógico no cabo, se não tiver, significa que nenhum outro host está enviando informações, então está tudo limpo e a partir de então o host começa a enviar os dados.
	2. O host que está enviando os dados verifica constantemente se algum outro host na rede está enviando dados na rede, se não estiver nenhum host enviando dados, o host continua se comunicando sem problemas, caso um outro host comece a enviar dados, o host que está enviando envia um sinal de jam (jam signal) para todos os hosts no seguimento dizendo para parar de transmitir dados, assim os hosts que começaram a enviar devem esperar para transmitir os dados novamente, então é gerado um algorítimo backoff que determina quando os hosts deverão voltar a retransmitir os dados novamente, caso as colisões continuarem a acontecer depois de 15 tentativas , os hosts irão dar timeout  
- Quando uma colisão em uma rede Ethernet acontece:
	- É enviado um jam signal para todos os dispositivos na rede informando que uma colisão aconteceu
	- Essa colisão gera um algorítimo backoff
	- Todos os hosts da rede param de enviar dados até que o tempo expire
## Half- and Full-Duplex Ethernet
#### Half-Duplex
- Definida como Ethernet 802.3
- Usa somente um par de fios (sinais digitais) tanto para enviar quanto ara receber
- Possui de 30% a 40% de eficiência
#### Full-Duplex
- Usa dois pares de fios ao mesmo tempo
- Usa conexão ponto a ponto
- Velocidade maior e sem colisão pois usa o ponto a ponto
- Possui 100% de eficiência
- Switch to host
- Switch to switch
- Host to host usando um cabo crossover
- Não funciona no hub
- É possível alterar na configuração do NIC o quanto de velocidade deve passar por ela, se ela suporta a opção do full-duplex
## Ethernet at the Data Link Layer (camada de enlace)
- A ethernet na camada de enlace é responsável pelo endereçamento da ethernet, normalmente o MAC
- Ethernet quebra os pacotes vindos da camada de rede e separa em frames
- Endereços MAC são feitos de hexadecimais
## Binary to Decimal and Hexadecimal Convertion
#### Binário para Decimal
- Nibble são 4 bits
- Byte são 8 bits
![[Pasted image 20240219143959.png]]
- Para converter o número binário 1101 em decimal, já que é um nibble fica mais facil, pois encaixa respectivamente no 8 4 2 1, nesse caso o bit 1, 2 e 4 estão ativados, então o valor é 13
- Em casos de bytes a conta é um pouco maior, no caso o número 11111111 é 255 em decimal pois todos os bits estão ativados, logo 128+64+32+16+8+4+2+1 = 255
#### Hexadecimal para Decimal
- Os números em hexadecimal vão de 0 a 9, depois disso os caracteres são substituídos por letras A,B,C,D,E,F nos lugares do 10,11,12,13,14,15 respectivamente
- Números em hexadecimal começam com 0x 
- Um caractere hexadecimal forma um nibble e dois caracteres formam um byte
- Para converter um número binário em hexadecimal basta dividi-lo em nibble, no caso 01010101 divide em dois nibbles, dando o primeiro nibble 0101 e o segundo 0101, ambos tem o segundo e o quarto bit ativo, portando é 4+1 = 5, então o hexadecimal é esses dois nibbles juntos, dando 0x55
## Ethernet Addressing
- Endereçamento de funciona como MAC(Media Access Control) codificado diretamente no NIC
- O endereço MAC possui 48 bits (6 bytes) porém escrito em hexadecimal
- O endereço MAC é divido em dois, tendo 24 bits de um lado e 24 de outro, o primeiro lado de 24 bits é o OUI(organizationally unique identifier), que é o fabricante e o segundo lado é o número de série do dispositivo desse fabricante. Levando em consideração o MAC 00:1A:2B:3C:4D:5E, a primeira parte (24 bits) são os três primeiros octetos pois cada caractere é um nibble (4 bits), logo os três primeiros octetos são 00:1A:2B, se cada caractere é 4 bits então 8 são 24 bits, esse primeiro grupo determina o fabricante da placa de rede, já os demais, os outros três octetos, 3C:4D:5E é o serial único do dispositivo propriamente dito
## Ethernet Frames
- A camada de enlace é responsável por combinar bits em bytes e converter esses bytes em frames
- Os frames servem para encapsular pacotes
- Os frames são passados através das estações de Ethernet em um grupo de bits igual o formato do endereço MAC, isso proporciona detecção de erros CRC (cyclic redundancy check)
![[Pasted image 20240219221510.png]]
- Preamble: Composto por 7 bytes mais 1 byte final para sincronizar o clock do emissor e receptor
- DA(destination Address): Endereço MAC de destino, 6 bytes ou 48 bits
- SA(source address): Endereço MAC da origem, também 48 bits por o endereço MAC é composto por 48 bits
- Lenght: Indica o tipo de protocolo usado na camada superior, que é a camada de rede, o valor 0x0800 indica um protocolo IPv4 por exemplo
- Data: Carrega os pacotes enviados pela camada de rede, os pacotes podem variar de 64 a 1500 bytes e são pacotes do tipo IP, ICMP, ARP etc
- Frame Check Sequence (FSC): Um espeço na última posição do frame que guarda o CRC
Tipo de frame Ethernet II usando o protocolo IP
![[Pasted image 20240219223647.png]]
## Channel Bonding / link aggregation
É um arranjo de redes de computadores para gerar redundância e maior velocidade
Nesse caso é usado dois cabos para cada caso um falhar terá outro
![[Pasted image 20240219225045.png]]
## Ethernet at the Physical Layer
- Antigamente tinha a ethernet 802.3, esse número refere-se ao padrão ethernet, tem velocidade de 10Mbps
- A IEEE(Institutos de engenheiros e eletricistas e eletrônicos) fizeram o "upgrade" do padrão 802.3 para o 802.3u(fast ethernet) e o 802.3ab(gigabit ethernet de categoria 5+) e por último 802.3ae(10Gbps em fibra óptica e cabos coaxiais)
Especificações da ethernet na camada física
![[Pasted image 20240220094947.png]]
- A EIA/TIA criou a especificação para a ethernet na camada física
- A especificação consiste em usar o cabo RJ (registered jack) em cabos UTP, que são os RJ-45, ou um conector modular de 8 pinos
- Cada cabo ethernet tem uma especificação na qual é levado em consideração a perda de sinais que é medido em decibéis (dB)
![[Pasted image 20240220142920.png]]
![[Pasted image 20240220142943.png]]
![[Pasted image 20240220142959.png]]
![[Pasted image 20240220143008.png]]
