# HideToSee

## Descripcion Reto
How about some hide and seek heh? Look at this image [here](https://artifacts.picoctf.net/c/235/atbash.jpg).

## Pistas
1. Download the image and try to extract it.

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/hidetosee]
└─$ wget 'https://artifacts.picoctf.net/c/235/atbash.jpg'
--2023-04-27 18:24:05--  https://artifacts.picoctf.net/c/235/atbash.jpg
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.132.88, 18.154.132.74, 18.154.132.108, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[18.154.132.88]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 51499 (50K) [application/octet-stream]
Grabando a: «atbash.jpg»

atbash.jpg           100%[=====================>]  50.29K  --.-KB/s    en 0.08s   

2023-04-27 18:24:11 (630 KB/s) - «atbash.jpg» guardado [51499/51499]

                                                                                   
┌──(kali㉿kali)-[~/hacking/hidetosee]
└─$ ls
atbash.jpg

┌──(kali㉿kali)-[~/hacking/hidetosee]
└─$ open atbash.jpg

```
![[Pasted image 20230427192512.png]]
```bash
┌──(kali㉿kali)-[~/hacking/hidetosee]
└─$ steghide extract -sf atbash.jpg
Anotar salvoconducto: 
anot� los datos extra�dos e/"encrypted.txt".
                                                                                   
┌──(kali㉿kali)-[~/hacking/hidetosee]
└─$ ls
atbash.jpg  encrypted.txt
                                                                                   
┌──(kali㉿kali)-[~/hacking/hidetosee]
└─$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_92533667}
```
![[Pasted image 20230427193811.png]]


## Bandera
* picoCTF{atbash_crack_92533667}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()