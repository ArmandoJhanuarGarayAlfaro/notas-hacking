# PW Crack 3

## Descripcion Reto
Can you crack the password to get the flag?
Download the password checker [here](https://artifacts.picoctf.net/c/24/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/24/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/24/level3.hash.bin) in the same directory too.
There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Pistas
1. To view the level3.hash.bin file in the webshell, do: `$ bvi level3.hash.bin`
2. To exit `bvi` type `:q` and press enter.
3. The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
```bash
ajhagaal-picoctf@webshell:~$ mkdir pw3
ajhagaal-picoctf@webshell:~$ cd pw3
ajhagaal-picoctf@webshell:~/pw3$ wget https://artifacts.picoctf.net/c/24/level3.py
--2023-03-05 02:12:51--  https://artifacts.picoctf.net/c/24/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.120, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: 'level3.py'

level3.py                   100%[========================================>]   1.31K  --.-KB/s    in 0s      

2023-03-05 02:12:51 (63.7 MB/s) - 'level3.py' saved [1337/1337]

ajhagaal-picoctf@webshell:~/pw3$ wget https://artifacts.picoctf.net/c/24/level3.flag.txt.enc
--2023-03-05 02:13:03--  https://artifacts.picoctf.net/c/24/level3.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.6, 108.156.172.74, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.6|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level3.flag.txt.enc'

level3.flag.txt.enc         100%[========================================>]      31  --.-KB/s    in 0s      

2023-03-05 02:13:03 (1.14 MB/s) - 'level3.flag.txt.enc' saved [31/31]

ajhagaal-picoctf@webshell:~/pw3$ wget https://artifacts.picoctf.net/c/24/level3.hash.bin    
--2023-03-05 02:13:15--  https://artifacts.picoctf.net/c/24/level3.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.74, 108.156.172.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level3.hash.bin'

level3.hash.bin             100%[========================================>]      16  --.-KB/s    in 0s      

2023-03-05 02:13:15 (8.66 MB/s) - 'level3.hash.bin' saved [16/16]

ajhagaal-picoctf@webshell:~/pw3$ 
```

## Bandera
* picoCTF{Respuesta}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()