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
## Earlier Cryptographic Systems
- Todos os sistemas antigos são baseados na criptografia simétrica
- Os sistemas funcionavam via alfabeto e não binário como hoje
## Caesar Cipher
- Trocam letras do alfabeto por outras letras de outro alfabeto
- Turno de 3 (shift 3)
- Muito fácil de quebrar
![[Pasted image 20240811211709.png]]
## Simple Substitution Cipher
- É o caeser cipher só que aprimorado
- Permuta de letras, possui 4x10^26 possibildiades
- A escolha pode ser feita aleatoriamente 
- Computadores de hoje não conseguem quebrar esse sistema por conta da quantidade de possibilidade
## Monoalphabetic and Polyalphabetic Cipher
- Monoalphabetic sempre o plaintex A será igual ao ciphertext B, não tem como mudar, igual nos casos do Caesar cipher e simple substitution cipher
- Polyalphabetic é possivel que a letra A possa significar mais de uma outra letra, por exemplo a letra A pode ser a letra O e a letra H ao mesmo tempo
## Playfair Cipher
- Forme uma grid 5x5 do alfabeto
- Escolhe uma *key*
- A key deve ser colocada em primeiro lugar na grid
- Se a key tiver letras que se repetem, a letra que se repetir é ignorada
- Abaixo está um exemplo da grid com a *key* "tutorial"
![[Pasted image 20240811213240.png]]
## Vigenere Cipher
- Converte a letra em seu respectivo numero que seria a posição que elas estão no alfabeto, ex letra C é 3
## One-time Pad
- A key é gerada aleatoriamente
- A key tem o mesmo tamanho do plaintext

