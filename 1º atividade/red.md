# 🧠 interencdec

> Autor: @Ralfbp

 O desafio Red é um exercício da categoria Forense, proposto pelo picoCTF.

----------

## 🔍 Desafio: Red

### Introdução

* O desafio pertence à categoria forense.
* O objetivo é capturar a flag por meio de uma análise técnica e minuciosa dos dados fornecidos.

--------
## 🧪Primeiras análises

### Enunciado do exercicio: **Red,Red,Red,Red**.
 
![image](https://github.com/user-attachments/assets/d0e92aaf-524c-4c7c-bc1d-18848d0033e5)

* Instalando  a imagens que o exercicio te entrega, temos a seguinte imagem.

[![red.png](https://i.postimg.cc/J0kw0v1g/red.png)](https://postimg.cc/2Lr9XHLF)

------

## 🖼️Analise da Imagem 
> **Obs : essa ferramenta foi ultilisada Kali Linux**

* Para analisar a imagem, utilizamos o pacote de desenvolvimento Ruby, que permite a execução da ferramenta zsteg, especializada em análise esteganográfica.


-------
## 💻 Instalação do pacote de desenvolvimento no **Kali Linux**.

### Para instalar o Ruby e os pacotes necessários para análise forense com Ruby:

``` bash
    * sudo apt install ruby ruby-dev
    * sudo gem install zsteg
```

## 🛠️Para fazer a analise ultilisando o Ruby.

* Ultilisando o comando .
  
```bash
     zsteg nome_da_imagem.png
```

--------
## 📊 Resoltado apos a analise

* Ao analisar a imagem, se tem muitas informações apartir disso 
 ``` bash                
meta Poem           .. text: "Crimson heart, vibrant and bold,\nHearts flutter at your sight.\nEvenings glow softly red,\nCherries burst with sweet life.\nKisses linger with your warmth.\nLove deep as merlot.\nScarlet leaves falling softly,\nBold in every stroke."                                                                                                                                                                                                                
b1,rgba,lsb,xy      .. text: "cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ=="                                                                                                                                                                                         
b1,rgba,msb,xy      .. file: OpenPGP Public Key
b2,g,lsb,xy         .. text: "ET@UETPETUUT@TUUTD@PDUDDDPE"
b2,rgb,lsb,xy       .. file: OpenPGP Secret Key
b2,bgr,msb,xy       .. file: OpenPGP Public Key
b2,rgba,lsb,xy      .. file: OpenPGP Secret Key
b2,rgba,msb,xy      .. text: "CIkiiiII"
b2,abgr,lsb,xy      .. file: OpenPGP Secret Key
b2,abgr,msb,xy      .. text: "iiiaakikk"
b3,rgba,msb,xy      .. text: "#wb#wp#7p"
b3,abgr,msb,xy      .. text: "7r'wb#7p"
b4,b,lsb,xy         .. file: 0421 Alliant compact executable not stripped
```

* Uma parte desse texto chama mais atenção que os demais


``` bash
"cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ=="    
```
------
## 🧬 Decodificando o Valor

### identificando o formato

* Usando o [dcode.fr](https://www.dcode.fr) procurando por **Cipher Identifier**
* Ele irá te mostrar que o valor está em **Base64 Coding**

### Decodificação
* Utilizando o mesmo site para descriptografar, será exposta a flag

  [![Captura-de-tela-2025-05-28-213721.png](https://i.postimg.cc/DZBkvP5X/Captura-de-tela-2025-05-28-213721.png)](https://postimg.cc/cgg5TYpx)

------------

## ✅ Conclusão
O desafio Red do picoCTF é um ótimo exemplo de como a análise forense pode revelar dados ocultos em arquivos aparentemente inofensivos, como imagens .png.

Ao utilizar ferramentas específicas como o zsteg, foi possível detectar padrões escondidos nos canais de cor da imagem. Através da leitura dos resultados em LSB (Least Significant Bit), identificamos uma string codificada em Base64. Após a decodificação, obtemos a flag final do desafio:

 ``` bash
    [picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}]
```

