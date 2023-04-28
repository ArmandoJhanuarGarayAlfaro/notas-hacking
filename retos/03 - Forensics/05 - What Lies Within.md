# What Lies Within

## Descripcion Reto
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?

## Pistas
1. There is data encoded somewhere... there might be an online decoder.

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/forensic/what_lies_whitin]
└─$ wget https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
--2023-03-23 15:12:37--  https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 625219 (611K) [application/octet-stream]
Grabando a: «buildings.png.1»

buildings.pn   0%       0  --.-KB/s          buildings.pn  16% 103.72K   398KB/s          buildings.pn  56% 343.72K   690KB/s          buildings.pn 100% 610.57K   972KB/s    en 0.6s    

2023-03-23 15:12:43 (972 KB/s) - «buildings.png.1» guardado [625219/625219]

┌──(kali㉿kali)-[~/hacking/forensic/what_lies_whitin]
└─$ ls
buildings.png 

┌──(kali㉿kali)-[~/hacking/forensic/what_lies_whitin]
└─$ zsteg -a buildings.png | grep pico
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"

```

## Bandera
* picoCTF{h1d1ng_1n_th3_b1t5}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
| zsteg -a | Busca informacion en imagenes para decodificarla u obtener información por todas las tecnicas posibles. |

## Referencias
- [Decodifica una imagen obtener informacion oculta](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&ved=2ahUKEwin_4aW2_L9AhXGLUQIHWqZBzIQFnoECBIQAQ&url=https%3A%2F%2Fstylesuxx.github.io%2Fsteganography%2F&usg=AOvVaw3BoM9agDA-VTpFMEwSX5LG)