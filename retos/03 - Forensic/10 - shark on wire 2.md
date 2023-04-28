# shark on wire 2

## Descripcion Reto
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

## Pistas
1. 

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/shark_on_wire2]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap'
--2023-03-28 16:58:08--  https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 112318 (110K) [application/octet-stream]
Grabando a: «capture.pcap»

capture.pcap  100% 109.69K   434KB/s    en 0.3s       

2023-03-28 16:58:17 (434 KB/s) - «capture.pcap» guardado [112318/112318]

┌──(kali㉿kali)-[~/hacking/shark_on_wire2]
└─$ wireshark &
[10] 93638
```
![imagen](https://user-images.githubusercontent.com/89482389/228388570-2ba4f957-b7a1-4a5d-a297-9445f2c8ead4.png)
Ahora se tiene que obtener el valor en caracter de cada 5000 pero solo dejando sus ultimos 3 digitos y sin incluir el 5000 solo los que son mayores.
```bash
┌──(kali㉿kali)-[~/hacking/shark_on_wire2]
└─$ nano script.py
```
```python
# pip install scapy
from scapy.all import *

flag = ""

packets = rdpcap('capture.pcap')
for packet in packets:
    # if the packet is a UDP packet going to point 22
    if UDP in packet and packet[UDP].dport == 22:
        flag += chr(packet[UDP].sport - 5000)
print("Flag: {}".format(flag))
```
```bash
┌──(kali㉿kali)-[~/hacking/shark_on_wire2]
└─$ python3 script.py   
Flag: picoCTF{p1LLf3r3d_data_v1a_st3g0}
```
## Bandera
* picoCTF{p1LLf3r3d_data_v1a_st3g0}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()
