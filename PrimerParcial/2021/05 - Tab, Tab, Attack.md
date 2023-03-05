# Nombre Reto

## Descripcion Reto
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/3afd18a65e42b80526aa87f9766c588b/Addadshashanammu.zip)

## Pistas
1. After `unzip`ing, this problem can be solved with 11 button-presses...(mostly Tab)...

## Solución
```bash
ajhagaal-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/3afd18a65e42b80526aa87f9766c588b/Addadshashanammu.zip
--2023-03-05 00:40:45--  https://mercury.picoctf.net/static/3afd18a65e42b80526aa87f9766c588b/Addadshashanammu.zip
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4520 (4.4K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip        100%[========================================>]   4.41K  --.-KB/s    in 0s      

2023-03-05 00:40:45 (1.30 GB/s) - 'Addadshashanammu.zip' saved [4520/4520]

ajhagaal-picoctf@webshell:~$ ls
Addadshashanammu.zip  README.txt  decode  file  flag  ltdis.sh  netcat  static  warm
ajhagaal-picoctf@webshell:~$ unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
ajhagaal-picoctf@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip  README.txt  decode  file  flag  ltdis.sh  netcat  static  warm

```

## Bandera
* picoCTF{Respuesta}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| unzip | Descomprimir un .zip |

## Referencias
- [Descomprimir Zip](https://kinsta.com/es/base-de-conocimiento/descomprimir-archivo-zip/)