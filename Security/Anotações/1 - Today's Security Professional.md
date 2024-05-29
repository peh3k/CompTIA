## 3 Pilares da Cybersecurity ou CIA Triad
- **Confidentiality**: Garante que usuários não autorizados não tenham acesso à dados sensíveis
- **Integrity**: Modificações na informação que não são autorizadas
- **Availability**: Garante que a informação esteja disponível a todo momento
- ***Nonrepudiation***: Não está nos pilares da Cybersecurity porém é um adicional, trata de informações que não podem ser desfeito por exemplo assinatura digital
## The DAD Triad
- **Disclosure**: É a exposição de dados sensíveis para pessoas não autorizadas, conhecido também como *data loss*. Disclosure é uma violação do princípio da confidencialidade
- **Alteration**: São modificações não autorizadas de informações e viola o princípio da integridade
- **Denial**: É a interrupção do acesso legítimo de um usuário autorizado, viola o princípio de disponibilidade. Ex: DDoS
## Breach Impact
Muita das vezes quando acontece alguma violação dentro de um sistema, podem vir vários dos tipos de risco ao mesmo tempo ou por consequência
###### Financial Risk
Dano financeiro, desde um ataque hacker até a perca de um computador da empresa, tendo assim que comprar outro
###### Reputation Risk
Quando uma "publicidade" causa a perca de credibilidade de seus clientes, empregos, fornecedores etc.
- Quando uma violação atinge uma empresa muita das vezes chega aos clientes, fornecedores etc. Expondo o personally identifiable information (PII) dessas pessoa, nada mais é que informação pessoal, por exemplo conta de banco
###### Strategic Risk
Uma violação que diminui os objetivos estratégicos da empresa, por exemplo um funcionário que perde um laptop contendo os melhores fornecedores, se cair em mãos erradas alguém tem acesso a esses fornecedores e pode querer contrata-los também, assim causando uma concorrência com a empresa e diminuindo o faturamento dela por exemplo
###### Operational Risk
Causa o mesmo que o *Strategic Risk* porém é pior, pode causar parada total na empresa ou áreas vitais dela
###### Compliance Risk
São riscos que infringem a lei caso aconteçam
## Implementing Security Controls
###### Gap Analysis
Gap é um risco potencial de uma organização
###### Security Control Categories
- **Techinical controls**: É a trindade CIA no meio digital, regras de firewall, lista de controle de acesso, sistemas de prevenção de intrusão e criptografia
- **Operational controls**: É a forma de como gerenciar um sistema no âmbito de segurança, monitoramento de log, gerenciamento de vulnerabilidades e reviews do sistema
- **Physical controls**: Segurança física, cadeados, cercas, sistema de prevenção de fogo e alarmes
###### Security Control Types
- **Preventive controls**: Parar uma possível ameaça antes que ela aconteça, firewall e criptografia
- **Deterrent controls**: Previnir que atacantes comecem um ataque, cães de guarda e arame farpado
- **Detective controls**: Identificar eventos que já aconteceram, sistemas de detecção de intrusões
- **Corrective controls**: Remediar uma intrusão, restaurar backups após uma intrusão
- **Compensating controls**: Mitigiar o risco de exceções feitas por políticas de segurança, ou seja, achar alternativas para realizar uma tarefa que não infringe a política da empresa, por exemplo quando for testar um software novo rodar ele em uma máquina virtual e em uma rede avulsa
- **Directive controls**: Infomar funcionários sobre os riscos
## Data Protection
- **Data at rest**: São dados em repousos que estão guardados em discos rígidos, fitas ou na nuvem que podem ser roubados por pessoas internas ou externas
- **Data in transit**: São dados que estão passando pela rede, principalmente por uma rede não confiável é aberta para *sniffing*
- **Data in use**: São dados que estão sendo usados no momento por um computador, podem ser roubados caso o computador esteja infectado
## Data Encryption
- Criptografia de dados na rede ou em discos 
- Diminui o risco de roubo de dados
## Data Loss Prevention (DLP)
- São técnicas e meios de prevenir roubos de dados, estas são: Agent-based DLP e Agentless (network-based) DLP
- **Agent-based DLP**: São softwares que são instalados nos sistemas que procuram por informações sensíveis(número de cartões, senhas etc). Podem monitorar também configurações e ações de usuários e bloquear certo tipos de ações e configurações, por exemplo bloquear o uso de USB
- **Agentless DLP**: São dispositivos dedicados que monitoram o tráfego da rede, procurando por dados que passam pela rede que não estão criptografados, assim podem bloquear a passagem desses pacotes ou então aplicar criptografia nesses dados
Sistemas DLP têm dois mecanismos de ação:
- **Pattern matching**: Quando o software acha um número que se parece com um número de cartão ele ativa um *trigger* por exemplo
- **Watermarking**: Quando sistemas aplicam tags eletrônicas em documentos sensíveis o sistema monitora os arquivos que contenham essas tags
## Data Minimization
Reduzir riscos de informações sensíveis serem roubadas ou expostas, transformar dados sensíveis de modo que eles não possam ser recuperados, isso é chamado de *data obfuscation*
- **Hashing**: Forma de criptografia que não tem volta, unidirecional, porém se o atacante tiver a tabela de hash ele pode fazer o que chamamos de *rainbow table attack*
- **Tokenization**: Colocar identificadores nas informações sensíveis, deixando-as relacionadas com tabelas, assim não expõe diretamente tais informações
- **Masking**: Substituir parcialmente uma informação sensível, exemplo número de cartão xxx345
## Access Restrictions
Meios de limitar o acesso
- **Geographic restrictions**: Limita o acesso aos dados de forma física
- **Permission restrictions**: Limite o acesso aos dados baseado no nível do usuário
- **Segmentation and Isolation**: Limitar o acesso aos dados segmentando a rede
