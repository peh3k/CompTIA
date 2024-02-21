## Common Network Connectivity Devices
#### Hub
- Dispositivo que conecta todos os seguimentos da rede juntos na topologia estrela
- Quando ocorre uma transmissão em um das portas, a transmissão é escutada por todas as outras portas
- Costumar ocorrer muitas colisões, por esse motivo não é mais utilizado em empresas
#### Repeater
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
- Decide a rota na qual os frames irão passar, define o menor caminho
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
#### Multilayer Switch



