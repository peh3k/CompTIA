O transmission Control Protocol/Internet Protocol (TCP/IP) foi criado pelo departamento de defesa (DoD) para garantir e preservar a integridade dos dados
## TCP/IP and the DoD Model
- O modelo DoD é o modelo OSI porém condensado em quatro camadas:
	- Application layer(lida com a interface do usuário)
	- Host-to-Host layer(lida com pacotes de transporte)
	- Internet Layer(lida com endereçamento lógico)
	- Network Access layer(comunicação do host com a camada de internet)
![[Pasted image 20240226234041.png]]
![[Pasted image 20240226234306.png]]

## Application Layer Protocols
#### Telnet 
- Permite o host conversar remotamente com o servidor onde está instalado o telnet
- Acessa os recursos da outra máquina
- Não possui segurança e criptografia
- Substituído pelo Secure Shell (SSH) pois é mais seguro
#### File Transfer Protocol (FTP)
- Serve para transferir arquivos
- É mais vantajoso em casos de arquivos maiores, pois arquivos de até 5Mb podem ser enviados através de serviço de e-mail
- É uma pasta com arquivos(servidor)
- Da para logar em um serviço FTP porém tem login
- Não pode executar programas remotamente, somente criar arquivos e copiar
#### Secure File Transfer Protocol (SFTP)
- Usado quando precisa transferir arquivos de forma segura encriptada
- Usa serviço SSH para se tornar seguro, e dentro do SSH é feita a transferência normalmente com FTP
#### Trivial File Transfer Protocol (TFTP)
- Parecido com o FTP
- Não possui autenticação igual o FTP, logo não é seguro
- Pode somente enviar e receber arquivos
- Não possui as mesmas funções que o FTP pois é uma versão mais compacta do FTP
- Envia blocos menores de dados portanto é mais rápido
#### Network File System (NFS)
- Tipo de compartilhamento de arquivos
- Funciona como cliente-servidor, no servidor NFS possui os diretórios, e nos clientes possui o client do servidor NFS, o client monta a árvore de diretórios do servidor NFS localmente, parecendo que os arquivos sejam local, mas na verdade estão no servidor NFS, assim o usuário pode manipula arquivos sem nem perceber que os arquivos estão em outro lugar
#### Simple Mail Transfer Protocol (SMTP)
- Tranferência de e-mails
- Usa métodos de fila para transferir e-mails
- SMTP envia e-mails e POP3 recebe-os
#### Post Office Protocol (POP)
- Armazena a entrada de e-mails localmente
- Quando um e-mail chega, o dispositivo que está conectado a um servidor POP3 (última versão do POP), as mensagens que estão atreladas a esse cliente, são baixadas localmente, podendo assim ser apagada ou editada pelo cliente
- Não permite baixar e-mails específicos
- Está sendo substituída pelo IMAP
#### Internet Message Access Protocol, Version 4 (IMAP4)
- Igual o POP porém você tem a opção de escolher qual e-mail baixar localmente
- Mais seguro que o POP
- Possui filtros de pesquisa como cabeçalhos e corpos de mensagens
#### Transport Layer Security (TLS)
- Tanto o TLS quanto o Secute Sockets Layer (SSL) são protocolos de criptografia
- Segurança na transferência de arquivos
#### SIP (VoIP)
- Session Initiation Protocol (SIP)
- Constrói e descontrói comunicações de multimídia como voz e vídeos chamadas e comunicação em jogos
#### RTP (VoIP)
- Real-time Transport Protocol (RTP)
- Entrega de áudio e vídeo através da internet
- Usado em vídeo chamadas e streaming
#### Line Printer Daemon (LPD)
- Compartilhamento de impressões via TCP/IP
#### X Window
- Usado em operações cliente/servidor
- Replica a tela do servidor na tela do cliente
#### Simple Network Management Protocol (SNMP)
- Coleta informações relevantes da rede em tempo real
- Funciona como um cão de guarda, quando alguma coisa acontece na rede ele emite um alerta para a estação de gerenciamento
- Permite uma melhor administração de uma rede interna como um todo
#### Secure Shell (SSH)
- funciona como o Telnet, para fazer transferência de arquivos remotamente e conversar remotamente porém com as informações criptografadas
#### Hypertext Transfer Protocol (HTTP)
- Permite que sites misturem textos, links, gráficos etc
- Faz a comunicação entre o browser e o servidor web
#### Hypertext Transfer Protocol Secure(HTTPS)
- Pode ser escrito como SHTTP ou S-HTTP também
- Implemente segurança de criptografia e outras ferramentas de segurança entre o browser e o servidor web
#### Network Time Protocol (NTP)
- Protocolo que lida com o relógio das transferências afim de manter os dispositivos sincronizados pois existem protocolos que precisam estar perfeitamente alinhados para funcionar
#### Network News Transfer Protocol (NNTP)
- Transferência de notícias
- É pouco utilizado nos dias de hoje
#### Secure Copy Protocol (SCP)
- Faz o mesmo que o SFTP
- SFTP é mais utilizado
#### Lightweight Directory Access Protocol (LDAP)
- Forma de armazenar dados de forma hierárquica
- Armazena usuários, grupos ou dispositivos
#### Internet Group Management Protocol (IGMP)
- Gerenciar IPs sessões de grupo
- Hosts podem pertencer a um grupo, o IGMP é responsável por enviar mensagens aos hosts para descobrir a que grupos cada um pertence usando o protocolo IGMP
#### Line Printer Remote (LPR)
- Trabalha em conjunto com o LPD
- Envia dados do host para a rede da impressora usando o protocolo LPR
#### Domain Name Service (DNS)
- Resolve hostnames

Dynamic Host Configuration  Protocol (DHCP)
- Atribui IP, subnet, máscara, domínio, gateway padrão e DNS aos hosts que se conectam a ele

## Host-to-Host Layer Protocols
- Resumindo essa camada serve para pegar os dados da camada de aplicação e preparar para a camada de rede
- Possui dois protocolos
	- TCP
	- UDP
#### Transmission Control Protocol (TCP)
- Pega blocos grandes de informações da camada de aplicação e quebra em segmentos
- Antes do emissor enviar os seguimentos para o receptor, ambos precisam iniciar uma sessão remota
- TCP é full-duplex, confiável e preciso
- Assim que os segmentos de dados chegam na camada de rede, a camada de rede transforma em pacotes e envia para o destinatário
- Informa porta de destino e de origem, dados, janela, etc
![[Pasted image 20240228213503.png]]












