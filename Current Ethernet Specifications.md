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
- O endereço MAC é divido em dois, tendo 24 bits de um lado e 24 de outro, o primeiro lado de 24 bits é o OUI(organizationally unique identifier), que é um número único de 24 bits
