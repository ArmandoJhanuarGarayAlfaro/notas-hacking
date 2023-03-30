# WebNet0

## Descripcion Reto
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

## Pistas
1. Try using a tool like Wireshark.
2. How can you decrypt the TLS stream?

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/webnet0]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap'
--2023-03-29 22:38:25--  https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 13163 (13K) [application/octet-stream]
Grabando a: «capture.pcap»

capture.pcap 100%  12.85K  --.-KB/s    en 0.004s  

2023-03-29 22:38:31 (2.90 MB/s) - «capture.pcap» guardado [13163/13163]

┌──(kali㉿kali)-[~/hacking/webnet0]
└─$ wget https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key 
--2023-03-29 22:38:53--  https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 1704 (1.7K) [application/octet-stream]
Grabando a: «picopico.key»

picopico.key 100%   1.66K  --.-KB/s    en 0.003s  

2023-03-29 22:38:59 (554 KB/s) - «picopico.key» guardado [1704/1704]

┌──(kali㉿kali)-[~/hacking/webnet0]
└─$ ls
capture.pcap  picopico.key
                                                  
┌──(kali㉿kali)-[~/hacking/webnet0]
└─$ wireshark &
```
![[Pasted image 20230329224135.png]]
- Ir a edicion, despues a preferencias en la ventana emergente.

![[Pasted image 20230329225459.png]]
- Ir a protocolos
- Seleccionar TLS ![[Pasted image 20230329225611.png]]
- Cargar la llave RSA
![[Pasted image 20230329225725.png]]
![[Pasted image 20230329225741.png]]
![[Pasted image 20230329225801.png]]
![[Pasted image 20230329225839.png]]
- Se desencriptan los paquetes TLS en wireshark
- Buscar en los paquetes "picoCTF"
![[Pasted image 20230329230144.png]]
Pico-Flag: picoCTF{nongshim.shrimp.crackers}

```bash
┌──(kali㉿kali)-[~/hacking/webnet0]
└─$ ssldump -r capture.pcap -k picopico.key -d | grep pico -A 2  
    61 67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67    ag: picoCTF{nong
    73 68 69 6d 2e 73 68 72 69 6d 70 2e 63 72 61 63    shim.shrimp.crac
    6b 65 72 73 7d 0d 0a 43 6f 6e 74 65 6e 74 2d 4c    kers}..Content-L
--
    67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67 73    g: picoCTF{nongs
    68 69 6d 2e 73 68 72 69 6d 70 2e 63 72 61 63 6b    him.shrimp.crack
    65 72 73 7d 0d 0a 43 6f 6e 74 65 6e 74 2d 4c 65    ers}..Content-Le

```

## Bandera
* picoCTF{nongshim.shrimp.crackers}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()