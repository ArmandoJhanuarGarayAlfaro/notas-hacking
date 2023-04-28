# information

## Descripcion Reto
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/7cf6a33f90deeeac5c73407a1bdc99b6/cat.jpg)

## Pistas
1. Look at the details of the file
2. Make sure to submit the flag as picoCTF{XXXXX}

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/information]
└─$ wget https://mercury.picoctf.net/static/7cf6a33f90deeeac5c73407a1bdc99b6/cat.jpg
--2023-04-18 20:10:13--  https://mercury.picoctf.net/static/7cf6a33f90deeeac5c73407a1bdc99b6/cat.jpg
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 878136 (858K) [application/octet-stream]
Grabando a: «cat.jpg»

cat.jpg          100%[==========>] 857.55K   684KB/s    en 1.3s    

2023-04-18 20:10:20 (684 KB/s) - «cat.jpg» guardado [878136/878136]

                                                                    
┌──(kali㉿kali)-[~/hacking/information]
└─$ ls                          
cat.jpg
                                                                    
┌──(kali㉿kali)-[~/hacking/information]
└─$ file cat.jpg                
cat.jpg: JPEG image data, JFIF standard 1.02, aspect ratio, density 1x1, segment length 16, baseline, precision 8, 2560x1598, components 3
                                                                    
┌──(kali㉿kali)-[~/hacking/information]
└─$ binwalk cat.jpg   

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.02

┌──(kali㉿kali)-[~/hacking/information]
└─$ zsteg -a cat.jpg                    
[!] #<ZPNG::NotSupported: Unsupported header "\xFF\xD8\xFF\xE0\x00\x10JF" in #<File:cat.jpg>>

┌──(kali㉿kali)-[~/hacking/information]
└─$ zsteg -a cat.jpg | grep picoCTF

┌──(kali㉿kali)-[~/hacking/information]
└─$ strings cat.jpg | grep picoCTF       

┌──(kali㉿kali)-[~/hacking/information]
└─$ exiftool cat.jpg              
ExifTool Version Number         : 12.57
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
File Modification Date/Time     : 2021:03:15 12:24:46-06:00
File Access Date/Time           : 2023:04:18 20:11:25-06:00
File Inode Change Date/Time     : 2023:04:18 20:10:20-06:00
File Permissions                : -rwxrwx---
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels

┌──(kali㉿kali)-[~/hacking/forensic/so_meta]
└─$ hexeditor cat.jpg 
```


Buscamos entre las palabras entre '' para ver si se puede decodificar la bandera encontrando:
* W5M0MpCehiHzreSzNTczkc9d
* cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
![[Pasted image 20230418212319.png]]

![[Pasted image 20230418212508.png]]
Siendo la segunda la bandera codificada en base64

## Bandera
* picoCTF{the_m3tadata_1s_modified}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []