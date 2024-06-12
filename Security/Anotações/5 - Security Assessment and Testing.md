## Vulnerability Management
- Identificar
- Priorizar
- Remediar vulnerabilidades
- Usam *vulnerability scanning*
## Identifying Scan Targets
- Escanear vulnerabilidades em todos os sistemas de uma organização ou apenas em uma parte dos sistemas
- Qual a classificação dos dados desse sistema?
- O sistema está exposto à internet, pública ou rede semi-pública
- Quais serviços são oferecidos pelo sistema?
- O sistema é de produção, teste ou de desenvolvimento?
- Essas perguntas devem ser respondidas para definir qual o nível de criticidade do sistema
## Determining Scan Frequency
- Automação de escaneamento
- Scheduling do scanning
- Nessus
- *Risk appetite* é o quanto de risco a organização está disposta a correr
- Regulatory requiriments: São scans que são requeridos para ter uma frequência mínima, Payment Card Industry Data Security Standard (PCI DSS) ou a Federal Information Security Modernization Act (FISMA)
- Techinical constrainsts: Limita a frequência do scan, isso é feito para garantir que todos os scans foram completos com sucesso e deixar todos os scans iguais
- Business constraints: Quando uma organização interrompe os scans em períodos muito ativos daquela organização para evitar que atinja processos críticos
- Licensing limitations: Limitar o consumo do scan ou o número de scans feitos simultaneamente
## Configuring Vulnerability Scans
- Schedule
- Reports
#### Scan Sensitivity Levels
- Usar templates ou desenvolver um template para aquele tipo de scan
- Tipos de scan, só para redes, nuvem, malware etc
#### Supplementing Network Scans
- Scan com credencial
- Scan sem credencial (simula atacante externo que não tem acesso root)
#### Scan Perspective
- Scan de partes diferentes da rede
- Controles que mais afetam os resultados dos scans:
	- Firewall settings
	- Network segmentation
	- Intrusion detection systems (IDSs)
	- Intrusion prevention systems (IPSs)
#### Scanner Maintenance
- Manutenção regular
- Deixar os *vulnerability feeds* atualizados
#### Scanner Software
- Bug fixes
- Feature enhancements
#### Vulnerability Plug-in Feeds
- Atualizar plugins diariamente 
- Security Content Automation Protocol (SCAP) são padrões de segurança:
	- Common Configuration Enumeration(CCE)
	- Common Platform Enumeration(CPE): Nomes padrões para nomes de produtos e versões
	- Common Vulnerabilities and Exposures(CVE)
	- Common Vulnerability Scoring System(CVSS)
	- Extensible Configuration CHecklist Description Format(XCCDF):Linguagem para especificar checklists
	- Open Vulnerability and Assessment Language(OVAL):Linguagem para especificar testes de baixo nível usados por checklists
## Vulnerability Scanning Tools
Ferramentas para auxiliar o scan e achar vulnerabilidades em sistemas
#### Infrastructure Vulnerability Scanning
- Network vulnerability scanner:
	- Tenable's Nessus
	- Qualys
	- Rapid7's Nexpose
	- OpenVAS
#### Application Testing
Ferramentas que analisam softwares e buscam vulnerabilidades comuns 
- Static testing: Analisa o código sem executa-lo
- Dynamic testing: Executa o código como parte do teste usando inputs variados para buscar por vulnerabildiades
- Interactive testing: Combina teste estático e dinâmico
#### Web Application Scanning
- Buscam por vulnerabilidades de SQL injection, cross-site scripting (XSS)  e cross-site request forgery (CSRF)
- Nikto
- Arachni
#### Reviewing and Interpreting Scan Reports
- Internet Engineering Task Force (IETF) documentos detalhados que falam sobre vulnerabilidades
- Risk factor
- Risk information
#### Understanding CVSS
- Common Vulnerability Scoring System
- Avaliar a severidade de uma vulnerabilidade
- Técnica de score
- CVSS é um componente do SCAP
- Avalia a vulnerabilidade em 8 medidas diferentes
#### Attack Vector Metric (AV)
- Descreve scores de vetores de ataques
	- Phisical(P): Score 20
	- Local(L): Score 55
	- Adjacent(A): Quando o atacante tem acesso a rede em que o sistema está, Score 62
	- Network(N): Quando o atacante tem acesso remoto na rede, Score 85
