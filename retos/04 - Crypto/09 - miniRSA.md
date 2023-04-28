# miniRSA

## Descripcion Reto
Let's decrypt this: [ciphertext](https://jupiter.challenges.picoctf.org/static/d21037ad23ed84cfff20a84768a0f2b2/ciphertext)? Something seems a bit small.

## Pistas
1. RSA [tutorial](https://en.wikipedia.org/wiki/RSA_(cryptosystem))
2. How could having too small an e affect the security of this 2048 bit key?
3. Make sure you don't lose precision, the numbers are pretty big (besides the e value)

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/miniRSA]
└─$ wget https://jupiter.challenges.picoctf.org/static/d21037ad23ed84cfff20a84768a0f2b2/ciphertext
--2023-04-23 16:58:23--  https://jupiter.challenges.picoctf.org/static/d21037ad23ed84cfff20a84768a0f2b2/ciphertext
Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 884 [application/octet-stream]
Grabando a: «ciphertext»

ciphertext           100%[=====================>]     884  --.-KB/s    en 0.005s  

2023-04-23 16:58:29 (166 KB/s) - «ciphertext» guardado [884/884]

┌──(kali㉿kali)-[~/hacking/miniRSA]
└─$ cat ciphertext                       

N: 29331922499794985782735976045591164936683059380558950386560160105740343201513369939006307531165922708949619162698623675349030430859547825708994708321803705309459438099340427770580064400911431856656901982789948285309956111848686906152664473350940486507451771223435835260168971210087470894448460745593956840586530527915802541450092946574694809584880896601317519794442862977471129319781313161842056501715040555964011899589002863730868679527184420789010551475067862907739054966183120621407246398518098981106431219207697870293412176440482900183550467375190239898455201170831410460483829448603477361305838743852756938687673
e: 3

ciphertext (c): 2205316413931134031074603746928247799030155221252519872650073010782049179856976080512716237308882294226369300412719995904064931819531456392957957122459640736424089744772221933500860936331459280832211445548332429338572369823704784625368933 

┌──(kali㉿kali)-[~/hacking/miniRSA]
└─$ sudo python3 -m pip install gmpy2 
Collecting gmpy2
  Downloading gmpy2-2.1.5-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (1.8 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.8/1.8 MB 3.6 MB/s eta 0:00:00
Installing collected packages: gmpy2
Successfully installed gmpy2-2.1.5
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv
                                                                                   
┌──(kali㉿kali)-[~/hacking/miniRSA]
└─$ sudo python3 -m pip install pycryptodome
Collecting pycryptodome
  Downloading pycryptodome-3.17-cp35-abi3-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (2.1 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.1/2.1 MB 2.7 MB/s eta 0:00:00
Installing collected packages: pycryptodome
Successfully installed pycryptodome-3.17
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv

┌──(kali㉿kali)-[~/hacking/miniRSA]
└─$ python3
```
```python
Python 3.11.2 (main, Mar 13 2023, 12:18:29) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from Crypto.Util.number import long_to_bytes
>>> from gmpy2 import *
>>> 
>>> gmpy2.get_context().precision=2048
>>> 
>>> e = 3
>>> c = 2205316413931134031074603746928247799030155221252519872650073010782049179856976080512716237308882294226369300412719995904064931819531456392957957122459640736424089744772221933500860936331459280832211445548332429338572369823704784625368933
>>> 
>>> root. exact = iroot(c, e)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'builtin_function_or_method' object has no attribute 'exact'
>>> root, exact = iroot(c, e)
>>> root
mpz(13016382529449106065894479374027604750406953699090365388203708028670029596145277)
>>> print( long_to_bytes(root) )
b'picoCTF{n33d_a_lArg3r_e_ccaa7776}'
>>> 
```

## Bandera
* picoCTF{n33d_a_lArg3r_e_ccaa7776}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()