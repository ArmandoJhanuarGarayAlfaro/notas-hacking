# transposition-trial

## Descripcion Reto
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message. Download the corrupted message [here](https://artifacts.picoctf.net/c/193/message.txt).

## Pistas
1. Split the message up into blocks of 3 and see how the first block is scrambled

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ ls -la
total 5
drwxrwx--- 1 root vboxsf    0 may 14 16:48 .
drwxrwx--- 1 root vboxsf 4096 may 14 16:20 ..
-rwxrwx--- 1 root vboxsf   54 mar 15 21:15 message.txt
                                                                                                   
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ file message.txt 
message.txt: ASCII text, with no line terminators

┌──(kali㉿kali)-[~/hacking/examen3]
└─$ cat message.txt                                                               
heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V9AAB1F8}7 

```

Tomamos **heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V9AAB1F8}7** y lo giramos en bloques de 3 letras hasta el final para encontrar la bandera. El proceso es poner la ultima letra del bloque de 3 al inicio.

* **heT   fl\_   g\_a   s\_i   icp   CTo   {7F   4NR   P05   1N5   \_16  \_35   P3X   51N  3_V   9AA   B1F   8}7**

| bloq 1 | bloq 2 | bloq3 | bloq 4 | bloq 5 | bloq 6 | bloq 7 | bloq 8 | bloq 9 | bloq 10 | bloq 11 | bloq 12 | bloq 13 | bloq 14 | bloq 15 | bloq 16 | bloq 17 | bloq 18 | 
|------|-------|-------|------|-------|-------|------|-------|-------|------|-------|-------|------|-------|-------|------|-------|-------|
| heT | fl_ | g_a | s_i | icp | CTo | {7F | 4NR | PO5 | 1N5 | \_16 |  \_35 | P3X | 51N | 3_V | 9AA | B1F | 8}7 |
| The | \_fl | ag_ | is_ | pic | oCT | F{7 | R4N | 5PO | 5IN | 6_1 | 5_3 | XP3 | N51 | V3_ | A9A | FB1 | 78} |

## Bandera
* picoCTF{7R4N5P051N6_15_3XP3N51V3_A9AFB178}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()