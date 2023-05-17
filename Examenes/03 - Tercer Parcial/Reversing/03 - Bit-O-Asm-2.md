# Bit-O-Asm-2

## Descripcion Reto
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).

## Pistas
1. `PTR`'s or 'pointers', reference a location in memory where values can be stored.

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ ls
disassembler-dump0_b.txt
                                                                                  
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ file disassembler-dump0_b.txt 
disassembler-dump0_b.txt: ASCII text
                                                                                  
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ cat disassembler-dump0_a.txt
cat: disassembler-dump0_a.txt: No existe el fichero o el directorio
                                                                                  
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ cat disassembler-dump0_b.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret      
```

El ciclo normal del codigo va haciendo cambios en una pila donde se tiene el apuntador rbp y se  mueve rsp a la posicion de rbp que ahora sera el apuntador principal.

En la siguiente line se tiene que en la memoria **rbp-0x20**, este elemento apuntara a la direccion de rsi.

En la linea proxima se tiene que la posicion  **rbp-0x4** estara apuntado a la direccion de **0x9fe1a**.

Y por ultimo se tiene que eax apuntara a la direccion que apunta **rbp-0x4** que es el valor **0x9fe1a**.
Dando como resultado que eax es igual a **0x9fe1a**

```bash
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ python3                                 
Python 3.11.2 (main, Mar 13 2023, 12:18:29) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
>>> ascii(0x9fe1a)
'654874'
>>> 
```

## Bandera
* picoCTF{654874}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()