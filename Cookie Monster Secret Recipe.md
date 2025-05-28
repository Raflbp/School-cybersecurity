# 🧠 Cookie Monster Secret Recipe 

> autor:@Ralfbp
  O desafio "Cookie Monster Secret Recipe" do picoCTF pertence à categoria de Web Exploitation e foca na análise de cookies armazenados no navegador  
  - [página do desafio](https://play.picoctf.org/practice/challenge/469)
------------
## 🔍 Desafio: Web Exploitation

### Introdução 

 * Servidor Web HTML.
 * Objetivo encontrar a `flag.txt`** na página Web.

O desafio nos forneceu um ponto crucial para analise:
 * Cookie dentro da inpeção de página

------------

## 🧪Primeiras análises 

### A questão te entrega o seguinte enunciado:

[![1.png](https://i.postimg.cc/765XbVZJ/1.png)](https://postimg.cc/9RjynyTc):

 *  O link abaixo é a página que te aparece al clicar **here** [http://verbal-sleep.picoctf.net:49737/](http://verbal-sleep.picoctf.net:49737/)

![2.png](https://i.postimg.cc/8zK6sfXq/2.png)
 * Ao abrir página e ler o enunciado, o primeiro pensamento seria, procurar dentro dos **Cookies** da página HTML, para faze-lo clique com o botão direito em algum lugar da área em branco **ou pressione `Ctrl + Shift + I`** para abrir a aba de inspeção.
-----------
## 🍪 Analise dos **Cookies**

### inspeção 

* Abrindo a página indo em **Application** e  clicando em **Cookies**, serão mostrados os cookies que a página possui.
* Essa página em especifico possui apenas um [**http://verbal-sleep.picoctf.net:49737**]
 
[![Captura-de-tela-2025-05-28-195216.png](https://i.postimg.cc/2yDzmWgp/Captura-de-tela-2025-05-28-195216.png)](https://postimg.cc/Kk0XD1ZQ)

* A página não possui nenhuma informação relevante no **cookie**

--------
## 🔓 Expondo os Cookies

### Expondo as informações nos Cookies e as analisando

* Voltando a página do desafio, mais nenhum informação esta exposta.
* É necessário fazer uma tentativa com **Username** e **Password** inconrretos.
* Ao faze-lo e olhando novamente para a página **Inspect** ele te revelará as informações presentes nos **Cookies**.

[![3.png](https://i.postimg.cc/RFwdc0wv/3.png)](https://postimg.cc/8JPLGNyY).

------

## 🧬 Decodificando o Valor

### Identificando o formato

* O campo **Value/valor** te mostra algumas letras e números que parecem criptografados 
* Com ajuda do site [dcode.fr](https://www.dcode.fr) e o  **Cipher Identifier**
* Ele irá te mostrar que o valor está em **Base64 Coding**.
###  Decodificação
* Utilizando o mesmo site para descriptografar, será exposta a **flag**
  
[![4.png](https://i.postimg.cc/7L00RWhV/4.png)](https://postimg.cc/8Fk7JwhJ).

-------

## ✅ Conclusão
* O desafio "Cookie Monster Secret Recipe" do picoCTF nos conduz por uma exploração simples, porém eficaz, dos cookies de uma aplicação web. Através da inspeção dos cookies gerados após uma tentativa de login incorreta, foi possível identificar um valor codificado em Base64. Utilizando ferramentas online como o dcode.fr, conseguimos decodificar esse valor e descobrir a flag oculta.

* Esse tipo de desafio ensina a importância de entender o funcionamento dos cookies, como eles armazenam informações sensíveis e como podem ser manipulados ou analisados em testes de segurança. Além disso, ressalta o papel de ferramentas auxiliares na engenharia reversa de dados codificados.



