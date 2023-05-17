# ASCII FTW

## Descripcion Reto
This program has constructed the flag using hex ascii values. Identify the flag text by disassembling the program. You can download the file from [here](https://artifacts.picoctf.net/c/507/asciiftw).

## Pistas
1. The combined range of hex-ascii for English alphabets and numerical digits is from 30 to 7A.
2. Online hex-ascii converters can be helpful.

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ ls
asciiftw
                                                                                  
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ file asciiftw      
asciiftw: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=055f4d31f776ff9fba2b38d7e67a7d8a65cdd301, for GNU/Linux 3.2.0, not stripped

┌──(kali㉿kali)-[~/hacking/examen3]
└─$ readelf -h asciiftw
Encabezado ELF:
  Mágico:  7f 45 4c 46 02 01 01 00 00 00 00 00 00 00 00 00 
  Clase:                             ELF64
  Datos:                             complemento a 2, little endian
  Version:                           1 (current)
  OS/ABI:                            UNIX - System V
  Versión ABI:                       0
  Tipo:                              DYN (Position-Independent Executable file)
  Máquina:                           Advanced Micro Devices X86-64
  Versión:                           0x1
  Dirección del punto de entrada:    0x1080
  Inicio de encabezados de programa: 64  (bytes en el fichero)
  Inicio de encabezados de sección:  14768 (bytes en el fichero)
  Opciones:                          0x0
  Size of this header:               64 (bytes)
  Size of program headers:           56 (bytes)
  Number of program headers:         13
  Size of section headers:           64 (bytes)
  Number of section headers:         31
  Section header string table index: 30

┌──(kali㉿kali)-[~/hacking/examen3]
└─$ readelf -d asciiftw

Dynamic section at offset 0x2dc0 contains 27 entries:
  Marca      Tipo                         Nombre/Valor
 0x0000000000000001 (NEEDED)             Biblioteca compartida: [libc.so.6]
 0x000000000000000c (INIT)               0x1000
 0x000000000000000d (FINI)               0x12b8
 0x0000000000000019 (INIT_ARRAY)         0x3db0
 0x000000000000001b (INIT_ARRAYSZ)       8 (bytes)
 0x000000000000001a (FINI_ARRAY)         0x3db8
 0x000000000000001c (FINI_ARRAYSZ)       8 (bytes)
 0x000000006ffffef5 (GNU_HASH)           0x3a0
 0x0000000000000005 (STRTAB)             0x488
 0x0000000000000006 (SYMTAB)             0x3c8
 0x000000000000000a (STRSZ)              159 (bytes)
 0x000000000000000b (SYMENT)             24 (bytes)
 0x0000000000000015 (DEBUG)              0x0
 0x0000000000000003 (PLTGOT)             0x3fb0
 0x0000000000000002 (PLTRELSZ)           48 (bytes)
 0x0000000000000014 (PLTREL)             RELA
 0x0000000000000017 (JMPREL)             0x628
 0x0000000000000007 (RELA)               0x568
 0x0000000000000008 (RELASZ)             192 (bytes)
 0x0000000000000009 (RELAENT)            24 (bytes)
 0x000000000000001e (FLAGS)              BIND_NOW
 0x000000006ffffffb (FLAGS_1)            Opciones: NOW PIE
 0x000000006ffffffe (VERNEED)            0x538
 0x000000006fffffff (VERNEEDNUM)         1
 0x000000006ffffff0 (VERSYM)             0x528
 0x000000006ffffff9 (RELACOUNT)          3
 0x0000000000000000 (NULL)               0x0

```

## Bandera
* picoCTF{Respuesta}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- [ReaderELF comandos](https://linux.die.net/man/1/readelf)