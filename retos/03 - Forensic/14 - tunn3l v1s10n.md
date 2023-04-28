# tunn3l v1s10n

## Descripcion Reto
We found this [file](https://mercury.picoctf.net/static/d0129ad98ba9258ab59e7700a1b18c14/tunn3l_v1s10n). Recover the flag.

## Pistas
1. Weird that it won't display right...

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/tunn3lvision]
└─$ wget 'https://mercury.picoctf.net/static/d0129ad98ba9258ab59e7700a1b18c14/tunn3l_v1s10n'
--2023-03-29 23:29:03--  https://mercury.picoctf.net/static/d0129ad98ba9258ab59e7700a1b18c14/tunn3l_v1s10n
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 2893454 (2.8M) [application/octet-stream]
Grabando a: «tunn3l_v1s10n»

tunn3l_v1s10   0%       0  --.-KB/s       tunn3l_v1s10   3% 103.72K   350KB/s       tunn3l_v1s10   7% 215.72K   419KB/s       tunn3l_v1s10  13% 391.72K   535KB/s       tunn3l_v1s10  21% 615.72K   644KB/s       tunn3l_v1s10  31% 887.72K   760KB/s       tunn3l_v1s10  39%   1.08M   793KB/s       tunn3l_v1s10  52%   1.46M   933KB/s       tunn3l_v1s10  64%   1.79M  1004KB/s       tunn3l_v1s10  77%   2.15M  1.06MB/s       tunn3l_v1s10  89%   2.48M  1.10MB/s       tunn3l_v1s10 100%   2.76M  1.16MB/s    en 2.4s    

2023-03-29 23:29:11 (1.16 MB/s) - «tunn3l_v1s10n» guardado [2893454/2893454]

┌──(kali㉿kali)-[~/hacking/tunn3lvision]
└─$ ls                 
tunn3l_v1s10n
                                          
┌──(kali㉿kali)-[~/hacking/tunn3lvision]
└─$ file tunn3l_v1s10n 
tunn3l_v1s10n: data

┌──(kali㉿kali)-[~/hacking/tunn3lvision]
└─$ xxd tunn3l_v1s10n | head
00000000: 424d 8e26 2c00 0000 0000 bad0 0000 bad0  BM.&,...........
00000010: 0000 6e04 0000 3201 0000 0100 1800 0000  ..n...2.........
00000020: 0000 5826 2c00 2516 0000 2516 0000 0000  ..X&,.%...%.....
00000030: 0000 0000 0000 231a 1727 1e1b 2920 1d2a  ......#..'..) .*
00000040: 211e 261d 1a31 2825 352c 2933 2a27 382f  !.&..1(%5,)3*'8/
00000050: 2c2f 2623 332a 262d 2420 3b32 2e32 2925  ,/&#3*&-$ ;2.2)%
00000060: 3027 2333 2a26 382c 2836 2b27 392d 2b2f  0'#3*&8,(6+'9-+/
00000070: 2623 1d12 0e23 1711 2916 0e55 3d31 9776  &#...#..)..U=1.v
00000080: 668b 6652 996d 569e 7058 9e6f 549c 6f54  f.fR.mV.pX.oT.oT
00000090: ab7e 63ba 8c6d bd8a 69c8 9771 c193 71c1  .~c..m..i..q..q.

┌──(kali㉿kali)-[~/hacking/tunn3lvision]
└─$ hexeditor tunn3l_v1s10n
```
![[Pasted image 20230329233219.png]]
![[Pasted image 20230329233604.png]]
![[Pasted image 20230329233643.png]]
```bash
┌──(kali㉿kali)-[~/hacking/tunn3lvision]
└─$ exiftool tunn3l_v1s10n 
ExifTool Version Number         : 12.57
File Name                       : tunn3l_v1s10n
Directory                       : .
File Size                       : 2.9 MB
File Modification Date/Time     : 2023:03:29 23:36:09-06:00
File Access Date/Time           : 2023:03:29 23:36:31-06:00
File Inode Change Date/Time     : 2023:03:29 23:36:09-06:00
File Permissions                : -rwxrwx---
File Type                       : BMP
File Type Extension             : bmp
MIME Type                       : image/bmp
BMP Version                     : Windows V3
Image Width                     : 1134
Image Height                    : 306
Planes                          : 1
Bit Depth                       : 24
Compression                     : None
Image Length                    : 2893400
Pixels Per Meter X              : 5669
Pixels Per Meter Y              : 5669
Num Colors                      : Use BitDepth
Num Important Colors            : All
Image Size                      : 1134x306
Megapixels                      : 0.347

┌──(kali㉿kali)-[~/hacking/tunn3lvision]
└─$ hexeditor tunn3l_v1s10n
```
![[Pasted image 20230329233944.png]]
![[Pasted image 20230329234017.png]]
![[Pasted image 20230329234035.png]]

## Bandera
* picoCTF{qu1t3_a_v13w_2020}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()