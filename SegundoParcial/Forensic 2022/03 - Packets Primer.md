# Packets Primer

## Descripcion Reto
Download the packet capture file and use packet analysis software to find the flag.

-   [Download packet capture](https://artifacts.picoctf.net/c/194/network-dump.flag.pcap)

## Pistas
1. Wireshark, if you can install and use it, is probably the most beginner friendly packet analysis software product.

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/packetsPrimer]
└─$ wget https://artifacts.picoctf.net/c/194/network-dump.flag.pcap
--2023-04-18 21:12:45--  https://artifacts.picoctf.net/c/194/network-dump.flag.pcap
Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.144.107, 18.154.144.85, 18.154.144.103, ...
Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[18.154.144.107]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 778 [application/octet-stream]
Grabando a: «network-dump.flag.pcap»

network-dump.flag.pcap    100%[==================================>]     778  --.-KB/s    en 0.003s  

2023-04-18 21:12:50 (247 KB/s) - «network-dump.flag.pcap» guardado [778/778]

                                                                                                     
┌──(kali㉿kali)-[~/hacking/packetsPrimer]
└─$ ls
network-dump.flag.pcap
                                                                                                     
┌──(kali㉿kali)-[~/hacking/packetsPrimer]
└─$ wireshark &                                                    
[2] 141904

```
![[Pasted image 20230418221358.png]]
Se siguen las tramas de TCP 
![[Pasted image 20230418221500.png]]
![[Pasted image 20230418222056.png]]

## Bandera
* picoCTF{p4ck37_5h4rk_ceccaa7f}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()