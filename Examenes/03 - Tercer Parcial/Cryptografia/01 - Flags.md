# Flags

## Descripcion Reto
What do the [flags](https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png) mean?

## Pistas
1. The flag is in the format PICOCTF{}

## Solución

```bash
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png'  
--2023-05-14 16:20:43--  https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 43257 (42K) [application/octet-stream]
Grabando a: «flag.png»

flag.png                 100%[=================================>]  42.24K  --.-KB/s    en 0.03s   

2023-05-14 16:20:49 (1.52 MB/s) - «flag.png» guardado [43257/43257]

┌──(kali㉿kali)-[~/hacking/examen3]
└─$ ls -la
total 48
drwxrwx--- 1 root vboxsf     0 may 14 16:20 .
drwxrwx--- 1 root vboxsf  4096 may 14 16:20 ..
-rwxrwx--- 1 root vboxsf 43257 oct 26  2020 flag.png

┌──(kali㉿kali)-[~/hacking/examen3]
└─$ file flag.png 
flag.png: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced

┌──(kali㉿kali)-[~/hacking/examen3]
└─$ open flag.png
```

![[Pasted image 20230514172229.png]]
Haciendo una busqueda de banderas con significado se encontro [banderas maritimas](https://en.wikipedia.org/wiki/International_maritime_signal_flags)
las cuales dan como resultado la bandera del reto:
* PICOCTF{F1AG5AND5TUFF}

## Bandera
* PICOCTF{F1AG5AND5TUFF}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()