- Escanear portas (serviços) e ver as versões deles, a versão pode ter algum exploit
## Ping Sweeps
- Antes de escanear uma rede, usar ferramentas ICMP para verificar se o dispositivo está "vivo"
#### Using fping
`# fping -aeg 192.168.1.0/24`
- Esse comando ira pingar todos os IPs dessa rede
- As vezes o firewall bloqueia os pacotes ICMP