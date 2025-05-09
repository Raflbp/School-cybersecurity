
# interencdec 

> autor: Rafael Bruno 

## Desafio: Red

### introdução 

    Red é um desafio  de **florence** com o seguinte enuncuado [Red,Red,Red,Red] o desafio te entrega um Arquivo '.png' [] que é unicamente uma imagem em vermelho** 

### Resolução 
    
    Abrindo o kali e usando o comando no terminal [sudo apt install ruby ruby-dev] e [sudo gem install zsteg] instalando o aplicativo [ruby  e ruby-dev] e [zsteg]

    Ainda no terminal se usando o comando 
        [steg -a red.png ]

    Se analisa a imagem .png dando os resultados em vermelho 
    []

    um dos permeiros resutados é:

    [7cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ]

    usando o [dcode.fr](https://www.dcode.fr) procurando por **Cipher Identifier**. Ele irá te mostrar que o valor está em **Base64 Coding**

### Resultado

    Ao converter a string, tera a flag
     
    [picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}]



