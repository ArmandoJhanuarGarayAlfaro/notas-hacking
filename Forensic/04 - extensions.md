# extensions

## Descripcion Reto
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?

## Pistas
1. How do operating systems know what kind of file it is? (It's not just the ending!
2. Make sure to submit the flag as picoCTF{XXXXX}

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/forensic/extensions]
└─$ wget https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt    
--2023-03-23 12:36:22--  https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 9984 (9.8K) [application/octet-stream]
Grabando a: «flag.txt»

flag.txt       0%       0  --.-KB/s          flag.txt     100%   9.75K  --.-KB/s    en 0.002s  

2023-03-23 12:36:28 (6.24 MB/s) - «flag.txt» guardado [9984/9984]

                                             
┌──(kali㉿kali)-[~/hacking/forensic/extensions]
└─$ ls               
flag.txt
                                             
┌──(kali㉿kali)-[~/hacking/forensic/extensions]
└─$ file flag.txt    
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced

+ El archivo TXT no es un txt es una imagen + 

┌──(kali㉿kali)-[~/hacking/forensic/extensions]
└─$ mv flag.txt flag.png 

┌──(kali㉿kali)-[~/hacking/forensic/extensions]
└─$ open flag.png 

```
![[Pasted image 20230323124143.png]]

## Bandera
* picoCTF{now_you_know_about_extensions}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()