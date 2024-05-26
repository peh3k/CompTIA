## Introduction to Wireless Technology
- Usa radio frequências(RFs)
- Frequência alta, menor a distância
- 802.11b/g é a mais usada
## The 802.11 Standards
- WLAN 1 e 2Mbps
## 2.4GHz (802.11b)
- Data rate de no máximo 11Mbps
- 2.4GHz
- Rate-shift é a diminuição do data rate conforme o host se distancia do AP
- 3 canais não sobrepostos
- DSSS 
## 2.4GHz (802.11g)
- Data rate máxima de 54Mbps
- 2.4GHz
- DSSS
- OFDM
- Caso exista 2 802.11g e 1 802.11b conectados em um AP, todos os hosts obrigatoriamente terão que usar o 802.11b
- Só pode ter até 3 AP na mesma área, porque só o canal 1,6 e 11 não tem sobreposição
## 5GHz (802.11a)
- Máximo de 54Mbps de data rate com 12 canais que não tem sobreposição
- 12 canais
- OFDM
## 2.4GHz/5GHz (802.11n)
- n canais
- + 100Mbps
- DSSS
- CCK
- OFDM
- Usa o MIMO que é quando várias antenas enviam sinais para vários paths, isso aumenta a velocidade da transferência
## Direct-Sequence Spread Spectrum (DSSS)
- Espalha um sinal com uma largura mais alta pra melhorar a resistência do sinal e aumentar a segurança do sinal contra ruídos
- Usado na tecnologia da IEEE 802.11b
## Frequency-Hopping Spread Spectrum (FHSS)
- Fica mudando de frequência rapidamente para dificultar interceptações do sinal
- Permite que múltiplos usuários compartilhem a mesma banda de frequência sem causar muita interferência no sinal
## Orthogonal Frequency Division Multiplexing (OFDM)
- Possui pouca interferência e pouca distorção
## Wireless Network Components
- Mais fácil de instalar do que rede cabeada pois só precisa de um AP e de um NIC wireless
## Wireless Access Points (APs)
- Wireless access point (WAP) ou AP
- Pode ser usado como uma ponta entre o cliente wireless e a rede cabeada
- Pode ser usado também para fazer a ponte entre duas redes cabeadas (não todos, dependendo das configurações)
## Wireless Network Interface Card (NIC)
- Cliente wireless
## Wireless Antenas
- Transmitem e recebem sinais
- Omni directional (point-to-multipoint)
- directional (point-to-point)-Yagi
- Antenas Yagi provêm maior distância pela mesma qualidade do que a omni directional
- A maioria dos APs usam omni porque o AP precisa enviar os sinais para todos os lados
- dBi/dBd
## Installing a Wireless Network
- Existem dois modos de instalação principal: ad hoc e modo infraestrutura
- Esses modos são chamados de service sets
## Ad hoc Mode: Independent Basic Service Set (IBSS)
- Modo mais fácil de instalar
- Os wireless NICs podem se comnunicar com outros NICs diretamente sem a necessidade de um AP, porém os dois NICs precisam estar no modo ad hoc
- Essa independência é chamada de IBSS
## Infraestructure Mode: Basic Service Set (BSS)
- NICs nesse modo somente se comunicam diretamente com os APs
- Todos os clientes wireless aparecem para toda a rede
- Um AP precisa estar conectado em um cabo de rede, isso é chamado de Distribution System (DS)
- Nome
- SSID é o nome da rede
- Security
- Se dois APs tiverem o mesmo SSID, a rede se torna extended service set (ESS)
## Mesh and Lightweight Access Port Protocol (LWAPP)
- Topologia Mesh
- Possui redundância pois cada mesh é conectado em vários meshs
- Mais caro e é melhor usar em empresas grandes
## Signal Degradation
- Como o 802.11 usa radio frequência, possui limite de distância
## Wireless Security
## Remote Authentication Dial In User Service (RADIUS)
- Quando o host vai se conectar no AP ele deverá informar a senha, nesse método RADIUS, ao enviar a senha para o AP, o AP monta um pacote RADIUS e esse pacote é enviado para o servidor de autenticação, o server de autenticação envia o resultado para o AP e é o AP que decide se vai liberar o acesso ou não, pois no pacote que chega do server de autenticação contém se o acesso é liberado ou negado
## Temporal Key Integrity Protocol (TKIP)
- Existe uma chave mestra e uma temporal, a temporal é derivada da chave mestra e essa é mudada a cada sessão feita no AP
- Para cada pacote transmitido possui uma chave de 48 bits (IV), essa chave é combinada com a chave temporal dessa sessão e é gerada outra chave de criptografia para aquele pacote específico
- Mistura a chave temporal, a IV e o endereço MAC do cliente a fim de criar uma chave de criptografia única para cada pacote
## Wi-Fi Protected Access (WPA) or WPA 2 Pre-Shared Key
- WPA utiliza a chave temporal
- Utiliza um mecanismo chamado de MIC(Message Integrity Check) para verificar a integridade dos dados e garantir que não sejam alterados durante a transmissão
- WPA2 utiliza o método de encriptação AES portanto é mais seguro
