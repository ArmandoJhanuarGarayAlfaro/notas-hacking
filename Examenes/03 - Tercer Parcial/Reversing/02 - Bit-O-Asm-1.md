# Bit-O-Asm-1

## Descripcion Reto
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`. Download the assembly dump [here](https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt).

## Pistas
1. As with most assembly, there is a lot of noise in the instruction dump. Find the one line that pertains to this question and don't second guess yourself!

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ ls
disassembler-dump0_a.txt
                                                                                  
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ cat disassembler-dump0_a.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x4],edi
<+11>:    mov    QWORD PTR [rbp-0x10],rsi
<+15>:    mov    eax,0x30
<+20>:    pop    rbp
<+21>:    ret
```

La respuesta es 0x30 ya que no se hace ningun salto solo se sigue la linea comun del codigo y en eax solo se mueve el valor de 0x30 a esa variable.
Bandera = 0x30 

```bash
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ python3
Python 3.11.2 (main, Mar 13 2023, 12:18:29) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> ascii(0x30)
'48'
```

## Bandera
* picoCTF{48}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()