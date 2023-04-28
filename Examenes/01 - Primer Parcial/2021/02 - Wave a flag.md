# Wave a flag

## Descripcion Reto
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/a00f554b16385d9970dae424f66ee1ab/warm) has extraordinarily helpful information...

## Pistas
1. This program will only work in the webshell or another Linux computer.
2. To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/a00f554b16385d9970dae424f66ee1ab/warm`
3. Run this program by entering the following in the Terminal prompt: `$ ./warm`, but you'll first have to make it executable with `$ chmod +x warm`
4. -h and --help are the most common arguments to give to programs to get more information from them!
5. Not every program implements help features like -h and --help.

## Solución
```bash
ajhagaal-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/a00f554b16385d9970dae424f66ee1ab/warm
--2023-03-04 23:44:31--  https://mercury.picoctf.net/static/a00f554b16385d9970dae424f66ee1ab/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm'

warm                        100%[========================================>]  10.68K  --.-KB/s    in 0s      

2023-03-04 23:44:32 (272 MB/s) - 'warm' saved [10936/10936]

ajhagaal-picoctf@webshell:~$ ls
README.txt  file  flag  warm
ajhagaal-picoctf@webshell:~$ ls -l
total 308
-rw-r--r-- 1 root             root               4443 Mar  4 22:31 README.txt
-rw-rw-r-- 1 ajhagaal-picoctf ajhagaal-picoctf 288821 Mar  4 22:33 file
-rw-rw-r-- 1 ajhagaal-picoctf ajhagaal-picoctf     34 Mar 16  2021 flag
-rw-rw-r-- 1 ajhagaal-picoctf ajhagaal-picoctf  10936 Mar 16  2021 warm
ajhagaal-picoctf@webshell:~$ sudo chmod +x warm
-bash: sudo: command not found
ajhagaal-picoctf@webshell:~$ chmod +x warm
ajhagaal-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_18788aaa}
ajhagaal-picoctf@webshell:~$ 


```

## Bandera
* picoCTF{b1scu1ts_4nd_gr4vy_18788aaa}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| chmod +x | Da permisos de ejecucion |

## Referencias
- []()