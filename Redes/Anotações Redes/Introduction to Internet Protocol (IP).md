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
- Permite fazer transferência de arquivos
- É uma pasta com arquivos
- Da para logar em um serviço FTP porém tem login
- Não pode executar programas remotamente, somente criar arquivos e copiar
#### Secure File Transfer Protocol (SFTP)
- Usado quando precisa transferir arquivos de forma segura encriptada
- Usa serviço SSH para se tornar seguro, e dentro do SSH é feita a transferência normalmente com FTP
#### Trivial File Transfer Protocol (TFTP)



