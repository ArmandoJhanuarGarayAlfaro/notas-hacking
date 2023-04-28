# c0rrupt

## Descripcion Reto
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

## Pistas
1. Try fixing the file header

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/corrupt]
└─$ wget https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery       
--2023-03-28 12:04:23--  https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 202940 (198K) [application/octet-stream]
Grabando a: «mystery»

mystery        0%       0  --.-KB/s          mystery       52% 103.72K   147KB/s          mystery      100% 198.18K   222KB/s    en 0.9s    

2023-03-28 12:04:32 (222 KB/s) - «mystery» guardado [202940/202940]

┌──(kali㉿kali)-[~/hacking/corrupt]
└─$ ls
mystery

┌──(kali㉿kali)-[~/hacking/corrupt]
└─$ file mystery 
mystery: data

┌──(kali㉿kali)-[~/hacking/corrupt]
└─$ xxd mystery | head
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71 bd2d 8b20 2080 9041 8302 08d0  .d.q.-.  ..A....
00000070: f9ed 40a0 f36e 407b 9023 8f1e d720 8b3e  ..@..n@{.#... .>
00000080: b7c1 0d70 0374 b503 ae41 6bf8 bea8 fbdc  ...p.t...Ak.....
00000090: 3e7d 2a22 336f de5b 55dd 3d3d f920 9188  >}*"3o.[U.==. ..
Se cambia el HEADER para que corresponda al de un png

┌──(kali㉿kali)-[~/hacking/corrupt]
└─$ xxd -g 1 mystery.png | head
00000000: 89 50 4e 47 0d 0a b0 aa 00 00 00 0d 49 48 44 52  .PNG........IHDR
00000010: 00 00 06 6a 00 00 04 47 08 02 00 00 00 7c 8b ab  ...j...G.....|..
00000020: 78 00 00 00 01 73 52 47 42 00 ae ce 1c e9 00 00  x....sRGB.......
00000030: 00 04 67 41 4d 41 00 00 b1 8f 0b fc 61 05 00 00  ..gAMA......a...
00000040: 00 09 70 48 59 73 aa 00 16 25 00 00 16 25 01 49  ..pHYs...%...%.I
00000050: 52 24 f0 aa aa ff a5 ab 44 45 54 78 5e ec bd 3f  R$......DETx^..?
00000060: 8e 64 cd 71 bd 2d 8b 20 20 80 90 41 83 02 08 d0  .d.q.-.  ..A....
00000070: f9 ed 40 a0 f3 6e 40 7b 90 23 8f 1e d7 20 8b 3e  ..@..n@{.#... .>
00000080: b7 c1 0d 70 03 74 b5 03 ae 41 6b f8 be a8 fb dc  ...p.t...Ak.....
00000090: 3e 7d 2a 22 33 6f de 5b 55 dd 3d 3d f9 20 91 88  >}*"3o.[U.==. ..

┌──(kali㉿kali)-[~/hacking/corrupt]
└─$ xxd -g 1 -s 0x3e -l $((4+4+9+4)) mystery  
0000003e: 00 00 00 09 70 48 59 73 aa 00 16 25 00 00 16 25  ....pHYs...%...%
0000004e: 01 49 52 24 f0  

┌──(kali㉿kali)-[~/hacking/corrupt]
└─$ hexeditor mystery       
                                                                                                                    
┌──(kali㉿kali)-[~/hacking/corrupt]
└─$ xxd -g 1 -s 0x3e -l $((4+4+9+4)) mystery  
0000003e: 00 00 00 09 70 48 59 73 aa 00 16 25 00 00 16 25  ....pHYs...%...%
0000004e: 01 49 52 24 f0                                   .IR$.
                                                                                                                    
┌──(kali㉿kali)-[~/hacking/corrupt]
└─$ printf '\x00' | dd of=mystery bs=1 seek=70 count=1 conv=notrunc
1+0 records in
1+0 records out
1 byte copied, 0.00140823 s, 0.7 kB/s
                                                                                                                    
