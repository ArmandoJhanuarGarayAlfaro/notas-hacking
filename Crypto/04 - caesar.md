# caesar

## Descripcion Reto
Decrypt this [message](https://jupiter.challenges.picoctf.org/static/6385b895dcb30c74dbd1f0ea271e3563/ciphertext).

## Pistas
1. caesar cipher [tutorial](https://learncryptography.com/classical-encryption/caesar-cipher)

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/caesar]
└─$ wget https://jupiter.challenges.picoctf.org/static/6385b895dcb30c74dbd1f0ea271e3563/ciphertext
--2023-04-20 17:32:18--  https://jupiter.challenges.picoctf.org/static/6385b895dcb30c74dbd1f0ea271e3563/ciphertext
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 35 [application/octet-stream]
Grabando a: «ciphertext»

ciphertext                100%[==================================>]      35  --.-KB/s    en 0s      

2023-04-20 17:32:23 (33.0 MB/s) - «ciphertext» guardado [35/35]

                                                                                                     
┌──(kali㉿kali)-[~/hacking/caesar]
└─$ ls
ciphertext
                                                                                                     
┌──(kali㉿kali)-[~/hacking/caesar]
└─$ file ciphertext    
ciphertext: ASCII text, with no line terminators

┌──(kali㉿kali)-[~/hacking/caesar]
└─$ cat ciphertext                       
picoCTF{dspttjohuifsvcjdpoabrkttds}

```
```python
import string
import re

abc = string.ascii_letters

encriptado = open('ciphertext','r').read()
encriptado = re.findall('\{(.*?)}',encriptado)[0]

rot = 25
salida = ''
for car in encriptado:
        salida == abc[ (abc.find(car) + rot) % 26 ]

print(salida)
```
```bash
┌──(kali㉿kali)-[~/hacking/caesar]
└─$ python3 exp.py
crossingtherubiconzaqjsscr
```

Se pone la cadena `dspttjohuifsvcjdpoabrkttds`
![Pasted image 20230420183509.png](https://github.com/ArmandoJhanuarGarayAlfaro/notas-hacking/blob/main/Crypto/img/Pasted%20image%2020230420183509.png)

## Bandera
* picoCTF{crossingtherubiconzaqjsscr}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- [Caesar tutorial cifrador](https://learncryptography.com/classical-encryption/caesar-cipher)
