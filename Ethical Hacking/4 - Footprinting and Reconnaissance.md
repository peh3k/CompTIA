## Open Source Intelligence
- EDGAR
- Whois
- Theharvester
## Social Networking
- Facebook
- Linkedin
- Usar the harvester para buscar funcionários de uma empresa
- Twitter
- recon-ng
- Maltego
## Domain Name System
- Top-level domains (TDLs) são os, .com, .br, .ed, .uk, .br etc
- Second-level domain é o nome, exemplo www.dominio.com, o second-domain é "dominio"
- Subdomain são subdominios antes do second-level domain
- Juntando tudo temos o fully qualified domain name (FQDN)
## DNS Lookups Using Host
`# host www.site.com`
- É possível fazer o contrário usando o IP mas a maioria dos servidores bloqueiam DNS reverso
## Using nslookup
![[Pasted image 20240614144734.png]]
## Using dig
![[Pasted image 20240614162149.png]]
## Zone Transfers
`# dig axfr dominio.com`
- Descobrir mais detalhes sobre a infraestrutura da rede
- A maioria dos DNS não permitem fazer transferência de zona, para isso é usado o método de brute force usando o dnsrecon
## Dnsrecon (bruteforce)
`# dnsrecon -d dominio.com -D wordlist.txt -t brt`
## Passive Reconnaissance
- r3con site para coletar todas as informações de um domínio
## Mirroring Sites with httrack
- Quando voce quer analisar um site offline, usa o httrack
## Google Hacking
- inurl
- intext
- site
- filetype
## IoT
- Shodan