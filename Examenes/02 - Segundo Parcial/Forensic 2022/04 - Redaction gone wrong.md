# Redaction gone wrong

## Descripcion Reto
Now you DON’T see me. This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

## Pistas
1. How can you be sure of the redaction?

## Solución
```bash
──(kali㉿kali)-[~/hacking/redactionGoneWrong]
└─$ wget https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
--2023-04-18 21:25:43--  https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.144.85, 18.154.144.104, 18.154.144.107, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[18.154.144.85]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 34915 (34K) [application/octet-stream]
Grabando a: «Financial_Report_for_ABC_Labs.pdf»

Financial_Report_for_ABC_ 100%[==================================>]  34.10K  --.-KB/s    en 0.03s   

2023-04-18 21:25:49 (1.25 MB/s) - «Financial_Report_for_ABC_Labs.pdf» guardado [34915/34915]

                                                                                                     
┌──(kali㉿kali)-[~/hacking/redactionGoneWrong]
└─$ ls
Financial_Report_for_ABC_Labs.pdf

┌──(kali㉿kali)-[~/hacking/redactionGoneWrong]
└─$ open Financial_Report_for_ABC_Labs.pdf 

```
![[Pasted image 20230418222757.png]]
Seleccione todo el texto con el cursor
![[Pasted image 20230418222839.png]]
Y la bandera se mostró.

## Bandera
* picoCTF{C4n_Y0u_S33_m3_fully}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()