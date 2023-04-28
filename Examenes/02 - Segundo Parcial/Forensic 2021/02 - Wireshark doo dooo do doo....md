# Wireshark doo dooo do doo...

## Descripcion Reto
Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/d6f9aa16d2a2c51d2e431e658d87af9e/shark1.pcapng).

## Pistas
1. (None)

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/wiresharkDoo]
└─$ wget https://mercury.picoctf.net/static/d6f9aa16d2a2c51d2e431e658d87af9e/shark1.pcapng
--2023-04-18 20:30:36--  https://mercury.picoctf.net/static/d6f9aa16d2a2c51d2e431e658d87af9e/shark1.pcapng
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 1558808 (1.5M) [application/octet-stream]
Grabando a: «shark1.pcapng»

shark1.pcapng             100%[==================================>]   1.49M  1.14MB/s    en 1.3s    

2023-04-18 20:30:43 (1.14 MB/s) - «shark1.pcapng» guardado [1558808/1558808]

┌──(kali㉿kali)-[~/hacking/wiresharkDoo]
└─$ ls
shark1.pcapng

┌──(kali㉿kali)-[~/hacking/wiresharkDoo]
└─$ file shark1.pcapng 
shark1.pcapng: pcapng capture file - version 1.0

┌──(kali㉿kali)-[~/hacking/wiresharkDoo]
└─$ file shark1.pcapng 
shark1.pcapng: pcapng capture file - version 1.0

┌──(kali㉿kali)-[~/hacking/wiresharkDoo]
└─$ wireshark &
[2] 119791
```

Abrimos Wireshark y abrimos el archivo descargado
![[Pasted image 20230418213316.png]]
![[Pasted image 20230418213354.png]]
Se sigue la secuencia TCP
![[Pasted image 20230418213910.png]]
![[Pasted image 20230418214029.png]]
En la secuencia 5 se encuentra algo parecido a la bandera
![[Pasted image 20230418214335.png]]
Haciendo ROT13 a *'Gur synt vf cvpbPGS{c33xno00_1_f33_h_qrnqorrs}'* se pudo encontrar la bandera

## Bandera
* picoCTF{p33kab00_1_s33_u_deadbeef}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []