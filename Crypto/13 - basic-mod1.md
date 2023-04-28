# basic-mod1

## Descripcion Reto
We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message [here](https://artifacts.picoctf.net/c/127/message.txt). Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

## Pistas
1. Do you know what `mod 37` means?
2. `mod 37` means modulo 37. It gives the remainder of a number after being divided by 37.

## Solución
```bash
──(kali㉿kali)-[~/hacking/basicmod1]
└─$ wget https://artifacts.picoctf.net/c/127/message.txt
--2023-04-27 18:18:09--  https://artifacts.picoctf.net/c/127/message.txt
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.74, 18.154.132.88, 18.154.132.108, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[18.154.132.74]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 85 [application/octet-stream]
Grabando a: «message.txt»

message.txt          100%[=====================>]      85  --.-KB/s    en 0s      

2023-04-27 18:18:14 (71.9 MB/s) - «message.txt» guardado [85/85]

                                                                                   
┌──(kali㉿kali)-[~/hacking/basicmod1]
└─$ cat message.txt 
128 322 353 235 336 73 198 332 202 285 57 87 262 221 218 405 335 101 256 227 112 140 

┌──(kali㉿kali)-[~/hacking/basicmod1]
└─$ nano exp.py 
```

```python
f = open('message.txt').read().split()

flag = ''

for n in f:
        n = int(n) % 37
        if n>=0 and n<=25:
                c = chr(n+65)
        elif n>=26 and n<=35:
                c = chr(n+22)
        else:
                c = '_'
        flag += c

print(flag)
```

```bash
┌──(kali㉿kali)-[~/hacking/basicmod1]
└─$ python3 exp.py
R0UND_N_R0UND_79C18FB3

```


## Bandera
* picoCTF{R0UND_N_R0UND_79C18FB3}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()