# 💡 Favourite Byte

> Autor: @Ralfbp

---

## ✨ Desafio: XOR

> Link: [https://cryptohack.org/courses/intro/xorkey0/](https://cryptohack.org/courses/intro/xorkey0/)

---

### Introdução

#### Enunciado

[![Captura de tela](https://i.postimg.cc/d1W36wHK/Captura-de-tela-2025-06-04-235033.png)](https://postimg.cc/LY1m6KFy)

O enunciado nos fornece uma sequência numérica em hexadecimal e menciona que há uma letra repetida.

```
73626960647f6b206821204f21254f7d694f7624662065622127234f726927756d
```

As instruções indicam que:

* Primeiro é preciso **decodificar a string hexadecimal**.
* Em seguida, realizar uma operação de **XOR**.

Ferramenta utilizada:

```
https://cyberchef.io/#input=NzM2MjY5NjA2NDdmNmIyMDY4MjEyMDRmMjEyNTRmN2Q2OTRmNzYyNDY2MjA2NTYyMjEyNzIzNGY3MjY5Mjc3NTZk
```

Sabemos também que a flag será formatada como:

```
crypto{nova_string}
```

---

### 🛠️ Resolução

Utilizando o site [CyberChef](https://cyberchef.io):

1. Na aba de "**Data format**", arraste a função **From Hex** para a área de "Recipe".
2. Em seguida, na aba "**Encryption / Encoding**", selecione **XOR Brute Force** e adicione ao Recipe.
3. A ferramenta testará todas as chaves de 1 byte (0 a 255). A flag correta aparecerá quando a chave for **10** (decimal).

[![Captura de tela](https://i.postimg.cc/QMpZj3RZ/Captura-de-tela-2025-06-05-000143.png)](https://postimg.cc/SXNvGwSg)

Resultado:

```
crypto{0x10_is_my_favourite_byte}
```

---

### ✅ Conclusão

Esse desafio reforça a importância de compreender os formatos de codificação (como hexadecimal) e a aplicação de XOR, uma das operações mais comuns em criptografia e desafios CTF.

O uso do CyberChef torna a resolução muito mais acessível e visual, permitindo identificar rapidamente a chave correta para a decifração.

> ⚡ A flag final é: **crypto{0x10\_is\_my\_favourite\_byte}**
