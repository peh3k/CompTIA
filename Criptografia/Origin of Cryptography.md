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
