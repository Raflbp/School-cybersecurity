# 💡 You either know, XOR you don't

> Autor: @Ralfbp

---

## ✨ Desafio: XOR

> Link: [https://cryptohack.org/courses/intro/xorkey1/](https://cryptohack.org/courses/intro/xorkey1/)

---

### Introdução

#### Enunciado

[![Captura de tela](https://i.postimg.cc/qgfm474C/Captura-de-tela-2025-06-05-133708.png)](https://postimg.cc/N248xByg)

O enunciado fornece uma sequência de caracteres codificados:

```
0e0b213f26041e480b26217f27342e175d0e070a3c5b103e2526217f27342e175d0e077e263451150104
```

#### 🛠️ Ferramenta utilizada:

```
https://cyberchef.io/#input=NzM2MjY5NjA2NDdmNmIyMDY4MjEyMDRmMjEyNTRmN2Q2OTRmNzYyNDY2MjA2NTYyMjEyNzIzNGY3MjY5Mjc3NTZk
```

#### Formato da flag:

```
crypto{nova_string}
```

---

### 🛠️ Resolução

Utilizando o site [CyberChef](https://cyberchef.io):

1. Na aba de "**Data format**", arraste a função **From Hex** para a área de "Recipe".
2. Em seguida, na aba "**Encryption / Encoding**", selecione **XOR**, altere o parâmetro de HEX para **UTF-8**.
3. Cole o início do formato da flag, ou seja, **crypto{** no campo de "Key".

[![Captura de tela](https://i.postimg.cc/7h9KTJJv/Captura-de-tela-2025-06-05-135023.png)](https://postimg.cc/n9s4yz1T)

4. A saída revelará parte da chave usada para codificar: **myXORke+y**. Retire o caractere **+** (pois foi um erro de codificação ou representa um caractere nulo/substituto).

[![Captura de tela](https://i.postimg.cc/rmfkqsym/Captura-de-tela-2025-06-05-135043.png)](https://postimg.cc/LYg7TH1K)

5. Com a chave correta **myXORkey**, refaça a operação XOR com a entrada original. O resultado será a flag.

---

### ✅ Conclusão

Esse desafio demonstra a técnica de descobrir a chave de XOR conhecida apenas parcialmente, explorando o conhecimento sobre o formato da flag. A partir de um pequeno trecho conhecido, conseguimos recuperar a chave completa e descriptografar a mensagem.

> ⚡ A flag final é: **crypto{1f_y0u_Kn0w_En0uGH_y0u_Kn0w_1t_4ll}**
