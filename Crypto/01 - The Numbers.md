# The Numbers

## Descripcion Reto
The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?

## Pistas
1. The flag is in the format PICOCTF{}

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/numbers]
└─$ wget https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
--2023-04-20 12:17:48--  https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 100721 (98K) [application/octet-stream]
Grabando a: «the_numbers.png»

the_numbers.png   100%[=============>]  98.36K   620KB/s    en 0.2s    

2023-04-20 12:17:57 (620 KB/s) - «the_numbers.png» guardado [100721/100721]

┌──(kali㉿kali)-[~/hacking/numbers]
└─$ ls        
the_numbers.png
                                                                        
┌──(kali㉿kali)-[~/hacking/numbers]
└─$ open the_numbers.png 
```
![[Pasted image 20230420131851.png]]
![[Pasted image 20230420132523.png]]

## Bandera
* picoCTF{Thenumbersmason}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()