#### Attack Complexity Metric (AC)
- Descreve a dificuldade de achar um exploit
	- High(H): Precisa de condições específicas para achar um exploit, Score 44
	- Low(L): Não precisa de condições específicas, Score 77
#### Privileges Required Metric(PR)
- Descreve o tipo de conta que o usuário precisa para atacar um sistema
	- High(H): Atacante precisa ser admin para conduzir o ataque, Score 27
	- Low(L): Atacante precisa de privilégios básicos, 62
	- None(N): Atacante não precisa se autenticar para conduzir o ataque, Score 85
#### User Interaction Metric(UI)
- Descreve se o atacante precisa usar outro humano para fazer o ataque
	- None(N): Não precisa de ação de qualquer usuário a não ser do atacante, Score 85
	- Required(R): Precisa da ação de outra pessoa, Score 62
#### Confidentiality Metric(C)
- O tipo de informação que será afetada caso o atacante invada o sistema
	- None(N): Não possui informações confidenciais, Score 0
	- Low(L): O acesso a informação é possível mas o atacante não consegue modifica-la, Score 22
	- High(H): Todas as informações do sistema foram comprometidos, Score 56
#### Integrity Metric(I)
 - Descreve se um atacante pode alterar uma informação
	 - None(N): Score 0
	 - Low(L): Modificação da informação é possível mas o atacante não consegue ter controle de qual informação foi modificada, Score 22
	 - High(H): O atacante consegue editar e fazer o que quiser com a informação, Score 56
#### Availability Metric(A)
- O impacto que pode causar a um sistema caso um atacante invadir
	- None(N): 0
	- Low(L): A performance do sistema é afetada, Score 22
	- High(H): O sistema caiu completamente, Score 56
#### Scope Metric(S)
- Informa se um ataque com escopo X pode afetar sistemas do escopo Y
	- Unchanged(U): Afeta somente o escopo atacado
	- Changed(C): Pode afetar sistemas além do atacado
