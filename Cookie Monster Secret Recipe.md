# Cookie Monster Secret Recipe 

> autor: Rafael Bruno 

## Desafio: Web Exploitation

### Introdução 

O desafio "Cookie Monster Secret Recipe" do picoCTF pertence à categoria de Web Exploitation e foca na análise de cookies armazenados no navegador  
- [Página do desafio](https://play.picoctf.org/practice/challenge/469)

### Primeiras análises 

> A questão te entrega o seguinte enunciado:

Clicando em **here**, entra-se nesse link[]:  
[http://verbal-sleep.picoctf.net:49737/](http://verbal-sleep.picoctf.net:49737/)

Isso vai te levar até essa página[].

Com essa página aberta, clique com o botão direito em algum lugar da área em branco **ou pressione `Ctrl + Shift + I`** para abrir a aba de inspeção[].

Com a aba aberta, vá até **Applications** e procure pelo cookie com o nome:  
`verbal-sleep.picoctf.net`

Abrindo o cookie, existe um campo com o nome **Value/valor**:


Esse valor está codificado. Copie o valor e entre no site [dcode.fr](https://www.dcode.fr).  
Procure por **Cipher Identifier**. Ele irá te mostrar que o valor está em **Base64 Coding**.

Peça para o próprio dcode decodificar, e será exposta a **flag**[].




