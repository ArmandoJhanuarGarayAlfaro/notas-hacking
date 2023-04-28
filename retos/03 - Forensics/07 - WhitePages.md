# WhitePages

## Descripcion Reto
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt) is all blank!

## Pistas
1. 

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/whitepages]
└─$ wget https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt
--2023-03-28 11:43:32--  https://jupiter.challenges.picoctf.org/static/74274b96fe966126a1953c80762af80d/whitepages.txt
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 2964 (2.9K) [application/octet-stream]
Grabando a: «whitepages.txt»

whitepages.t   0%       0  --.-KB/s          whitepages.t 100%   2.89K  --.-KB/s    en 0.003s  

2023-03-28 11:43:48 (1017 KB/s) - «whitepages.txt» guardado [2964/2964]

                                             
┌──(kali㉿kali)-[~/hacking/whitepages]
└─$ nano conversor.py
```
```python
def convertSpacesToBinary():
    with open('whitepages.txt', 'rb') as f:
        result = f.read()
        result = result.replace(b'\xe2\x80\x83', b'0')
        result = result.replace(b'\x20', b'1')
        result = result.decode()
    return result    

def convertFromBinaryToASCII(binaryValues):

    binary_int = int(binaryValues, 2)
    byte_number = binary_int.bit_length() + 7 // 8

    binary_array = binary_int.to_bytes(byte_number, "big")
    ascii_text = binary_array.decode('ascii')

    print(ascii_text)

convertFromBinaryToASCII(convertSpacesToBinary()) 
```
```bash
┌──(kali㉿kali)-[~/hacking/whitepages]
└─$ python3 conversor.py 

                picoCTF

                SEE PUBLIC RECORDS & BACKGROUND REPORT
                5000 Forbes Ave, Pittsburgh, PA 15213
                picoCTF{not_all_spaces_are_created_equal_c54f27cd05c2189f8147cc6f5deb2e56}
```
## Bandera
* picoCTF{not_all_spaces_are_created_equal_c54f27cd05c2189f8147cc6f5deb2e56}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()