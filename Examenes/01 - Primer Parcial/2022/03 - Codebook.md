# Nombre Reto

## Descripcion Reto
Run the Python script `code.py` in the same directory as `codebook.txt`.

-   [Download code.py](https://artifacts.picoctf.net/c/101/code.py)
-   [Download codebook.txt](https://artifacts.picoctf.net/c/101/codebook.txt)

## Pistas
1. On the webshell, use `ls` to see if both files are in the directory you are in
2. The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
```bash
ajhagaal-picoctf@webshell:~$ ls
Addadshashanammu      README.txt    decode  flag      netcat    static
Addadshashanammu.zip  convertme.py  file    ltdis.sh  runme.py  warm
ajhagaal-picoctf@webshell:~$ mkdir codebook
ajhagaal-picoctf@webshell:~$ cd codebook/
ajhagaal-picoctf@webshell:~/codebook$ wget https://artifacts.picoctf.net/c/101/code.py
--2023-03-05 01:36:19--  https://artifacts.picoctf.net/c/101/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.6, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py                     100%[========================================>]   1.25K  --.-KB/s    in 0s      

2023-03-05 01:36:19 (458 MB/s) - 'code.py' saved [1278/1278]

ajhagaal-picoctf@webshell:~/codebook$ wget https://artifacts.picoctf.net/c/101/codebook.txt
--2023-03-05 01:36:30--  https://artifacts.picoctf.net/c/101/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.6, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt                100%[========================================>]      27  --.-KB/s    in 0s      

2023-03-05 01:36:30 (19.8 MB/s) - 'codebook.txt' saved [27/27]

ajhagaal-picoctf@webshell:~/codebook$ ls
code.py  codebook.txt
ajhagaal-picoctf@webshell:~/codebook$ python3 code.py 
picoCTF{c0d3b00k_455157_7d102d7a}
```

## Bandera
* picoCTF{c0d3b00k_455157_7d102d7a}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()