┌──(kali㉿kali)-[~/hacking/corrupt]
└─$ xxd -g 1 mystery | head  
00000000: 89 50 4e 47 0d 0a b0 aa 00 00 00 0d 49 48 44 52  .PNG........IHDR
00000010: 00 00 06 6a 00 00 04 47 08 02 00 00 00 7c 8b ab  ...j...G.....|..
00000020: 78 00 00 00 01 73 52 47 42 00 ae ce 1c e9 00 00  x....sRGB.......
00000030: 00 04 67 41 4d 41 00 00 b1 8f 0b fc 61 05 00 00  ..gAMA......a...
00000040: 00 09 70 48 59 73 00 00 16 25 00 00 16 25 01 49  ..pHYs...%...%.I
00000050: 52 24 f0 aa aa ff a5 ab 44 45 54 78 5e ec bd 3f  R$......DETx^..?
00000060: 8e 64 cd 71 bd 2d 8b 20 20 80 90 41 83 02 08 d0  .d.q.-.  ..A....
00000070: f9 ed 40 a0 f3 6e 40 7b 90 23 8f 1e d7 20 8b 3e  ..@..n@{.#... .>
00000080: b7 c1 0d 70 03 74 b5 03 ae 41 6b f8 be a8 fb dc  ...p.t...Ak.....
00000090: 3e 7d 2a 22 33 6f de 5b 55 dd 3d 3d f9 20 91 88  >}*"3o.[U.==. ..
                                                                                                                    
┌──(kali㉿kali)-[~/hacking/corrupt]
└─$ xxd -g 1 -s 0x53 -l 8 mystery                                  
00000053: aa aa ff a5 ab 44 45 54                          .....DET
                                                                                                                    
┌──(kali㉿kali)-[~/hacking/corrupt]
└─$ printf 'IDAT' | dd of=mystery bs=1 seek=87 count=4 conv=notrunc
4+0 records in
4+0 records out
4 bytes copied, 0.00278143 s, 1.4 kB/s
                                                                                                                    
┌──(kali㉿kali)-[~/hacking/corrupt]
└─$ binwalk -R "IDAT" mystery  

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
87            0x57            Raw signature (IDAT)
65544         0x10008         Raw signature (IDAT)
131080        0x20008         Raw signature (IDAT)
196616        0x30008         Raw signature (IDAT)

┌──(kali㉿kali)-[~/hacking/corrupt]
└─$ printf '\x00\x00' | dd of=mystery bs=1 seek=83 count=2 conv=notrunc
2+0 records in
2+0 records out
2 bytes copied, 0.00387289 s, 0.5 kB/s

┌──(kali㉿kali)-[~/hacking/corrupt]
└─$ xxd -g 1 mystery | head                                            
00000000: 89 50 4e 47 0d 0a 1a 0a 00 00 00 0d 49 48 44 52  .PNG........IHDR
00000010: 00 00 06 6a 00 00 04 47 08 02 00 00 00 7c 8b ab  ...j...G.....|..
00000020: 78 00 00 00 01 73 52 47 42 00 ae ce 1c e9 00 00  x....sRGB.......
00000030: 00 04 67 41 4d 41 00 00 b1 8f 0b fc 61 05 00 00  ..gAMA......a...
00000040: 00 09 70 48 59 73 00 00 16 25 00 00 16 25 01 49  ..pHYs...%...%.I
00000050: 52 24 f0 00 00 ff a5 49 44 41 54 78 5e ec bd 3f  R$.....IDATx^..?
00000060: 8e 64 cd 71 bd 2d 8b 20 20 80 90 41 83 02 08 d0  .d.q.-.  ..A....
00000070: f9 ed 40 a0 f3 6e 40 7b 90 23 8f 1e d7 20 8b 3e  ..@..n@{.#... .>
00000080: b7 c1 0d 70 03 74 b5 03 ae 41 6b f8 be a8 fb dc  ...p.t...Ak.....
00000090: 3e 7d 2a 22 33 6f de 5b 55 dd 3d 3d f9 20 91 88  >}*"3o.[U.==. ..

┌──(kali㉿kali)-[~/hacking/corrupt]
└─$ pngcheck -v mystery   
File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
  chunk IDAT at offset 0x00057, length 65445
    zlib: deflated, 32K window, fast compression
  chunk IDAT at offset 0x10008, length 65524
  chunk IDAT at offset 0x20008, length 65524
  chunk IDAT at offset 0x30008, length 6304
  chunk IEND at offset 0x318b4, length 0
No errors detected in mystery (9 chunks, 96.3% compression).
```
![[Pasted image 20230328163025.png]]

## Bandera
* picoCTF{c0rrupt10n_1847995}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| hexeditor | Edita o administra diferentes datos como ASCII, binario, etc |
| pngcheck | Verifica la integridad de los archivos PNG, JNG y MNG |

## Referencias
- []