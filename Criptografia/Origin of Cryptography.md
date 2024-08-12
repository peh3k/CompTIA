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
## Modern Symmetric Key Encryption
- Utiliza bits ao invés de alfabetos
## Block Ciphers
- Ao invés de criptografar caractere por caractere, block ciphers pega o bloco inteiro criptografa e descriptografa usando esse bloco, exemplo o AES 128 bits, que o tamanho do bloco é 128bits.
- Evite usar blocos pequenos pois é mais fácil de ser quebrado
- Evite usar blocos grandes pois para isso é necessário modificar o plaintext antes de ser criptografado
- É melhor se o tamanho do bloco for múltiplo de 8 bits pois a maioria dos processadores tratam os dados dessa forma
![[Pasted image 20240812150451.png]]
## Padding in Block Cipher
- É quando é necessário adicionar bits em um bloco caso ele não esteja em blocos, por exemplo um plaintext de 150 bits precisa de 3 blocos de 64 bits, porem para completar os 192 faltam 42, nesse caso precisa adicionar mais bits ao final do bloco para que complete 3 blocos inteiros
## Block Cipher Schemes
- Digital encryption standard(DES)
- Triple DES ou 3DES
- Advanced Encryption Standard(AES)
- IDEA
- Twofish
- Serpent
## Stream Ciphers
- Processa bit por bit
## Feistel Block Cipher
- DES é um tipo de Feistel Cipher
- Consiste em varios rounds de substituição seguido de permutação
- ![[Pasted image 20240812152323.png]]
- Quanto mais rounds mais seguro é porém demora mais para criptografar e descriptografar
## Data Encryption Standard(DES)
- Symmetric-key 
- Usa 16 rounds da estrutura de Feistel
- Recebe um plaintext de 64 bits
- Usa uma key de 56 bits
- Gera um ciphertext de 64 bits
- Cada round possui 48 bits
- ![[Pasted image 20240812153845.png]]
## 3-Key Triple DES
- Evolução de DES
- Usa o mesmo processo do DES porém, após obter o ciphertext, é feito o reverse cipher usando uma segunda key do DES, e no fim o plaintext decifrado é cifrado novamente porém com a terceira key do DES
## Advanced Encryption Standard (AES)
- 6 vezes mais rápido que o 3 key DES
- 128-bit de dados e 128/192/256 bits de keys
- Computa em byte ao invés de bit
- O número de round é variável e depende do tamanho da chave, para chaves de 128bits=10rounds, 192bits=12 round e 256bits = 14 rounds
## Block Cipher Modes of Operation
- Processa o bloco de dados de tamanhos fixos
- Caso passe do tamanho fixo, o dado é dividido em uma série de blocos menores, onde o cipher opera um por um
#### Electronic Code Book (ECB) Mode
- Método mais simples para criptografia de bloco
- Usado no AES
- Basta dividir o bloco em blocos menores, criptografar cada bloco usando a mesma chave e depois concatenar o resultado para formar o ciphertext cmopleto
#### Cipher Block Chaining (CBC) Mode
- Mais seguro que ECB
- Cada bloco é feito o XOR com o bloco anterior para manter uma ligação entre eles, o que torna esse modo não determinístico, diferente do ECB que é determinístico
#### Cipher Feedback (CFB) Mode
- Permite criptografia de dados em tamanhos menores do que o tamanho do bloco
- Se um bloco de ciphertext for corrompido, só afeta o bloco em si e não os demais
- Usado para criptografia em tempo real
####  Output Feedback (OFB) Mode
- O output do bloco é a entrada do próximo bloco
#### Counter (CTR) Mode
- Converte o block cipher em stream cipher
- Ambos o sender e o receiver precisam estar sincronizados
- Permitem processo paralelo pois cada bloco é independente
## Public Key Encryption
![[Pasted image 20240812174304.png]]
- Chaves diferentes são usadas para criptografar e descriptografar
- Cada receptor possui uma única chave de descriptografia, que é a private key
- Receptores precisam publicar a encription key, que é a públic key
- Existem 3 tipos de esquemas de public key
## RSA Cryptosystem
- Gerar uma chave pública e uma privada a partir de valores escolhidos P e Q
- Só pode ser revertida para plaintext com a private key
- A segurança depende dos números primitivos P e Q, pois quanto maiores mais seguro
## EIGamal Cryptosystem
- Logarítimo
- Hoje é utilizado keys de 2048bits
## Elliptic Curve Cryptography(ECC)

## Data Integrity in Cryptography
- Passive threats: Ruídos na comunicação
- Active threats: Quando o atacante pode manipular o dado
## Cryptography Hash functions
- Input pode ser diferente mas o output sempre terá o mesmo tamanho
- Hash values é o resultado do plaintext após a operação de hash
- ![[Pasted image 20240812182425.png]]
- Hash values normalmente são menores que o input, por isso chamam o hash de compressão
- São mais rápidos
## Properties of Hash Functions
- É difícil ou quase impossível de reverter um hash
- Difícil de fazer bruteforcing
- Difícil achar input diferente para a mesma hash
## Design of Hashing Algorithms
- Funciona em blocos
- Funciona em rounds parecido como o block cipher, o output do bloco anterior é o input do bloco atual
## Popular Hash Functions
#### Message Digest (MD)
- MD2,MD4,MD5 e MD6
- 128-bit
#### Secure Hash Function (SHA)
- SHA-0, SHA-1, SHA-2 e SHA-3
- SHA-1 é a mais usada mundialmente dentre essas
- SHA-2 possui derivações, SHA224, SHA-256, SHA-384 e SHA-512
- SHA-3 oferece melhor performance e resistência a ataques
#### RIPEMD
- RIPEND, RIPEMD-128, RIPEMD-160, 256 e 320 bits
- A mais utilizada entre essas é a RIPEMD-160
- As 256 e 320 bits só diminuem a chance de existir colisão, e não oferece vantagens em relação a segurança igual a RIPEMD-160
#### WhirIpool
- 512bit hash function
- Derivação do AES
## Applications of Hash Functions
- Password Storage
- Data integrity check
## Message Authentication Code (MAC)
- Symmetric key techinique
- O sender e o receiver compartilham a mesma key
- Funciona como uma assinatura
## Cryptography Digital signatures
- Public key
- ![[Pasted image 20240812190856.png]]
- Encrypt-then-sign e sign-then-encrypt

