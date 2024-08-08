- Surgiu nas civilizações Romanas e Egípcias
- Hieróglifo é o mais antigo tipo de criptografia (4000 anos atrás)
## Steganografia
- Parecido com criptografia porém a mensagem fica invisível, escondia em uma imagem por exemplo
## Modern Cryptography
- Opera de forma digital
- Opera de forma matemática
- Criptologia são divididas em duas partes
	- 1.Criptografia
		- Proteger informações por meio da matemática
	- 2.Criptoanalise
		- Quebrar a criptografia
## Security Services of Cryptography
- Confidentiality: Evitar acesso não autorizado a informação
- Data Integrity: Evitar que a informação seja alterada
- Authentication: Garante que a informação é original e foi emitida por uma entidade confiável
## Cryptography Primitives
- Criptografia
- Hash
- Message Authentication codes (MAC)
- Digital Signatures
## Cryptosystems
- Conjunto de técnicas de criptografia desde quem está enviando um dado até quem está recebendo
## Components of a Cryptosystem
- Plaintext(dado que será protegido)
- Algorítimo de criptografia(processo matemático que criptografa o plaintext)
- Ciphertext(plaintext criptografado)
- Algorítimo de descriptografia
- Chave de criptografia
- Chave de descriptografia
- Key space(Coleção de todas as possíveis chaves de descriptografa)
## Types of Cryptosystems
- Criptografia simétrica
- Criptografia assimétrica
## Symmetric Key Encryption
- Quando a mesma chave é usada tanto para criptografar quanto para descriptografar
- Exemplos de criptografia simétrica: DES, 3DES, IDEA e BLOWFISH
- Não é tão comum nos dias de hoje por conta da sua segurança
## Asymmetric Key Encryption
- Quando existe uma chave só para criptografar e outra para descriptografar
- Ambos quem está recebendo e enviando a mensagem precisa ter uma chave pública e uma privada
- A chave pública precisa ficar em um repositório a fim de ambos os hosts tenham acesso e a chave privada deve ser mantida em segredo
- Quem está enviando precisa criptografar a mensagem com a chave pública de quem está recebendo, e a mensagem só poderá ser descriptografada usando a chave privada par dessa chave pública
![[Pasted image 20240807212416.png]]
## Attacks On Cryptosystems
- Ataques podem ser passivos ou ativos
## Passive Attacks
- Obter acesso não autorizado a informação
- Informações são roubadas sem o dono saber
## Active Attacks
- Alterar a informação
- DOS
## Encryption Scheme
- Public Algorithms: Os detalhes do algorítimos são públicos
- Proprietary Algorithms: Os detalhes do algorítimo são privados
- É importante assumir que o algorítimo de criptografia é conhecida pelo atacante
## Cryptographic Attacks
- O objetivo de um ataque é quebrar a criptografia e obter o plaintext
- Caso o atacante tenha acesso a chave privada, o sistema fica conhecido como *broken* ou *compromised*
- **Ciphertext Only Attacks (COA)**: Atacante tem acesso a vários ciphertexts e tenta descobrir o plaintext ou a key a partir de padrões desses ciphertexts
- **Known Plaintext Attack (KPA)**: Quando o atacante sabe o plaintext de alguma parte do ciphertext, o objetivo é tentar decifrar o resto do ciphertext com o plaintext que ele tem
- **Chosen Plaintext Attack (CPA)**: Quando o atacante tem tanto o plaintext quanto o ciphertext correspondente, isso é importante para descobrir qual a key é usada
- **Dictionary Attack**: Quando o atacante tem um dicionário contendo os plaintexts e os ciphertexts correspondentes que ele coletou em outro momento
- **Brute Force Attack (BFA)**: O atacante testa N keys no ciphertext a fim de quebra-lo
- **Birthday Attack**: Usa o paradoxo do aniversário ao seu favor, o atacante tenta descobrir uma key diferente da original porém que gera a mesma hash, esse método é mais rápido que o brute force matematicamente falando.
- **Man in Middle Attack (MIM)** : O atacante escuta a "conversa" entre os hosts e coleta ou altera as informações
- **Side Channel Attack (SCA)**: Tenta achar falhas físicas nos sistemas de criptografia
- **Timing Attacks**: O atacante observa o tempo que um computador leva para criptografar ou descriptografar, isso pode dar indicações se uma key é grande ou pequena
- **Power Analysis Attacks**: Parecido com timing attacks porém usando o consumo de energia
- **Fault analysis Attacks**: O atacante induz o sistema de criptografia ao erro a fim de obter outputs úteis