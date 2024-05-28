## Security Filtering
- Somente os hosts permitidos poderão acessar sua rede
## Access Control Lists
- Firewall
- Access control list (ACL) 
- Normalmente estão em roteadores, determinam quem deve ter acesso a ele pelo IP
- Port ACL filtra o tráfego baseado na porta
## Tunneling
- Encapsular um protocolo em outro para garantir que a transmissão é segura
- Virtual Private Network (VPN)
- Secure Sockets Layer (SSL)
- Secure Sockets Layer Virtual Private Network (SSL VPN)
- Layer 2 Tunneling Protocol (L2TP)
- Point to Point Tunneling Protocol (PPTP)
- Internet Protocol Security (IPSec)
## Virtual Private Network (VPN)
- Objetivo é garantir uma conexão segura entre dois pontos e se tornar local na rede remota
- Existem 3 tipos de VPNs
	- Remote access VPNs: acessar uma rede remota de qualquer lugar de forma segura
	- Site-to-site VPNs: permite que empresas se conectem às suas sedes e uma rede pública WAN
	- Extranet VPNs: clientes e parceiros de empresas se comunicarem com ela de forma limita apenas para negócios B2B
## SSL and SSL VPN
- É baseada na criptografia RSA
- Usado para se conectar de um web browser e um web server
- HTTPS usa SSL
## L2TP
- Suportam VPNs que não usam o protocolo TCP/IP
- Funciona na camada 2 do modelo OSI
## PPTP
- Desenvolvido pela Microssoft
- Combina o PPP (unsecure point to point protocol) e GRE(generic routing encapsulation)
- Antigo e não muito seguro
## IPSec
- Funciona na camada de rede no modelo OSI (camada 3)
- Fornece autenticação e criptografia através da internet
- Os dois principais protocolos que trabalham com IPSec é o Authentication Header (AH) e Encapsulating Security Payload (ESP)
- AH só fornece autenticação, ESP fornece autenticação e criptografia
- Protocolo AH não é compatível com o NAT
- IPSec funciona em dois modos transporte e tunneling, o tranporte apenas cria autenticação e criptografia porém um túnel não é criado e no tunneling mode o pacote inteiro é encapsulado dentro do IPSec
- No ESP o payload e o header do pacote é criptografado
## Encryption
- Proteger dados
- Publico
- Privado
## Private Encryption Keys
- Ambos os emissores e receptores deverão ter a mesma chave para criptografar e descriptografar os dados
- O lado ruim é que para enviar essa chave privada é necessário envia-la usando chaves públicas
## The Data Encryption Standars (DES)
- Chave privada de 56 bits
- Não era tão segura pois só são 56 bits
## Triple Data Encryption Standard (3DES)
- Fazia criptografia da DES 3 vezes, isto é 56 x 3 = 168 bits
- Mais segura porém mais lenta
- Por ser mais lenta foi criado sua posterior que é a AES
## The Advanced Encryption Standard (AES)
- 128, 192 ou 256 bits
- Criada em 2002 é a mais recente
## Public Key Encryption
- Usa o algorítimo Diffie-Hellman que usa a chave pública e privada para criptografar e descriptografar os dados
- Comunicação e transferência da chave pública porém de forma segura em um rede que não é segura
## RSA Data Security
- Algorítimo de chave pública
- Assimétrico
## Pretty Good Privacy (PGP)
- Criada por Zimmerman para transferência de e-mails
- Forte método de criptografia
- Usa combinação simétrica e assimétrica
## Remote Access
- Bom para empregados que trabalham de casa pois podem acessar a rede da empresa
## Remote Access Services (RAS)
- Não é um protocolo
- Combina o hardware e o software para fazer um acesso remoto
- RAS por si só não é seguro porém pode ser usado em conjunto com o PPTP para fazer o tunneling e tornar seguro
## RDP (Remote Desktop Protocol)
- Permite que usuários se conectem em um computador enquanto ele está rodando
- Remote Desktop
## PPP(Point to Point Protocol)
- Provê autenticação, criptografia e serviços de compressão
- ISPs usam o PPP para autenticar clientes juntamente com o modem
## PPPoE (Point to Point Protocol over Ethernet)
- É uma extensão do PPP
- Seu objetivo é encapsular os frames do PPP dentro dos frames da Ethernet
- Funciona em dois estágios: discovery e session
## VNC (Virtual Networking Computer)
- Controlar um computador ou servidor á distância de forma gráfica
- Não é seguro por si só mas pode ser usado em conjunto com SSH ou VPN
## ICA(Independent Computing Architecture)
- Comunicação entre cliente e servidor
## User-Authentication Methods
## Public Key Infrastructure (PKI)
- PKI permite que pessoas se comuniquem de forma segura usando certificate authority (CA)
- Usa criptografia assimétrica, ou seja, chaves diferentes são usadas para criptografar e descriptografar, enquanto na simétrica é apenas uma chave para ambos
## Kerberos
- Emprega criptografia forte para todas as transações e comunicações
## Authentication, Authorization, and Accounting (AAA)
- o AAA(os três As) não é um protocolo e sim um modelo conceitual
- As duas implementações mais usadas do AAA é o RADIUS e TACACS+
#### RADIUS
- Usado para fazer autenticação dos clientes
- Usado bastante em firewalls
- Quando um cliente quer acessar uma porta TCP/IP particular, ele deverá informar o login e senha, então o firewall contacta o RADIUS para verificar se o login que foi passado está certo
#### The Terminal Access Controller Access-Control System Plus (TACACS+)
- É um protocolo
- É um método alternativo ao RADIUS
- TACACS+ separa a autenticação e autorização do usuário enquanto o RADIUS deixa-os em um só perfil e TACACS+ usa TCP enquanto RADIUS usa UDP
- Considerado mais seguro e estável do que o RADIUS
## Network Access Control (NAC)
- É um método para manter os hosts seguros antes deles se conectarem na rede
## Challenge Handshake Authentication Protocol (CHAP)
- Usuário e senha nunca passam explicitamente pela rede
- Ambos o cliente e o server estão configurados coma mesma frase secreta isso é chamado de *shared secret*
## MS-CHAP
- Microsoft Challenge CHAP
- MS-CHAP criptografa a *shared key* localmente enquando o CHAP mantém ela em texto explícito
## Extensible Authentication Protocol (AEP)
- Extensão do PPP
- 

