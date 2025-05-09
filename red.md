# interencdec

> Autor: Rafael Bruno

## Desafio: Red

### Introdução

Red é um desafio de **forense** com o seguinte enunciado:  
**[Red, Red, Red, Red]**.  
O desafio entrega um arquivo `.png` que é unicamente uma imagem vermelha.

### Resolução

Abrindo o Kali Linux, utilizamos o terminal para instalar as dependências necessárias:

```bash
sudo apt install ruby ruby-dev
sudo gem install zsteg


    Se analisa a imagem .png dando os resultados em vermelho 
    []

    um dos permeiros resutados é:

    [7cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ]

    usando o [dcode.fr](https://www.dcode.fr) procurando por **Cipher Identifier**. Ele irá te mostrar que o valor está em **Base64 Coding**

### Resultado

    Ao converter a string, tera a flag
     
    [picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}]



