# shark on wire 1

## Descripcion Reto
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

## Pistas
1. Try using a tool like Wireshark
2. What are streams?

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/forensic/shark_on_wire1]
└─$ wget https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
--2023-03-23 12:26:31--  https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 239455 (234K) [application/octet-stream]
Grabando a: «capture.pcap»

capture.pcap   0%       0  --.-KB/s          capture.pcap  44% 103.72K   400KB/s          capture.pcap 100% 233.84K   597KB/s    en 0.4s    

2023-03-23 12:26:37 (597 KB/s) - «capture.pcap» guardado [239455/239455]

┌──(kali㉿kali)-[~/hacking/forensic/shark_on_wire1]
└─$ file capture.pcap 
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)
```

Entrar a wireshark para introducir la captura y seguir una trama para encontrar la bandera

![[Pasted image 20230323123400.png]]
![[Pasted image 20230323123503.png]]
## Bandera
* picoCTF{StaT31355_626f6efe}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []