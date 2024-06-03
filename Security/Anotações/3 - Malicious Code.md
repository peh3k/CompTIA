## Malware
- Software que tem como objetivo causar danos a sistemas e dispositivos
## Ransomware
- É um malware que exige dinheiro em troca da libertação da vítima
- Criptografam pastas
- A maior parte desses ataques são feitos por phishing
- Os IoCs desse tipo de malware incluem:
	- Command and control (C&C)
	- Arquivos criptografados
	- Transferência de muitos arquivos
- Uma da melhores defesas contra o ransomware é fazer backup em outro local que não vai ser impactado
## Trojans
- Software que parece ser legítimo mas não é
- Triada Trojan é quando um software original passa por versões alternativas por exemplo o whatsapp modificado
- IoCs:
	- Arquivos adicionais sendo baixados
	- Controle do sistema
	- Arquivos e pastas sendo criados
- Remote access Trojans (RATs)
- Ferramenteas Anti-malware ajudam a combater os trojans
- Abre portas para Bot e botnets, que são hosts infectados
## Worms
- Diferente dos trojans que precisam de interação humana, os worms se espalham sozinhos
- Worms podem se esplahar através de e-mails, arquivos compartilháveis na rede, celulares etc.
- Os worms se instalam sozinhos, não precisando que cliquem neles, o que os torna perigosos
- Firewalls e controles de rede(segmentação) são as melhores soluções para diminuir ataques worms
- IoCs:
	- Arquivos maliciosos conhecidos
	- Download de componentes adicionais
	- C&C
	- Uso do cmd.exe, msiexec.exe etc
	- Teclado mexendo sozinho
## Spyware
- Obter informações de um sistema ou organização
- Stalkware é um tipo de spyware usado para monitorar parceiros em relações
- Pode ser evitado com ferramentas de altimalware
- IoCs:
	- Acesso remoto
	- Ataques contra browsers
- Spyware pode usar trojan, worm ou outros tipos de malwares
## Bloatware
- Quando você compra um computador e ele vem com aplicativos que você não queria
- Desinstalar bloatware ou usar uma ISO de um SO limpa é uma forma de corrigir esse malware
- O principal problema desse malware é que ele consome recursos que não precisariam ser consumidos
- Esse malware não necessariamente é perigoso porém pode abrir brechas pois são softwares que podem ter algum tipo de exploit
- Bloatware são simplesmente programas não desejados
## Viruses
- São programas maliciosos que se auto copiam e auto replicam quando são ativados
- Diferente dos worms, eles não se espalham pela rede ou para outros dispositivos, ficam somente no dispositivo infectado
- Virus possuem *trigger* que são configuração de quando o virus deve executar
- Virus também possuem payloads que são as ações propriamente ditas deles
- Tipos de vírus:
	- Memory-resident viruses: Permanecem na memória enquanto o dispositivo está ligado
	- Non-memory-resident viruses: Vírus que executam, se espalham e se desligam
	- Boot sector viruses: Residem dentro do setor de boot de uma mídia de armazenamento
	- Macro viruses: Quando códigos dentro de softwares são capazes de fazer o vírus se espalhar por exemplo um arquivo Word malicioso, tem um código malicioso dentro deste arquivo
	- Email viruses: Se espalham através de anexos de emails ou partes defeituosas de emails
## Keyloggers
- Captura o teclado
- Podem capturar movimentações do mouse, touchscreen ou deslize de cartões de crédito em máquininhas
- IoCs:
	- Hashes de arquivos e assinaturas
	- Atividade C&C
	- Nomes de processos
	- URLs conhecidos
- Existe hardware keyloggers
## Logic Bombs
- Não são programas maliciosos e sim códigos colocados dentro de programas que são ativados quando determinada condição seja estabelecida
- IoCs para logic bombs são menores pois requerem análises no código e a lógica do código
## Rootkits
- Malware que permite que atacantes acessem sistemas através de backdoor
- Difícil de ser detectado pois um dispositivo que está infectado com esse tipo de malware não é confiável
- A melhor forma de combater um rootkit é reistalar o SO ou voltar um backup mais antigo
- São usados em anti-cheat de jogos
- IoCs comuns para rootkits:
	- Hashes de arquivos e assinaturas
	- C&C
	- Invocação de comandos
	- Mudança de configurações
	- Portas se abrindo
- 