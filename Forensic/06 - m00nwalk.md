# m00nwalk

## Descripcion Reto
Decode this [message](https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav) from the moon.

## Pistas
1. How did pictures from the moon landing get sent back to Earth?
2. What is the CMU mascot?, that might help select a RX option

## Solución
Se descarga QSSTV una aplicación que permite recrear imagenes a traves de un audio.

```bash
┌──(kali㉿kali)-[~/hacking/mOOnwalk]
└─$ sudo apt-get install qsstv && sudo apt-get install pavucontrol -y

┌──(kali㉿kali)-[~/hacking/mOOnwalk]
└─$ qsstv
```
![[Pasted image 20230328111816.png]]
```bash
┌──(kali㉿kali)-[~/hacking/mOOnwalk]
└─$ pavucontrol
```
![[Pasted image 20230328111921.png]]
Se hace una conexion entre pavucontrol y qsstv
```bash
┌──(kali㉿kali)-[~]
└─$ pactl load-module module-null-sink sink_name=virtual-cable
23
┌──(kali㉿kali)-[~/hacking/mOOnwalk]
└─$ paplay -d virtual-cable message.wav

```
![[Pasted image 20230328113744.png]]
![[Pasted image 20230328113759.png]]
![[Pasted image 20230328113938.png]]


## Bandera
* picoCTF{beep_boop_im_in_space}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()