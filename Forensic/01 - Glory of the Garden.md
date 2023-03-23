# Glory of the Garden

## Descripcion Reto
This [garden](https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg) contains more than it seems.

## Pistas
1. What is a hex editor?

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/forensic/garden_of_the_garden]
└─$ wget https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg
--2023-03-23 12:14:25--  https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 2295192 (2.2M) [application/octet-stream]
Grabando a: «garden.jpg»

garden.jpg     0%       0  --.-KB/s          garden.jpg     4% 103.72K   371KB/s          garden.jpg    15% 343.72K   662KB/s          garden.jpg    30% 679.72K   940KB/s          garden.jpg    51%   1.12M  1.03MB/s          garden.jpg    90%   1.98M  1.54MB/s          garden.jpg   100%   2.19M  1.68MB/s    en 1.3s    

2023-03-23 12:14:32 (1.68 MB/s) - «garden.jpg» guardado [2295192/2295192]

                                             
┌──(kali㉿kali)-[~/hacking/forensic/garden_of_the_garden]
└─$ strings garden.jpg | grep picoCTF
Here is a flag "picoCTF{more_than_m33ts_the_3y3657BaB2C}"
                                             
┌──(kali㉿kali)-[~/hacking/forensic/garden_of_the_garden]
└─$ 

```

## Bandera
* picoCTF{more_than_m33ts_the_3y3657BaB2C}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| strings | obtiene la cadena del archivo |

## Referencias
- []()