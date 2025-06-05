# 🏴‍☠️ Flag Hunters

> Autor: Rafael Bruno

----------
## 💡 Desafio: Engenharia Reversa

### Introdução

> Obs: Usar o Kali Linux facilita o processo.

O enunciado do desafio é o seguinte:

> "Lyrics jump from verses to the refrain kind of like a subroutine call. There's a hidden refrain this program doesn't print by default. Can you get it to print it? There might be something in it for you. The program's source code can be downloaded here. Connect to the program with netcat:
> `$ nc verbal-sleep.picoctf.net 56688`"

Ao baixar e abrir o código, temos o seguinte script em Python:

```[python
import re
import time

# Lê a flag do arquivo
flag = open('flag.txt', 'r').read()

secret_intro = \
'''Pico warriors rising, puzzles laid bare,
Solving each challenge with precision and flair.
With unity and skill, flags we deliver,
The ether’s ours to conquer, ''' + flag + '\n'

song_flag_hunters = secret_intro +\

'''

[REFRAIN]
We’re flag hunters in the ether, lighting up the grid,
No puzzle too dark, no challenge too hid.
With every exploit we trigger, every byte we decrypt,
We’re chasing that victory, and we’ll never quit.
CROWD (Singalong here!);
RETURN

[VERSE1]
Command line wizards, we’re starting it right,
Spawning shells in the terminal, hacking all night.
Scripts and searches, grep through the void,
Every keystroke, we're a cypher's envoy.
Brute force the lock or craft that regex,
Flag on the horizon, what challenge is next?

REFRAIN;

Echoes in memory, packets in trace,
Digging through the remnants to uncover with haste.
Hex and headers, carving out clues,
Resurrect the hidden, it's forensics we choose.
Disk dumps and packet dumps, follow the trail,
Buried deep in the noise, but we will prevail.

REFRAIN;

Binary sorcerers, let’s tear it apart,
Disassemble the code to reveal the dark heart.
From opcode to logic, tracing each line,
Emulate and break it, this key will be mine.
Debugging the maze, and I see through the deceit,
Patch it up right, and watch the lock release.

REFRAIN;

Ciphertext tumbling, breaking the spin,
Feistel or AES, we’re destined to win.
Frequency, padding, primes on the run,
Vigenère, RSA, cracking them for fun.
Shift the letters, matrices fall,
Decrypt that flag and hear the ether call.

REFRAIN;

SQL injection, XSS flow,
Map the backend out, let the database show.
Inspecting each cookie, fiddler in the fight,
Capturing requests, push the payload just right.
HTML's secrets, backdoors unlocked,
In the world wide labyrinth, we’re never lost.

REFRAIN;

Stack's overflowing, breaking the chain,
ROP gadget wizardry, ride it to fame.
Heap spray in silence, memory's plight,
Race the condition, crash it just right.
Shellcode ready, smashing the frame,
Control the instruction, flags call my name.

REFRAIN;

END;
'''

MAX_LINES = 100

def reader(song, startLabel):
    lip = 0
    start = 0
    refrain = 0
    refrain_return = 0
    finished = False

    # Obtém a lista de linhas da música
    song_lines = song.splitlines()

    # Localiza o início, refrão e retorno
    for i in range(len(song_lines)):
        if song_lines[i] == startLabel:
            start = i + 1
        elif song_lines[i] == '[REFRAIN]':
            refrain = i + 1
        elif song_lines[i] == 'RETURN':
            refrain_return = i

    # Imprime as letras
    line_count = 0
    lip = start
    while not finished and line_count < MAX_LINES:
        line_count += 1
        for line in song_lines[lip].split(';'):
            if line == '' and song_lines[lip] != '':
                continue
            if line == 'REFRAIN':
                song_lines[refrain_return] = 'RETURN ' + str(lip + 1)
                lip = refrain
            elif re.match(r"CROWD.*", line):
                crowd = input('Crowd: ')
                song_lines[lip] = 'Crowd: ' + crowd
                lip += 1
            elif re.match(r"RETURN [0-9]+", line):
                lip = int(line.split()[1])
            elif line == 'END':
                finished = True
            else:
                print(line, flush=True)
                time.sleep(0.5)
                lip += 1

reader(song_flag_hunters, '[VERSE1]')]

```

## 🛠️ Resolução

* Analisando o código, percebemos que a flag está definida na variável flag, que é lida diretamente do arquivo flag.txt. Ela é concatenada dentro da variável secret_intro:

```
Analisando o codigo, se ve que a flag esta nesse trecho;

    [secret_intro = \
    '''Pico warriors rising, puzzles laid bare,
    Solving each challenge with precision and flair.
    With unity and skill, flags we deliver,
    The ether’s ours to conquer, '''\
    + flag + '\n']

Analisando uma parte mais a baixo dele vemos que ele pede um RETUN

    [[REFRAIN]
    We’re flag hunters in the ether, lighting up the grid,
    No puzzle too dark, no challenge too hid.
    With every exploit we trigger, every byte we decrypt,
    We’re chasing that victory, and we’ll never quit.
    CROWD (Singalong here!);
    RETURN]
```

--------
## 🧪 Execução com Netcat

* Com isso, ao usar o nc para entrar no servidor

```
[$ nc verbal-sleep.picoctf.net 56688]
```

* Vai imprimir parte da musica até que vai imprimir essa menssagem esperando algo

```
[Crowd:]
```

* Ultilando o comando test;RETUN 0 a frente dessa menssagem, a kali vai imprimir mais parte da musica junto com a flag

```
[Crowd:test;RETUN 0]
```

## 🏁 Resultado

* A flag estará presente nesta parte da música:

``` bash
\[We’re flag hunters in the ether, lighting up the grid,
No puzzle too dark, no challenge too hid.
With every exploit we trigger, every byte we decrypt,
We’re chasing that victory, and we’ll never quit.
Crowd: teste
Pico warriors rising, puzzles laid bare,
Solving each challenge with precision and flair.
With unity and skill, flags we deliver,
The ether’s ours to conquer, picoCTF{70637h3r\_f0r3v3r\_75053bc3}
```
-------

## ✅ Conclusão
Este desafio mostra de forma criativa como explorar fluxos de execução e entradas interativas em scripts. Ao injetar um comando controlado no ponto de entrada do usuário (Crowd:), conseguimos manipular o programa para revelar a flag escondida.

Técnicas como esta são comuns em desafios de engenharia reversa, e destacam a importância de entender fluxo de execução, interação dinâmica e compreensão de código-fonte.

``` bash
picoCTF{70637h3r\_f0r3v3r\_75053bc3}
```
