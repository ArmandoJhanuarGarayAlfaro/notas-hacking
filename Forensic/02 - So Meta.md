# So Meta

## Descripcion Reto
Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/00efdf2961da1e21470ffc0d496c3cc2/pico_img.png).

## Pistas
1. What does meta mean in the context of files?
2. Ever heard of metadata?

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/forensic/so_meta]
└─$ wget https://jupiter.challenges.picoctf.org/static/00efdf2961da1e21470ffc0d496c3cc2/pico_img.png
--2023-03-23 12:18:21--  https://jupiter.challenges.picoctf.org/static/00efdf2961da1e21470ffc0d496c3cc2/pico_img.png
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 108795 (106K) [application/octet-stream]
Grabando a: «pico_img.png»

pico_img.png   0%       0  --.-KB/s          pico_img.png  97% 103.72K   425KB/s          pico_img.png 100% 106.25K   432KB/s    en 0.2s    

2023-03-23 12:18:27 (432 KB/s) - «pico_img.png» guardado [108795/108795]

──(kali㉿kali)-[~/hacking/forensic/so_meta]
└─$ ls
pico_img.png

┌──(kali㉿kali)-[~/hacking/forensic/so_meta]
└─$ exiftool pico_img.png 
ExifTool Version Number         : 12.57
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2020:10:26 12:38:23-06:00
File Access Date/Time           : 2023:03:23 12:18:27-06:00
File Inode Change Date/Time     : 2023:03:23 12:18:29-06:00
File Permissions                : -rwxrwx---
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Warning                         : [minor] Text/EXIF chunk(s) found after PNG IDAT (may be ignored by some readers)
Artist                          : picoCTF{s0_m3ta_fec06741}
Image Size                      : 600x600
Megapixels                      : 0.360

┌──(kali㉿kali)-[~/hacking/forensic/so_meta]
└─$ exiftool pico_img.png | grep pico
File Name                       : pico_img.png
Artist                          : picoCTF{s0_m3ta_fec06741}
                                             
┌──(kali㉿kali)-[~/hacking/forensic/so_meta]
└─$ 

┌──(kali㉿kali)-[~/hacking/forensic/so_meta]
└─$ strings pico_img.png | grep pico 
picoCTF{s0_m3ta_fec06741}
                                             
┌──(kali㉿kali)-[~/hacking/forensic/so_meta]
└─$ 

```

## Bandera
* picoCTF{s0_m3ta_fec06741}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| exilftool | Muestra los metadatos del archivo |

## Referencias
- []()