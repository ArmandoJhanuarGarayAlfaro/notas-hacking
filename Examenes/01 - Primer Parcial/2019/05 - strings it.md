# strings it
#grep

## Descripcion Reto
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings) without running it?

## Pistas
1. [Comando strings](https://linux.die.net/man/1/strings)

## Solución
```bash
ajhagaal-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings
--2023-03-02 19:07:48--  https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 776032 (758K) [application/octet-stream]
Saving to: 'strings'

strings                                                   100%[==================================================================================================================================>] 757.84K  1.85MB/s    in 0.4s    

2023-03-02 19:07:49 (1.85 MB/s) - 'strings' saved [776032/776032]

ajhagaal-picoctf@webshell:~$ ls
README.txt  strings
ajhagaal-picoctf@webshell:~$ chmod 777 strings
ajhagaal-picoctf@webshell:~$ ./strings
Maybe try the 'strings' function? Take a look at the man page
ajhagaal-picoctf@webshell:~$ strings strings | grep picoCTF
picoCTF{5tRIng5_1T_827aee91}
ajhagaal-picoctf@webshell:~$ 
```

## Bandera
* picoCTF{5tRIng5_1T_827aee91}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| strings | Imprime la secuencia de caracteres imprimibles en un archivo binario |
| wget | Descarga una pagina web |

## Referencias
- []()