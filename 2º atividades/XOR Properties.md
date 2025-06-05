# 💡 XOR Properties

> Autor: @Ralfbp

---

## ✨ Desafio: XOR

> Link: [https://cryptohack.org/courses/intro/xor1/](https://cryptohack.org/courses/intro/xor1/)

---

### Introdução

#### Enunciado

[![Captura de tela](https://i.postimg.cc/fy81ngrk/Captura-de-tela-2025-06-05-192014.png)](https://postimg.cc/fS08Y5Zh)

O desafio explora a propriedade comutativa e associativa do XOR, destacando que a ordem das operações não altera o resultado final, o que permite reverter ou reorganizar as operações para encontrar a flag escondida.

#### 🛠️ Ferramenta utilizada:

```
https://cyberchef.io/
```

#### Formato da flag a ser encontrada:

```
crypto{nova_string}
```

---

## 🛠️ Resolução

Utilizando o site [CyberChef](https://cyberchef.io):

### Etapa 1: Encontrar CHAVE2

1. Adicione a operação **From Hex** para converter a entrada.
2. Em seguida, adicione a operação **XOR** e insira a **CHAVE1** como chave:

```
a6c8b6733c9b22de7bc0253266a3867df55acde8635e19c73313
```

3. Adicione a operação **To Hex** para visualizar o resultado em hexadecimal.
4. Use como entrada **CHAVE2 ^ CHAVE1**:

```
37dcb292030faa90d07eec17e3b1c6d8daf94c35d4c9191a5e1e
```

[![Imagem](https://i.postimg.cc/MGnJYxXH/Captura-de-tela-2025-06-05-193029.png)](https://postimg.cc/sBCLVkYC)

Resultado armazenado:

```
91 14 04 e1 3f 94 88 4e ab be c9 25 85 12 40 a5 2f a3 81 dd b7 97 00 dd 6d 0d
```

### Etapa 2: Encontrar CHAVE3

1. Altere a chave do XOR para o resultado obtido acima.
2. Use como entrada **CHAVE2 ^ CHAVE3**:

[![Imagem](https://i.postimg.cc/jSpDVRmw/Captura-de-tela-2025-06-05-193603.png)](https://postimg.cc/dh9srcqw)

Resultado armazenado:

```
50 40 53 b7 57 ea fd 3d 70 9d 63 39 b1 40 e0 3d 98 b9 fe 62 b8 4a dd 03 32 cc
```

### Etapa 3: Resolver sinalizador final

1. Adicione mais duas operações **XOR** entre o **From Hex** e o **To Hex**.

2. Defina:

   * XOR 1: **CHAVE1**
   * XOR 2: Resultado de **CHAVE1 ^ CHAVE2**
   * XOR 3: Resultado de **CHAVE2 ^ CHAVE3**

3. Adicione no final a operação **From Hex**.

4. Use como entrada: **SINALIZADOR ^ CHAVE1 ^ CHAVE3 ^ CHAVE2**

```
04ee9855208a2cd59091d04767ae47963170d1660df7f56f5faf
```

[![Imagem](https://i.postimg.cc/MpcZ5gss/Captura-de-tela-2025-06-05-194401.png)](https://postimg.cc/K12yvphL)

Resultado:

```
crypto{x0r_i5_ass0c1at1v3}
```

---

## ✅ Conclusão

Esse desafio é um excelente exemplo prático das propriedades do XOR, especialmente a associatividade. Explorando combinações e operações encadeadas, conseguimos reconstruir a chave e revelar a flag final.

> ⚡ A flag final é: **crypto{x0r\_i5\_ass0c1at1v3}**
