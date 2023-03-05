# Glitch Cat

## Descripcion Reto
Our flag printing service has started glitching!`$ nc saturn.picoctf.net 53933`

## Pistas
1. ASCII is one of the most common encodings used in programming
2. We know that the glitch output is valid Python, somehow!
3. Press Ctrl and c on your keyboard to close your connection and return to the command prompt.

## Solución
```bash
ajhagaal-picoctf@webshell:~$ nc saturn.picoctf.net 53933
'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'
^C
ajhagaal-picoctf@webshell:~$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> flag = 'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'
>>> print(flag)
picoCTF{gl17ch_m3_n07_a4392d2e}
>>> 
```

## Bandera
* picoCTF{gl17ch_m3_n07_a4392d2e}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()