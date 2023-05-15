# Vigenere

## Descripcion Reto
Can you decrypt this message? Decrypt this [message](https://artifacts.picoctf.net/c/158/cipher.txt) using this key "CYLAB".

## Pistas
1. https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ ls -la
total 5
drwxrwx--- 1 root vboxsf    0 may 14 17:16 .
drwxrwx--- 1 root vboxsf 4096 may 14 16:20 ..
-rwxrwx--- 1 root vboxsf   43 mar 15 21:15 cipher.txt
                                                                                                   
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ file cipher.txt 
cipher.txt: ASCII text
                                                                                                   
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ cat cipher.txt 
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_cc82272b}
```

![[Pasted image 20230514182122.png]]

Usamos [Cyberchef]() donde le damos el texto a decodificar **rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_cc82272b}** y le damos su llave **CYLAB**, dando como resultado **picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_ae82272q}** 

## Bandera
* picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_ae82272q}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()