# reverse_cipher

## Descripcion Reto
#### Description

We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this). Can you reverse the flag.`

## Pistas
1. objdump and Gihdra are some tools that could assist with this

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/picoCTF_Reversing/reverse_sipher]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev'                                           
--2023-05-09 22:14:44--  https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 16856 (16K) [application/octet-stream]
Grabando a: «rev»

rev                  100%[====================>]  16.46K  --.-KB/s    en 0.006s  

2023-05-09 22:14:50 (2.77 MB/s) - «rev» guardado [16856/16856]

                                                                                  
┌──(kali㉿kali)-[~/hacking/picoCTF_Reversing/reverse_sipher]
└─$ wget 'https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this'
--2023-05-09 22:15:04--  https://jupiter.challenges.picoctf.org/static/31c9b832d036a10daeef52d8b4290ef0/rev_this
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 24 [application/octet-stream]
Grabando a: «rev_this»

rev_this             100%[====================>]      24  --.-KB/s    en 0s      

2023-05-09 22:15:09 (25.4 MB/s) - «rev_this» guardado [24/24]

┌──(kali㉿kali)-[~/hacking/picoCTF_Reversing/reverse_sipher]
└─$ ls -la
total 21
drwxrwx--- 1 root vboxsf     0 may  9 22:15 .
drwxrwx--- 1 root vboxsf     0 may  9 22:13 ..
-rwxrwx--- 1 root vboxsf 16856 oct 26  2020 rev
-rwxrwx--- 1 root vboxsf    24 oct 26  2020 rev_this

┌──(kali㉿kali)-[~/hacking/picoCTF_Reversing/reverse_sipher]
└─$ file rev           
rev: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=523d51973c11197605c76f84d4afb0fe9e59338c, not stripped
                                                                                  
┌──(kali㉿kali)-[~/hacking/picoCTF_Reversing/reverse_sipher]
└─$ file rev_this                              
rev_this: ASCII text, with no line terminators

┌──(kali㉿kali)-[~/hacking/picoCTF_Reversing/reverse_sipher]
└─$ ghidra &
```

![[Pasted image 20230509232057.png]]
![[Pasted image 20230509232240.png]]
![[Pasted image 20230509232300.png]]
![[Pasted image 20230509232327.png]]
![[Pasted image 20230509232404.png]]
![[Pasted image 20230509232455.png]]

```bash
void main(void)

{
  size_t sVar1;
  char flag [23];
  char local_41;
  int local_2c;
  FILE *flagrev;
  FILE *flagfile;
  uint j;
  int i;
  char rev;
  
  flagfile = fopen("flag.txt","r");
  flagrev = fopen("rev_this","a");
  if (flagfile == (FILE *)0x0) {
    puts("No flag found, please make sure this is run on the server");
  }
  if (flagrev == (FILE *)0x0) {
    puts("please run this on the server");
  }
  sVar1 = fread(flag,0x18,1,flagfile);
  local_2c = (int)sVar1;
  if ((int)sVar1 < 1) {
                    /* WARNING: Subroutine does not return */
    exit(0);
  }
  for (i = 0; i < 8; i = i + 1) {
    rev = flag[i];
    fputc((int)rev,flagrev);
  }
  for (j = 8; (int)j < 0x17; j = j + 1) {
    if ((j & 1) == 0) {
      rev = flag[(int)j] + '\x05';
    }
    else {
      rev = flag[(int)j] + -2;
    }
    fputc((int)rev,flagrev);
  }
  rev = local_41;
  fputc((int)local_41,flagrev);
  fclose(flagrev);
  fclose(flagfile);
  return;
```
```python     
cifrado = open('rev_this', 'r').read()
print(cifrado)

flag = ''

for i in range( 8, len(cifrado)-1 ):
        if i & 1 == 0:
                flag += chr( ord(cifrado[i]) - 5 )
        else:
                flag += chr( ord(cifrado[i]) + 2 )

print(flag)
```
```bash
┌──(kali㉿kali)-[~/hacking/picoCTF_Reversing/reverse_sipher]
└─$ python3 exp.py
picoCTF{w1{1wq85jc=2i0<}
r3v3rs37ee84d27
```

## Bandera
* picoCTF{r3v3rs37ee84d27}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()