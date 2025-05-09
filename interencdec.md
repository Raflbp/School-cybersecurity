
# interencdec 

> autor: Rafael Bruno 

## Desafio: Cryptography

### introdução 

    O desafio "interencdec" do picoCTF tem como objetivo testar seus conhecimentos sobre criptografia, e mostrar que é possível criptografar uma string mais de uma vez

### Resolução 
       
> A questão te entrega o seguinte enunciado:

    Você consegue entender o significado real deste arquivo?
    baixe o arquivo **aqui** [].

    abrindo o arquivo em .txt se tem essa frase encriptada

        [YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyeG9OakJzTURCcGZRPT0nCg==]

    Entrando no site [dcode.fr](https://www.dcode.fr) procurando pela função  **Cipher Identifier**, ele identifica que é uma string em base64. Com essa informação entra-se no site [cyberchef](https://cyberchef.org/) e usando o **From Base64** terá esse resultado.


        [b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2xoNjBsMDBpfQ=='] 

    Com esse resultado temos outra string em base64 mas que precisa ser alterada para te entregar o resultado necessário , retirar os 2 primeiros caracteres e o último [b'] e [']

        [d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2xoNjBsMDBpfQ==]

    Fazendo a decodificação novamente terá.

        [wpjvJAM{jhlzhy_k3jy9wa3k_lh60l00i}]

    Voltando para o [dcode.fr](https://www.dcode.fr) e usando novamente a função **Cipher Identifier**, se descobre que é uma [caesar cipher] utilizando o mesmo para descriptografar a flag fica assim.
    

### Resultado


        [picoCTF{caesar_d3cr9pt3d_ea60e00b}]

