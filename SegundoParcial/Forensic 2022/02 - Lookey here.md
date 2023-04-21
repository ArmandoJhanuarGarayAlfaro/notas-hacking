# Lookey here

## Descripcion Reto
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it. Download the data [here](https://artifacts.picoctf.net/c/124/anthem.flag.txt).

## Pistas
1. Download the file and search for the flag based on the known prefix

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/lookey]
└─$ wget https://artifacts.picoctf.net/c/124/anthem.flag.txt 
--2023-04-18 21:02:07--  https://artifacts.picoctf.net/c/124/anthem.flag.txt
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.144.107, 18.154.144.85, 18.154.144.104, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[18.154.144.107]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 108668 (106K) [application/octet-stream]
Grabando a: «anthem.flag.txt»

anthem.flag.txt           100%[==================================>] 106.12K  --.-KB/s    en 0.1s    

2023-04-18 21:02:13 (732 KB/s) - «anthem.flag.txt» guardado [108668/108668]

┌──(kali㉿kali)-[~/hacking/lookey]
└─$ ls
anthem.flag.txt
                                                                                                     
┌──(kali㉿kali)-[~/hacking/lookey]
└─$ file anthem.flag.txt 
anthem.flag.txt: Unicode text, UTF-8 text
                                                                                                     
┌──(kali㉿kali)-[~/hacking/lookey]
└─$ cat anthem.flag.txt | grep picoCTF
      we think that the men of picoCTF{gr3p_15_@w3s0m3_4c479940}
```

## Bandera
* picoCTF{gr3p_15_@w3s0m3_4c479940}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()