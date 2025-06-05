# 💡XOR Starter

> Autor: @Ralfbp

---

## ✨ Desafio: XOR

> Link: https://cryptohack.org/courses/intro/xor0/

------
### Introdução

> Obs: Utilizar o Kali Linux facilita o processo.

O enunciado apresenta a palavra **label** e solicita que seja aplicada a operação XOR em cada caractere dessa palavra, utilizando o inteiro **13** como chave.

[![Captura-de-tela-2025-06-03-144142.png](https://i.postimg.cc/0N3zstfg/Captura-de-tela-2025-06-03-144142.png)](https://postimg.cc/ns4FKGgT)

Sabemos também que a flag será formatada como:

```
crypto{nova_string}
```

---

## 🛠️ Resolução

Com base nas informações fornecidas, podemos usar o terminal do Kali Linux para realizar o XOR byte a byte. Um comando prático e direto para isso é:

```bash
echo -n "label" | perl -pe 's/(.)/chr(ord($1) ^ 13)/ge'
```

Esse comando faz o seguinte:

* `echo -n "label"`: imprime a palavra sem quebra de linha.
* `perl -pe ...`: aplica uma substituição para cada caractere, utilizando XOR com 13 (`ord($1) ^ 13`), e converte de volta para caractere (`chr(...)`).

[![Captura-de-tela-2025-06-03-144108.png](https://i.postimg.cc/Mp4gwRhM/Captura-de-tela-2025-06-03-144108.png)](https://postimg.cc/Hrw64JWd)

Ao executar esse comando, obtemos como saída:

```
aloha
```

Portanto, a flag é:

```
crypto{aloha}
```

---

## ✅ Conclusão

Esse desafio é uma ótima introdução ao conceito de operações bit a bit, especificamente o operador XOR. Esse tipo de operação é comum em criptografia básica e em desafios de CTF (Capture The Flag).

Utilizar ferramentas simples, como Perl no terminal, demonstra como é possível resolver problemas criptográficos com comandos compactos e eficientes.

> ⚡ A flag final é: **crypto{aloha}**