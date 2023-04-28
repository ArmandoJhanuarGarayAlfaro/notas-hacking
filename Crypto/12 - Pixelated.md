# Pixelated

## Descripcion Reto
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/6e4afb967ef8c865f79f3a8cd7767cca/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/6e4afb967ef8c865f79f3a8cd7767cca/scrambled2.png)

## Pistas
1. [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
2. Think of different ways you can "stack" images

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/pixelated]
└─$ wget https://mercury.picoctf.net/static/6e4afb967ef8c865f79f3a8cd7767cca/scrambled2.png       
--2023-04-27 17:56:06--  https://mercury.picoctf.net/static/6e4afb967ef8c865f79f3a8cd7767cca/scrambled2.png
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 197173 (193K) [application/octet-stream]
Grabando a: «scrambled2.png»

scrambled2.png       100%[====================>] 192.55K   746KB/s    en 0.3s    

2023-04-27 17:56:12 (746 KB/s) - «scrambled2.png» guardado [197173/197173]

                                                                                  
┌──(kali㉿kali)-[~/hacking/pixelated]
└─$ wget https://mercury.picoctf.net/static/6e4afb967ef8c865f79f3a8cd7767cca/scrambled1.png
--2023-04-27 17:57:28--  https://mercury.picoctf.net/static/6e4afb967ef8c865f79f3a8cd7767cca/scrambled1.png
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 197171 (193K) [application/octet-stream]
Grabando a: «scrambled1.png»

scrambled1.png       100%[====================>] 192.55K   710KB/s    en 0.3s    

2023-04-27 17:57:34 (710 KB/s) - «scrambled1.png» guardado [197171/197171]

                                                                                  
┌──(kali㉿kali)-[~/hacking/pixelated]
└─$ ls
scrambled1.png  scrambled2.png

┌──(kali㉿kali)-[~/hacking/pixelated]
└─$ nano exp.py 
```
![Pasted image 20230427191618.png](https://github.com/ArmandoJhanuarGarayAlfaro/notas-hacking/blob/main/Crypto/img/Pasted%20image%2020230427191618.png)

```python
from PIL import Image
import numpy as np

imagen1 = np.asarray( Image.open('scrambled1.png') )
imagen2 = np.asarray( Image.open('scrambled2.png') )

datos = imagen1.copy() + imagen2.copy()

nueva = Image.fromarray(datos)

nueva.save('nueva.png','PNG')
```

```bash
┌──(kali㉿kali)-[~/hacking/pixelated]
└─$ python3 exp.py
                                                                                   
┌──(kali㉿kali)-[~/hacking/pixelated]
└─$ ls
exp.py  nueva.png  scrambled1.png  scrambled2.png
                                                                                   
┌──(kali㉿kali)-[~/hacking/pixelated]
└─$ open nueva.png
```
![Pasted image 20230427191536.png](https://github.com/ArmandoJhanuarGarayAlfaro/notas-hacking/blob/main/Crypto/img/Pasted%20image%2020230427191536.png)

## Bandera
* picoCTF{0542dc1d}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()