#### Interpreting the CVSS Vector
- O CVSS é uma linha contendo as informações faladas anteriormente
- Exemplo da linha: CVSS:3.0/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:N/A:N
- Por exemplo a primeira seção que é o AV:N indica que o Attack Vector(AV) é o Network (N)
#### Calculating the Impact Sub-Score (ISS)
- Calcula de forma única o impacto da vulnerabilidade considerando a confidencialidade, integridade e disponibilidade
- Fórmula: ISS = 1-(1-Confidentiality) x (1-Integrity) x (1-Availability)
#### Calculating the Impact Score
- O impacto considerando o ISS e o scope metrics (S)
- Caso o scope metrics for U(unchanged), basta multiplicar o ISS por 6.42
- Caso o scope metrics for C(changed) usa a fórmula: Impact = 7.52 x (ISS - 0.029) - 3.25 x (ISS - 0.02)^15 
#### Calculating the Exploitability Score
- Exploitability = 8.22 x Attack Vector x Attack Complexity x Privileges Required x User Interaction
#### Calculating the Base Score
- Com todas essas informações anteriores podemos definir o score base para o CVSS
- Se o impact é 0, o score é 0
- Se o scope metric é unchanged (U), soma o score do impacto e da exploitability
- Se o scope metric é changed (C), soma o score do impacto e a exploitability e depois multiplica por 1.08
- O valor máximo do score é 10, caso passe de 10 precisa ser definido para 10
- Existem sites para calcular automaticamente o base score(CVSS calculator), um deles é o NIST
#### Categorizing CVSS Base Scores
- 0: None
- 0.1 - 3.9: Low
- 4.0-6.9: Medium
- 7.0-8.9: High
- 9.0-10.0: Critical
## Confirmation of Scan Results
#### False Positives
- Scanners as vezes causam falsos positivos
- Quando os scanners acham corretamente uma vulnerabilidade é chamado de *true positive report*
- Administradores de banco de dados, engenheiros de sistemas, técnicos de redes, desenvolvedores conseguem avaliar se o report é falso positivo
#### Reconciling Scan Results with Other Data Sources
- Security information and event management (SIEM) são sistemas que correlacionam vários logs de scanners diferentes e gera um output único
## Vulnerability Classification
Existem vários tipos de vulnerabilidades que são escaneadas por scanners de vulnerabilidades e será abordado adiante
#### Patch Management
- Aplicar patch de segurança (atualizações pequenas)
- Programas de gerenciamento de patch fazem verificações periódicas a fim de encontrar problemas de patches(versões antigas etc)
#### Legacy Platforms
- Plataformas que foram descontinuadas e que não recebem mais suporte do fornecedor
#### Weak Configurations
- Usar configurações padrões 
- Credenciais padrões
- Deixar portas de serviços abertas
- Deixar permissões abertas
#### Insecure Protocols
- Telnet pode ser substituído pelo SSH
- FTP pode ser substituído pelo SFTP e FTPS
#### Weak Encryption
- Quando você vai implementar a criptografia é necessário apenas duas coisas, o algorítimo da criptografia e a chave para usar nesse algorítimo
## Penetration Testing
- Teste de penetração tem como o objetivo achar falhas em um sistema como se fosse um ataque real
- É legalizado e autorizado
- Threat Hunting
## Penetration Test Types
- Phisical penetration testing
- Offensive penetration testing: Achar exploits em sistemas
- Defensive penetration testing
- Integrated penetration testing: Combina os aspectos do teste ofensivo e defensivo
Os testes podem ser feitos em algumas modalidades:
- Known enviroment onde o atacante tem acesso as todas as informações do sistema previamente
- Unknown environmente onde o atacante não sabe nada do sistema e precisa achar as informações manualmente
- Partially known environment onde o atacante sabe apenas algumas informações
## Rules of Engagement (RoE)
- A *timeline* em que o ataque pode ser feito, ou seja, o período pois existem casos em que os ataques podem atrapalhar o sistema de produção, por isso deve ser feito fora da hora de produção
- Quais lugares, sistemas, aplicações e outros *targets* podem ser atacados
- *Data handling requiriments* significa que o atacante precisa assinar um contrato para não fazer nada com os dados da empresa além dos testes
- Quais comportamentos são esperados do alvo, se ele irá bloquear ou não o ataque etc
- Quais recursos estão comprometidos com o teste
- *Legal concerns*, tudo o que for feito deve seguir as leis
- Quando e como as comunicações irão ser feita, isto é, quando o atacante irá atualizar a empresa, semanalmente, diariamente etc
## Reconnaissance
Antes de começar um ataque é necessário coletar informações sobre o alvo, existem dois tipos de coleta
- Passiva, onde o atacante pega informações sem ser necessariamente do alvo propriamente dito, pode usar enumeração DNS, WHOIS etc
- Direta, onde o atacante busca informações diretamente com o alvo, busca de portas, footprinting(saber o SO e a aplicação por trás do alvo)
- *War driving* é quando o atacante vai próximo ao local do alvo com um carro equipado com antenas potentes para tentar se conectar com a rede interna
- *War flying* é o mesmo que o *war driving* porém usam veículos aéreos, drones por exemplo, esses veículos aéreos são chamados de UAVs
## Running the Test
- Acesso inicial
- Escalar privilégios
- *Pivoting* ou movimento lateral, que é tentar afetar outras máquina na rede além do alvo
- Por fim estabilizar a persistência, normalmente feta usando *backdoors*
## Vulnerability Life Cycle
1. Identification(Identificar uma falha)
2. Analysis(Analisar a falha)
3. Response and Remediation(Tratar essa falha)
4. Validation of Remediation(Reescanear o sistema para saber se a falha foi eliminada)
5. Reporting(Documentar)

1. a x c
2. b x d
3. c ok
4. a x c
5. a ok
6. b ok
7. a x c
8. a ok
9. b ok
10. a ok
11. a ok
12. c ok
13. d ok
14. c ok
15. c x b
16. c ok
17. a x c
18. b ok
19. b ok
20. d x c


