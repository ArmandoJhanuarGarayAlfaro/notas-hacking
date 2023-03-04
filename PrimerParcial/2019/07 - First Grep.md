# First Grep

## Descripcion Reto
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file)? This would be really tedious to look through manually, something tells me there is a better way.

## Pistas
* grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)

## Solución
```bash
ajhagaal-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file
--2023-03-02 22:29:39--  https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 14551 (14K) [application/octet-stream]
Saving to: 'file.1'

file.1                                                    100%[==================================================================================================================================>]  14.21K  --.-KB/s    in 0s      

2023-03-02 22:29:39 (353 MB/s) - 'file.1' saved [14551/14551]

ajhagaal-picoctf@webshell:~$ cat file | grep picoCTF
picoCTF{grep_is_good_to_find_things_dba08a45}
ajhagaal-picoctf@webshell:~$ 
```

## Bandera
* picoCTF{grep_is_good_to_find_things_dba08a45}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- [Funciones wget y grep](obsidian://open?vault=notas_hacking&file=PrimerParcial%2F2019%2F05%20-%20strings%20it)