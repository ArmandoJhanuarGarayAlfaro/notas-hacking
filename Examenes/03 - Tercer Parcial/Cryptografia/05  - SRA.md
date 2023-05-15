# SRA

## Descripcion Reto
I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check...

Additional details will be available after launching your challenge instance.

## Pistas
1. (None)

## Solución
```bash
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ ls -la
total 5
drwxrwx--- 1 root vboxsf    0 may 14 17:23 .
drwxrwx--- 1 root vboxsf 4096 may 14 16:20 ..
-rwxrwx--- 1 root vboxsf  630 mar 15 21:15 chal.py
                                                                                                   
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ file chal.py      
chal.py: Python script, ASCII text executable

┌──(kali㉿kali)-[~/hacking/examen3]
└─$ cat chal.py 
from Crypto.Util.number import getPrime, inverse, bytes_to_long
from string import ascii_letters, digits
from random import choice

pride = "".join(choice(ascii_letters + digits) for _ in range(16))
gluttony = getPrime(128)
greed = getPrime(128)
lust = gluttony * greed
sloth = 65537
envy = inverse(sloth, (gluttony - 1) * (greed - 1))

anger = pow(bytes_to_long(pride.encode()), sloth, lust)

print(f"{anger = }")
print(f"{envy = }")

print("vainglory?")
vainglory = input("> ").strip()

if vainglory == pride:
    print("Conquered!")
    with open("/challenge/flag.txt") as f:
        print(f.read())
else:
    print("Hubris!")

┌──(kali㉿kali)-[~/hacking/examen3]
└─$ python3 chal.py 
anger = 7217017699850873428502317422956943847980147725257447219466804442470175040981
envy = 39023773447220568111675691744950604559314961543941862697393453052301149894913
vainglory?
```

Renombremos las variables para que sea mucho mas entendible
```bash
┌──(kali㉿kali)-[~/hacking/examen3]
└─$ cat chal.py  
from Crypto.Util.number import getPrime, inverse, bytes_to_long
from string import ascii_letters, digits
from random import choice

plain = "".join(choice(ascii_letters + digits) for _ in range(16)) # Pride
p = getPrime(128) # gluttony
q  = getPrime(128) # greed
n = p * q # lust
e = 65537 # sloth
tn = (p - 1) * (q - 1)
d = inverse(e, tn) # envi

c = pow(bytes_to_long( plain.encode()), e, n ) # anger

print(f"{c = }")
print(f"{d = }")

print("vainglory?")
vainglory = input("> ").strip()

if vainglory == plain:
    print("Conquered!")
    with open("/challenge/flag.txt") as f:
        print(f.read())
else:
    print("Hubris!")
```

Entramos a python para empezar a desencriptar el mensaje
```python
>>> from Crypto.Util.number import long_to_bytes
>>> from Crypto.Util.number import inverse
>>> 
```

## Bandera
* picoCTF{Respuesta}

## Notas adicionales
| Comando | Descripcion |
|---------|-------------|
|  |  |

## Referencias
- []()